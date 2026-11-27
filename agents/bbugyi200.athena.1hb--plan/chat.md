# Chat History - ace-run (1hb--plan)

- **TIMESTAMP:** 2026-11-27 12:51:20 EST
- **MODEL:** claude/opus
- **AGENT:** 1hb--plan

**Plan:** /home/bryan/.sase/plans/202611/artifact_link_job_budgets.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/artifact_link_job_budgets.md`

> # Plan: Make the artifact-link chops honor their work budgets under host load
> ## Why (evidence from the apollo digest of 2026-11-27 10:33)
> The digest reported three SIGKILLs at the 300s axe timeout:
> `housekeeping/artifact_link_backfill` once (09:28–09:33) and
> `publication/agent_publication` twice in a row (09:35–09:40 and 09:40–09:45).
> - **apollo was overloaded at the time.** In 09:30–09:46 every lumberjack overran its
>   tick: `agent_waits` took up to 125s against a 2s interval, `hooks` took 30s+ against
>   5s, and `sidecar_sync` took 47s. The next `agent_publication` pass, at 09:45–09:48,
>   succeeded. Its bob-cli link drain alone took 145s, logged as
>   `publish=100.48s admission=39.29s beads=31.12s aggregate=27.96s`.

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. See the
~/.sase/axe/error_digests/digest_20261127_103358_806b1a2e.txt file on my apollo machine
for context. %m:@xlarge

## Response

Reading the axe logs on apollo to see why those two jobs hit the 300s timeout.

Tracing the two timeouts into the code: `artifact_link_backfill` was killed inside an unbudgeted `reconcile/aggregate` stage; now checking that stage and the publication job.

Still investigating: the backfill job routinely runs 260–270s of its 300s limit. Now checking the publication job's logs and earlier digests for a pattern.

Found the pattern: both jobs stall in bob-cli artifact-link work, and the publication job logs nothing until its first project finishes. Reading the publication job's deadline handling next.

Both jobs drain bob-cli's artifact-link outbox under a blocking per-project lock with no timeout. Checking whether other jobs on apollo were also slow in that 09:28–09:48 window.

Confirmed it's not a one-off: apollo was overloaded 09:30–09:46 (every lumberjack overran), and these two jobs had almost no headroom. Checking a few more deadline paths, then I'll write the plan.

Writing the plan now; checking existing tests for the reconcile-estimate gate and slow-pass progress so the plan can cite them.

Drafting the plan file now (one tale, medium size).

Plan drafted; validating it now.

Validation passed. Proposing the plan.

Yes, we can fix this and should. These timeouts are a symptom of a real gap: both jobs have 240s work budgets that the slow steps don't actually check. I've proposed a plan for the fix, and it's waiting for your approval.

**What happened**
- **apollo was overloaded from about 09:30 to 09:46.** Every scheduler routine ran far past its interval: `agent_waits` took up to 125s against a 2s interval, `hooks` took 30s+ against 5s, and `sidecar_sync` took 47s. The publication pass right after the two timeouts succeeded. Its bob-cli link drain alone took 145s.
- **`artifact_link_backfill` has almost no slack even on normal days.** Its last 10 runs took 150–270s of the 300s limit. On 11-22 the median was 101s. Nearly all of the time goes to bob-cli:
  - The sweep takes 90–195s for just 1–7 documents, against a 45s budget.
  - The full reconcile takes about 100s.
  - Each publish spends about 40s in the step that admits incoming link events.

**Why the 240s budgets didn't prevent the kills**
1. **Backfill: the first project always reconciles.** The code lets the first project of a tick skip the "does reconcile fit in the remaining time" check. In the killed run, bob-cli's sweep had used about 150s, leaving about 65s. Reconcile started anyway with a ~100s estimate and was killed mid-way; that step only checks the deadline between stores.
2. **Publication: it waits on a lock with no timeout.** Publishing artifact-link events takes bob-cli's event lock with a blocking wait, even when the caller passed a deadline. It also starts the ~40s admission step however little time is left.
3. **A kill wipes the backfill's learned state.** Its reconcile time estimates and its record of which project goes first are only saved at the end of the run. So the next hourly run repeats the same project with the same stale estimate.
4. **The publication timeouts left no output.** Progress lines are only printed after 60s, so a step that starts early and then hangs never logs its name.

**What the plan does** (a single plan, medium size)
- **Publication:** a background thread logs `still in <stage>` every 60s once a run passes 60s, so a killed run says where it was stuck. Fast runs stay quiet.
- **Publishing link events:** when there's a deadline, the lock wait is bounded and publishing won't start with less than 60s left. Either case defers the rows to the next run instead of blocking. Interactive callers keep the current behavior.
- **Backfill reconcile:** reconcile only starts when its estimate times 1.5 fits in the remaining time. The first project no longer gets an automatic pass. A project whose reconcile was deferred goes first next run and skips its sweep, so reconcile gets nearly the full budget.
- **Backfill state:** saved after each project, with a marker so a reconcile that was killed gets priority next run.
- **Diagnostics:** the backfill logs per-step sweep timings, to explain why a few documents take 90–195s.
- It also updates the config descriptions, the scheduler docs and the tests.

**Decision for you:** whether to also raise the `artifact_link_backfill` timeout from 5m to 10m as a safety net. I defaulted to keeping 5m, so a timeout still flags the next budget bug instead of hiding it.

**Not in this plan:** the underlying costs that make bob-cli slow:
- Its artifact-link outbox holds 8,341 rows (5.4 MB). Every drain spends about 9s just reading it.
- Every publish re-reads about 11.4k event files in the admission step.
- Reconcile's first big step can't be interrupted.

The plan lists these as follow-up tasks to file.
