# Chat History - ace-run (19m--plan)

- **TIMESTAMP:** 2026-11-07 09:57:03 EST
- **MODEL:** claude/opus
- **AGENT:** 19m--plan

**Plan:** /home/bryan/.sase/plans/202611/artifact_link_backfill_timeouts.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/artifact_link_backfill_timeouts.md`

> # Make `artifact_link_backfill` finish reliably inside its budget
> ## Why this keeps happening
> Source: `research:202611/artifact_link_backfill_timeouts.md` (read it with
> `sase artifact read`). The hourly `housekeeping/artifact_link_backfill` chop has been
> SIGKILLed at its 300 s axe timeout 21 times since 2026-10-29. Every one of those runs
> died inside the **sase** outbox drain. Successful runs already take 240–262 s against a
> 240 s soft budget.
> Confirmed causes:
> 1. **The eligibility check is O(rows × evidence).** `_entry_is_eligible`
>    (`src/sase/sdd/_artifact_link_outbox_drain.py:383`) calls

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Can you help me fix the recurring artifact link backfill timeouts somehow? See the
artifact_link_backfill_timeouts.md file in the research sidecar repo for context. Think
hard about what the best, most reliable solution to this problem is.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

I'm reading the research report on the backfill timeouts. The research sidecar isn't cloned in this workspace yet, so I'm opening it first.

The report pins down the root cause well. Next I'm reading the drain and release-evidence code to design the fix.

I'm measuring how long the drain's other steps take (parsing the outbox, building the evidence index), since the fix depends on the cost of what's left.

Reconcile is also expensive: 37–59 s for sase and about 26 s for bob-cli. I'm checking whether part of that is the same outbox being re-parsed.

I'm counting how many times one reconcile pass re-reads the outbox. The plan's scope depends on whether reconcile time grows with queue size.

Two things still to check before writing the plan: the artifacts reference memory (it covers linking and retention), and the existing drain tests the plan will extend.

Writing the plan file now.

The plan passes validation. Submitting it now.

I've written a plan to fix the backfill timeouts and submitted it for your approval; nothing has been implemented yet. It's a single-agent (medium tale) plan. The plan file passed validation, and approving it starts the coder.

**Root cause.** The research report is right. The drain re-reads the whole release-evidence file once per queued row: 12,889 rows × 4,172 lines, about 108 s, with zero matches. It checks the 240 s budget only once, before its slow loops. My own read-only measurements on athena found more:
- **Outbox parsed three times:** each full parse of the sase outbox takes 4.7 s, and every drain does three. The last one rewrites the whole file while holding the exclusive lock, even when nothing changed.
- **Same evidence check in one pass:** 47 ms.
- **Reconcile pays for the queue too:** its core step, the aggregate preview, takes 59 s for sase and reads the outbox 4 times. About half that time is the outbox's pending rows.
- **The next risk after the fix:** once the drain is fast, that 59 s reconcile step becomes the long step that can't be interrupted. The chop only refuses to start reconcile after the deadline has already passed, so a slow tick could still run it into the 300 s kill. The plan closes this as well.

**What the plan does:**
1. **Faster drain:** load release evidence into one set index per drain and read the outbox once. Skip the rewrite when nothing settled, which also stops blocking agents' appends for seconds.
2. **Real deadline:** check it inside the drain loops, and require 60 s of headroom before building the agent catalog. A slow tick becomes a logged deferral instead of a SIGKILL.
3. **Rarer catalog builds:** build the catalog at most once per run, and only when some row is old enough to drop. Stale rows are dropped at most once a day per project.
4. **Reconcile guard:** don't start reconcile unless the remaining budget covers its last measured duration. A project whose work was deferred goes first on the next tick, so sase's reconcile stops being skipped.
5. **Bug fix:** parked rows are supposed to be rechecked once a day but are rechecked every hour. The fix persists their recheck times safely when another drain runs at the same time.
6. **Fewer reads elsewhere:** the pending-link view reads the outbox once instead of twice, which also helps interactive link reads.
7. **Logs:** each drain logs per-phase timings, so the next regression shows up in the logs.

None of this changes which rows publish or stay queued. The only behavior difference is that a stale-row drop can happen up to 24 h later than before.

I expect a run to drop from about 250 s to about 110–130 s, with sase's reconcile running every tick. sase commit finalization should also get about 10 s faster, since it uses the same drain.

**Decision for you:**
- **`keep` (default):** dead read rows (from agents that never commit) still leave the queue only 90 days after their agent finishes.
- **`days14`:** they leave after 14 days instead. That shrinks the queue about 6× and speeds up reconcile, but read-only agents' read links disappear from your local view after two weeks.

I chose `keep` because the other fixes already keep the job within budget without changing what you see.

After it lands, the hourly job keeps running the old code until you reinstall sase, because agents aren't allowed to do global installs. After that, look for the new `drain phases:` lines in the chop logs.
