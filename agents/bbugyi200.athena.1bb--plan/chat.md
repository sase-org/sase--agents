# Chat History - ace-run (1bb--plan)

- **TIMESTAMP:** 2026-11-11 10:27:43 EST
- **MODEL:** claude/opus
- **AGENT:** 1bb--plan

**Plan:** /home/bryan/.sase/plans/202611/publication_ledger_lookup_cost.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/publication_ledger_lookup_cost.md`

> # Stop paying a full protection-ledger read for every published file
> ## Problem
> The 2026-11-11 10:14 error digest on apollo reports two `agent_publication` errors
> (09:53 and 09:56 EST) for `gh_bobs-org__bob-cli`:
> `agent-hood publication did not complete within 120s; publication cleanup also failed: publication cleanup did not complete within 1s`.
> Evidence gathered while planning:
> - **Drain log.** On apollo, `~/.sase/logs/agent_publication_drains.jsonl` shows both
>   alarms fired while draining bob-cli's `research` hood, which has 937 runs.
>   - At 14:51Z, `inventory_build` took 16.9s and `hood_publish:research` took 75.3s. The
>     alarm fired during `commit`.

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase See the ~/.sase/axe/error_digests/digest_20261111_101419.txt file on the apollo
machine. Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. %m:@xlarge

## Response

Found a publication run in progress on apollo right now (2 min old, 52% CPU, ~400 MB). Next I'm finding the code behind the 120s hood-publication timeout.

The drain writes a per-stage timing log, so I'm pulling apollo's recent records for `bob-cli` to see which stage hits the timeout.

Locating the existing protection-ledger tests and call sites so the plan can point at them.

Enough context. Writing the plan as a tale: one medium-sized agent's worth of work. The notification-noise question goes in as an embedded reviewer decision.

Fixing the validation errors: adding `title` and `goal`, and trimming the decision text to the length limits.

The plan passes validation. Proposing it.

Yes, this is worth fixing, though nothing was lost this time. I've proposed a plan; it's waiting for your approval.

**What happened.** The two errors (09:53 and 09:56) were both the background `agent_publication` job hitting its 120s limit while publishing bob-cli's `research` hood on Apollo. The next run, 90 seconds later, published all eight waiting requests, and none were quarantined. The 1s "publication cleanup" failure is a side effect of the timeout, not a separate bug.

**Why it will keep happening.**
- **Drains are near the limit.** Publishing even one request rebuilds that whole hood (937 runs, about 6,400 files). On Apollo that already takes 35–100s, close to the 120s limit, so busy periods push it over. One of today's timeouts also lost a push race with another machine, which made it redo the expensive step. Athena's bob-cli drains take about 15s.
- **Timeouts can strand requests.** Each timeout uses one of a request's three attempts, after which it's quarantined. That is how 17 research requests on Apollo got stuck on Oct 27.

**The cause.** A read-only profile on Apollo shows most of the avoidable time in one function, `lookup_publication_content_record`. It runs once per published file, about 5,400 times per publish. Each call re-reads and fully re-checks the project's protection ledger file twice, even though that file holds only 16 records. That added roughly 13s per research-hood publish under the profiler.
- It costs nothing when a project has no ledger file. bob-cli's Apollo ledger was written recently, so the earlier speed-up for this hood (`sase-1qh.3`) didn't account for it.
- None of the open publication work (`sase-1qh`, `sase-1nf.10`, `sase-1nf.11`) covers it.

**The plan** (one agent, medium size):
1. **Cache the ledger.** Read and check it once, and only re-read it when the file changes. Requests for files that have no ledger entry (nearly all of them) are answered straight away; the existing Rust lookup handles the rest, so the protection rules don't change.
2. **Cache file-path checks.** Remember path segments that already passed validation; together these took about 4s.
3. **Tests and measurement.** Add tests that the cache picks up changes, plus a guard that the ledger is read at most once per hood build. Measure before and after on Athena's sase research hood. The coding agent won't update Apollo; it will hand you a command to re-run the profile there after you deploy.

**Decision for you:** should a timeout that the next run will retry stop showing up in the error digest? I defaulted to **keep**: once the slow lookup is gone, a timeout is a real warning sign and still uses up an attempt. Choosing **quiet** would log these as warnings and report only timeouts that quarantine or retire a request.

**Not in scope:** the ~640 older quarantined bob-cli requests (already owned by `sase-1nf.11` / `sase-1qh.7`), redoing work after a lost push race, and changing the 120s limit.
