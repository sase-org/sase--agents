# Chat History - ace-run (19j--plan)

- **TIMESTAMP:** 2026-11-07 09:26:12 EST
- **MODEL:** claude/opus
- **AGENT:** 19j--plan

**Plan:** /home/bryan/.sase/plans/202611/monitor_receiver_launch_receipt.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/monitor_receiver_launch_receipt.md`

> # Plan: Stop fencing booting monitor follow-ups to `needs_attention`
> ## Problem
> Monitor follow-up agents intermittently die on their first step with:
> ```text
> WorkflowExecutionError: Step 'main' failed: Error: conflict: cannot transition terminal
> delivery from needs_attention to acknowledged
> ```
> The most recent victim was phase bead `sase-1rq.4.1.2`. Its planner staged an unfiltered
> `macos-ci-check` monitor (`vkv33r475zps`). The monitor finished at 13:39:44Z with the
> expected red result. Settlement spawned the follow-up `sase-1rq.4.1.2--1` at 08:40:40

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase The `sase-1rq.4.1.2` sase agent just failed. Is there something that we can/should fix here? If so, use your /sase_plan skill to plan the appropriate changes. Think hard about this. %m:@xlarge

## Response

Looking into it: a fresh `sase-1rq.4.1.2` relaunch started at 09:04. I'm tracing the earlier run that failed (a plan step, then a `--mon` monitor around 08:22–08:39).

Narrowed to a few writers that can set `needs_attention`. Now checking whether host completion and the ordinary follow-up share one delivery key and overwrite each other.

Every on-disk trace of those runs has been purged, so I'll pin down the race from the code. Quickly searching logs and proc stores for the monitor id first.

The proc runtime kept the monitor's `settlement.json` and supervisor log. Reading both for the follow-up identity and timestamps.

That digest is unrelated (an `artifact_link_backfill` timeout). Searching earlier workflow logs to see whether this same delivery-conflict error has hit other runs.

All on-disk evidence for the earlier runs is gone too. Now checking what a receiver queued for a runner slot looks like to the liveness probe, mainly whether its process stays alive while it waits.

Two surprises in the probe. The queued `sase-1rq.4.1.2` relaunch can't be resolved at all (`ctx None`). And the RUNNING follow-up `sase-1rq.1--1` reads as **not alive**. Checking why.

Only today's failure is still in the notification inbox. Next I'll read the spawn path to see exactly what the parent writes before the child boots.

Root cause is clear. Before planning I'm checking whether the spawner already knows the child's pid and artifacts dir. That would allow a precise receiver proof instead of a time-based grace window.

The full probe timed out: each lookup rehydrates about 19k records. Rewriting it to load the project records once and check every live agent in memory.

Root cause confirmed. Loading the planning skill to write up the fix.

Checking for an existing bead that already tracks this failure.

No open bead tracks this. The reconciler came from closed bead `sase-zl.13.6`. Finding the existing tests so the plan can point the coder at them.

No other readers, so a `continuation/delivery/receivers/` subdirectory is safe. Last check: whether any docs describe receiver proofs and would need updating.

The validator needs `title` and `goal`. Adding them and switching the heading to the `# Plan:` form.

Validation passed. Submitting the plan.

The proposal is staged. Finishing the turn through `/sase_final`.

## What failed

`sase-1rq.4.1.2` didn't fail on its own work. The follow-up turn `sase-1rq.4.1.2--1` crashed before the model ever ran:

```
conflict: cannot transition terminal delivery from needs_attention to acknowledged
```

The bead work itself probably succeeded. The monitor result (`macos-ci-check` run `42376806344`) lists 12 failing tests, and `testMotionsLeaveTextAndUndoUntouched` isn't one of them. The follow-up just never got to judge that result and close the bead.

## Root cause: a race in SASE

1. When a monitor finishes, it marks the follow-up's delivery record `dispatching` and spawns the follow-up.
2. The follow-up only claims the delivery (`acknowledged`) when it reaches its first model call. Before that it has to boot (~16s under load) and wait for a runner slot (this one waited ~3.5 minutes; all 8 were busy).
3. Meanwhile, many commands in any agent call `list_monitors()`: `sase monitor list/show/stop`, `sase tool` stop/outputs, and agent kill/dismiss. That function checks every finished monitor whose delivery is still `dispatching` (`reconcile_terminal_deliveries` → `resume_monitor`).
4. That check decides whether the follow-up is alive by looking it up by name. A follow-up only records its name once it boots, so during that window the lookup finds nothing. The launch is already recorded, though, so a live follow-up looks crashed. The record is marked `needs_attention`, a terminal state.
5. When the follow-up finally reaches its model call, its claim is refused and it crashes. Nothing restarts it, so the bead is stranded.

The process that spawns the follow-up already knows its real pid and artifacts dir, but `record_followup_launched` throws them away.

This has happened before: the same error is in five workflow logs (Oct 9, Oct 20, Oct 23, Nov 1, today), and every time the follow-up had waited minutes before failing. The failed run's files were purged when it was dismissed, so I couldn't read the record itself. The conclusion rests on the code, those logs, and a read-only check of the agents running now.

## Plan (staged for your approval)

Tale, `medium`, Python only:
1. **Record a launch receipt at spawn time.** A new `src/sase/monitor/delivery_receipts.py` saves the follow-up's pid and process identity, before the launch is marked as recorded.
2. **Use the receipt in the liveness check** (`collect_receiver_proofs`). A follow-up that is still booting or queued counts as alive. One whose process is actually gone is still marked `needs_attention`, so the safety check keeps working.
3. **Record an accurate reason.** Today it always says "superseded by manual resume", even when no manual resume happened.
4. **Make the follow-up's error say what happened:** the monitor id, the state and reason, and how to inspect it with `sase monitor show`.
5. **Tests and docs:** a regression test for this exact race, a test that a dead follow-up is still blocked, a test that the receipt is written in the right order, and an update to `docs/reference/automation/monitor-operations.md`.

The decision logic in sase-core doesn't change, so no pin bump is needed.

## Until the fix lands

The relaunched `sase-1rq.4.1.2` has already started a new monitor, `sase-1rq.4.1.2--mon`, which is now watching CI. Its follow-up can hit the same race. If the bead strands again, relaunch it with `sase bead work sase-1rq.4.1 --yes-to-all`.
