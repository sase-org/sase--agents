# Chat History - ace-run (19m--code)

- **TIMESTAMP:** 2026-11-07 11:12:52 EST
- **MODEL:** claude/opus
- **AGENT:** 19m--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202611/artifact_link_backfill_timeouts.md

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false
Reviewer decisions for this plan (final · reviewer via ACE):
- outbox_retention = keep (planner default: keep). Implement the "outbox_retention = keep" branch; ignore "outbox_retention = days14". Context: "Should a terminal agent's never-publishable outbox rows leave the live queue 14 days after it finishes, instead of 90?".
Implement only the branches selected above.
%macros_enabled:true


## Response

I've read the approved plan (keep branch selected). Next I'm reading the drain, evidence, outbox I/O, and chop modules before I implement.

Context gathered. Now checking the line-count limits and existing tests before writing code.

Still reading tests; next I'll write the evidence index and outbox I/O changes.

Now writing the release-evidence index.

Now the outbox I/O: one-pass queue read and single-read pending snapshot.

Now the parked-ledger update helper.

Now the drain support module (lazy catalog provider + deadline helper).

Now rewriting the drain flow itself.

Now the chop's schedule-state module.

Now wiring the chop: shared catalog, daily stale drop, reconcile headroom, deferred-first cursor, phase log.

Core code is in place. Updating the existing tests that patched the old seams, then running the affected suites.

All 58 existing tests in the affected suites pass. Now writing new tests, starting with a look at the event-store constructor.

Now the release-evidence index tests.

Now the drain scaling/catalog/deadline/rewrite test module.

All 8 new drain tests pass. Now the parked-ledger tests.

Now the single-read event-store test.

Now chop tests: schedule rules, shared provider, reconcile headroom, deferred-first cursor, phase log.

All 22 chop tests pass. Now the docs, default config description, and changelog gate.

The changelog is generated from commit messages, so CHANGELOG.md stays untouched. Updating the docs and the chop description now.

Formatting applied. Now the read-only timing probe against the real sase queue (no publish, no rewrite).

Probe on the live sase queue (12,920 rows): read 3.75 s, evidence 0.042 s, eligibility 0.014 s, which matches the plan's targets. Now running `sase tool run check`.

Symvision flagged two public symbols that lost their last non-test consumer: `ArtifactLinkParkedEntry` and `artifact_link_run_has_release_evidence`. Checking for consumers elsewhere before deciding.

Now converting the release-evidence tests to the index.

All 41 pass. Re-running format and then the full check.

No duplicate in the search or the one-week sweep. Checking in-progress epics for a causal link.

Those epics overlap only by topic; none caused the double read. Collecting a concrete location for the bug report.

Root cause confirmed: `preview_aggregate` builds a full event snapshot, then `_load_store_truth_rows` builds an identical second one. Filing it as a medium bug.

Follow-up filed as `sase-1rt` and marked ready. Doing a final diff review before declaring.

Implementation and verification are complete. Submitting the final declaration.

I've implemented the approved plan with the `outbox_retention = keep` branch, so retention config is unchanged. `sase tool run check` passed every stage, including the scoped test lane (about 25 minutes in total). The host commits the work after this turn.

**Drain**
- **Release evidence:** loaded once per drain into a set of validated `(run_id, agent_id)` pairs. Rows no longer each trigger a read of the evidence file.
- **Outbox read:** one parse per drain instead of three.
- **Deadline:** checked inside the eligibility loop. If time runs out before anything is published, the drain returns a deferred report and nothing has changed on disk.
- **Agent catalog:** built only when some never-publishable row is older than the retention cutoff, and never with less than 60 s of budget left. One build is shared by every project in a run, and a failed build drops nothing.
- **Rewrite:** a drain that settles nothing no longer rewrites and fsyncs the whole outbox. A queue with duplicate ids is still compacted.
- **Parked-entry bug fixed:** when parked entries were rechecked, the recheck time was never saved, so the 24 h throttle never worked. It's now saved through a locked re-read, which also keeps any entry another drain parks at the same time.
- **Event snapshots:** the pending outbox is read once per snapshot instead of twice.

**Chop**
- The stale terminal drop runs at most once per 24 h per project. This state is stored in a new `artifact_link_backfill_schedule.json`.
- Reconcile starts only if its learned duration estimate fits in the time left. The first project of each tick always runs it.
- A project whose drain or reconcile was deferred for budget goes first on the next tick.
- Each drain logs one `drain phases:` line with per-phase timings, and there is a new `stale_checked_projects` counter.

**Measured on the live sase queue** (12,920 rows, read-only): outbox read 3.75 s, evidence 0.042 s, eligibility 0.014 s. The plan expected about 5 s, under 0.1 s and under 0.1 s.

**Departures from the plan:**
- **Deleted `artifact_link_run_has_release_evidence`** instead of reimplementing it. After the change only tests used it, which fails the unused-symbol lint gate (`symvision`). Its tests now check the new index, so there is still a single parsing path. `ArtifactLinkParkedEntry` became private for the same reason.
- **A failed catalog build also puts that project first on the next tick.** I couldn't cheaply tell it apart from a budget deferral. If the catalog is persistently broken, that project will always lead the rotation.

I added tests for each part of the plan (new files `tests/sdd/test_artifact_link_outbox_drain_scaling.py` and `tests/test_axe_chop_artifact_link_backfill_cadence.py`) and updated the docs pages and the chop description in `src/sase/default_config.yml`.

I filed the plan's out-of-scope follow-up as **`sase-1rt`**, marked ready. `preview_aggregate` builds the whole event snapshot twice, so each reconcile preview still reads the outbox and the stored link events twice.

**What you need to do:** the hourly job runs from the globally installed sase, so the fix takes effect only after you reinstall. Then look for the new `drain phases:` lines in the chop log, and check that `artifact_link_backfill` timeouts no longer appear in the next error digests.
