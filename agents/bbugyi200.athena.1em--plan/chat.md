# Chat History - ace-run (1em--plan)

- **TIMESTAMP:** 2026-11-20 11:19:34 EST
- **MODEL:** claude/opus
- **AGENT:** 1em--plan

**Plan:** /home/bryan/.sase/plans/202611/clan_monitor_settle_failed_flicker.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/clan_monitor_settle_failed_flicker.md`

> # Stop clan rows flashing FAILED while a failed monitor is still settling
> ## Problem
> Agent clan nodes on the Agents tab sometimes read `FAILED` (with an `F1` chip, a `✗` on
> the member in the CLAN waves strip and jump bar, a `✗1` wait-dependency count on the
> `.land` member, the clan filed under the `Failed` status group, and `1 failed` in the
> tab header) for several seconds up to about a minute, then go back to `RUNNING`. The
> member that causes it renders as `(RUNNING)` in the same frame. The aggregates disagree
> with the row because the member's `status` is `RUNNING` while its `status_bucket` is
> `Failed`.
> ## Root cause (verified)

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Sometimes agent clan nodes will show as `FAILED` on the "Agents" tab for a few
seconds before going back to `RUNNING`. This is misleading to the user. See the
~/tmp/screenshots/20261120_103033.png screenshot for an example. Can you help me
diagnose the root cause of this issue and fix it?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge %q:5

## Response

I'm reading the monitor supervisor's finish path to see what order it writes `monitor_state=failed`, `monitor_next_action`, and `monitor_followup_outcome`.

Nearly done exploring. Confirming the three loader paths that call `apply_monitor_meta` so the plan names exactly where `monitor_settled` must be plumbed.

Writing the tale plan now.

Validation passed. Cleaning up my scratch repro dir, then proposing.

The clan rows briefly show `FAILED` because, for a short window after a `just check` monitor fails, the Agents tab counts that failure against the whole session before the follow-up agent has been launched. I traced it with the live artifacts from your screenshot and reproduced it in memory. The fix plan has passed validation and is staged for your approval; no source files are changed yet.

**What happened in the screenshot (member `sase-1tz.3.1.5`)**
- About 10:29:52: its `just check` monitor exited 1. The monitor's supervisor immediately writes `monitor_state: "failed"` to the monitor's metadata. It deliberately leaves out the stop time and the "settled" flag, and there is no `done.json` yet.
- It then decides on and launches the follow-up agent. That agent was admitted at 10:30:44, and only after it started was the monitor marked settled with outcome `launched`.
- Your screenshot (10:30:33) falls inside that gap. Here it lasted about 50 seconds; usually it's a few seconds.

**Why the TUI shows FAILED in that gap**
- The monitor row gets bucket `Failed` from its state, but its label stays the raw `RUNNING`.
- The TUI treats any finished monitor state as settled. A settled failed monitor with no recorded follow-up counts as a real failure.
- The session row copies that monitor, so `.5` ends up labelled `RUNNING` but counted as `Failed`. That is the inconsistency in your screenshot.
- Everything that counts by bucket then reports a failure: the clan's `FAILED [.. F1 ..]`, the `.5 ✗` in the waves strip and jump bar, the `✗1` on `.land`, the Failed group, and `1 failed` in the tab header.
- This contradicts the documented rule in `docs/reference/automation/monitors.md`: a monitor is terminal only once it has settled and its follow-up has launched or been recorded. The earlier sase-19o fix only covered what happens after the follow-up outcome is written.

**Planned fix (TUI only; no `sase-core` change needed)**
- A failed monitor counts as "still settling" while three things hold: its state is finished, it has no stop time yet, and its supervisor process is confirmed alive (pid plus identity check).
- While settling, the session and clan read `Running`. The monitor's own row still shows `Failed`, which is accurate about the command itself.
- The liveness check matters: the existing dead-supervisor cleanup only handles monitors still marked `running`. Without the check, a supervisor that crashed mid-settle would look `Running` forever. With it, a dead or unknown supervisor keeps today's `Failed`, so a stuck session still shows up.
- The plan adds unit tests for the new rule, a regression test that recreates your screenshot plus a version with a dead supervisor, and liveness tests in the loader. It also adds one sentence to the monitors docs.

**Out of scope**
- The monitor's own row will still read `RUNNING ✗ 1` during the gap.
- Rows from other machines can't be checked for liveness locally, so they keep the current behaviour.
- There may be a separate backend gap: a supervisor that dies mid-settle never seems to get cleaned up. The plan has the implementing agent confirm it and file a task rather than fix it here.
