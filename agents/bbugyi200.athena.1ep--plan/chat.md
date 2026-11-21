# Chat History - ace-run (1ep--plan)

- **TIMESTAMP:** 2026-11-20 18:02:40 EST
- **MODEL:** claude/opus
- **AGENT:** 1ep--plan

**Plan:** /home/bryan/.sase/plans/202611/hijack_working_tale_status.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/hijack_working_tale_status.md`

> # Fix `,k` hijack refusing running WORKING TALE / WORKING PLAN agents
> ## Problem
> In the Agents tab the user selected the running tale coder `bob-cli-o6.4.1.2`. Its row
> showed `WORKING TALE`, and the detail panel showed the session turns
> `--plan ✓ · --gate ✓ · --code ▶`. The user pressed `,k` (hijack). The TUI refused with
> this toast:
> ```
> ineligible_status: agent is not RUNNING, STARTING, or RETRYING · wait for the turn to run, then hijack
> ```
> The agent was actively running its code turn, so hijack should have been offered and

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase This should work. Can you help me fix this? See the
~/tmp/screencasts/20261120_175216.mp4 screencast for context. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

Tracking down the live `bob-cli-o6.4.1.2` artifacts on disk so I can compare its raw state against what the TUI showed.

I have the root cause and the fix design. Loading the planning skill to write and submit the plan.

Writing the plan file now.

Validation passes. Rerunning it once more to confirm the exit code, then proposing.

The plan is staged. Finishing the turn through `/sase_final`.

I've written a plan for the fix and submitted it for your review. No code has changed yet; the coding agent starts once you approve.

**What happened in the screencast:** you pressed `,k` on `bob-cli-o6.4.1.2` while it was running its code turn, and the TUI refused with `ineligible_status: agent is not RUNNING, STARTING, or RETRYING`.

**Root cause:** for display, the TUI relabels a running session member's status from `RUNNING` to `WORKING TALE`, `WORKING PLAN`, `EPIC APPROVED` or `PLAN COMMITTED`. The hijack check is computed from that same TUI row. `_status()` in `src/sase/agent/hijack/_facts_resolve.py` passes the row's status through as-is, so the Rust eligibility check (in sase-core) receives `"WORKING TALE"`. That check only accepts `RUNNING`, `STARTING` or `RETRYING`, so it refuses. The CLI `sase agent hijack NAME` path isn't affected because it reads the agent's real `RUNNING` status. Inside the Rust check, the workspace-claim test runs before the status test, so a refusal on status means status was the only thing blocking it.

**The fix (small tale, Python only, no sase-core change):**
- Add one set in `status_buckets.py` naming the four display labels the TUI paints over a running member.
- In `_status()`, treat one of those labels as `RUNNING` when the agent's process is alive. Rows whose process is dead behave exactly as they do today.
- The TUI then reaches the same decision as the CLI. That covers the `,k` keybinding, its footer hint and the `h` option in the kill dialog.

**Tests in the plan:**
- Unit tests for `_status()`.
- A test that a row labelled `WORKING TALE` or `WORKING PLAN` gets the same decision in the TUI as in the CLI, and that a dead row is still refused.
- A guard test that fails if the TUI ever adds a new label for running members without adding it to the set.

**One decision for you (`alias_scope`):** the default fixes all four labels. The other option fixes only `WORKING TALE` and `WORKING PLAN`, which would leave running epic-role and commit-role members still refused. I recommend the default because all four labels come from the same relabelling code.

I couldn't replay the exact failing state: the original session's files are gone, and a new `bob-cli-o6.4.1.2` started at 17:56, presumably your retry. The diagnosis comes from reading the code against the screencast and from a finished session of the same shape.
