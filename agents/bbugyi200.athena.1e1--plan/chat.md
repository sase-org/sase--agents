# Chat History - ace-run (1e1--plan)

- **TIMESTAMP:** 2026-11-18 11:22:23 EST
- **MODEL:** claude/opus
- **AGENT:** 1e1--plan

**Plan:** /home/bryan/.sase/plans/202611/tui_update_waits_for_epic_launch.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/tui_update_waits_for_epic_launch.md`

> # Plan: TUI updates wait for an in-flight epic launch instead of failing
> ## Problem
> Every SASE TUI update entry point refuses to run while a `sase bead work` holds the
> code-swap reader lock. That includes the leader `,U` Update panel, `,E` Update
> everything, and the Admin Center Updates tab. Approved epics launch through exactly that
> kind of reader: the guarded epic-launch bootstrap hands its shared lock to
> `sase bead work <plan.md> --yes-to-all ...`, which holds it for the whole launch
> orchestration. So pressing `,U` mid-launch produces an error toast:
> ```text
> A sase bead work is running against this checkout (sase bead work (pid 21121); running

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Sase TUI updates fail currently if an epic is mid-launch. Can you help me make
these updates (triggered via the `,U` keymap on the "Agents" tab, for example) wait for
the epic to finish launching instead (like we do for procs)? See the
~/tmp/screencasts/20261118_110822.mp4 screencast for context.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

Screencast shows a toast: "A sase bead work is running against this checkout … Re-run the update after it finishes." Now tracing that guard in the code.

Checking the screencast frames around the Enter keypress to see which update flow triggered the toast.

Tracing the TUI update-proc submission path to find the existing "wait for procs" behavior the user referenced.

Still exploring: checking how long `sase bead work` holds the blocking reader lock during an epic launch.

Checking real epic-launch durations from proc records to pick a sensible wait timeout.

Checking whether TUI session-worker procs can be cancelled (matters for a long wait).

Reading the required TUI and ACE reference memory before finalizing the design.

Checking the `toobig` line limits, since `code_swap_lock.py` is already 562 lines.

Verifying Textual thread workers are daemon threads (a waiting update thread must not hang TUI exit/restart).

I have the full picture. Writing the plan now.

Validation passes. Proposing the plan.

I wrote a plan for this, and `sase plan propose` has staged it for your approval. It's a single-agent plan of medium size, and it passed `sase plan validate`. No code has changed yet.

**What the screencast shows:** pressing `,U` mid-launch gives the toast "A sase bead work is running against this checkout (…record_walk_ring.md…). Re-run the update after it finishes." An approved epic launches as a `sase bead work` that holds a shared lock on the source tree for the whole launch. Updates refuse to run while anyone holds it, in two places:
- **Before confirming:** `dev_update_blocking_reason` blocks the update for `,U`, `,E` and the Admin Center Updates tab.
- **While running:** `execute_dev_update` makes one attempt at the exclusive lock and gives up with "deferred:" if it's taken.

**What the plan changes:**
1. **The update waits for the lock.** It retries once a second, holds nothing while waiting, and stops after 30 minutes. It first waits for the launch to finish, then fetches, so it picks up anything that landed in the meantime. If it had to wait for the lock itself, it re-checks the checkouts before swapping. On timeout it reports "deferred:" with nothing changed.
2. **Every TUI update path uses the wait.** The update runs in its existing background proc, so the UI doesn't stall, and the proc's phase shows `Waiting for <holder> to finish`. The CLI `sase update` doesn't use the wait, so it still fails fast exactly as today.
3. **A running launch no longer blocks the update.** The confirm screen says the update will wait and names what it's waiting for. After you confirm, a toast says the update is queued, which also covers `,E` since it has no confirm screen.
4. **Docs and tests.** The plan updates the code-swap lock section of `docs/reference/integrations/plugins-update.md`, which currently says the writer must never wait. It adds new test modules for the lock wait, the update flow and the TUI notice.

**Choices I made:**
- **30-minute timeout.** A waiting update can't be cancelled from the TUI, so it needs a limit. Quitting or restarting ACE still drops it cleanly.
- **No new progress-gear state.** The waiting update shows up as a normal running update with the wait as its phase.

Approve, reject or give feedback in the plan approval prompt.
