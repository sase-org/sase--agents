# Chat History - ace-run (lw--plan)

- **TIMESTAMP:** 2026-07-27 06:50:28 EDT
- **MODEL:** claude/opus
- **AGENT:** lw--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-lw__plan-260727_063838.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-lw__code-260727_063838.md`

**Plan:** /home/bryan/.sase/plans/202607/defer_epic_completion_notification.md


## Prompt

#gh:gh_sase-org__sase Launching epics using detached background tasks is working great. There is only one problem: I receive a completion notification for the agent that proposed the epic plan before the task completes (see #sshot). I shouldn't receive that notification until the task completes and the agent's status is changed from `EPIC APPROVED` to `EPIC CREATED`. Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/defer_epic_completion_notification.md`

> # Defer the planner completion notification until the epic launch task settles
> ## Goal
> When a planner agent's epic plan is approved, the agent's "completed" notification must not fire until the detached
> `sase bead work` launch task has settled — i.e. until the planner row's status has moved from `EPIC APPROVED` to
> `EPIC CREATED`. Today the notification fires the moment the planner runner finalizes, while the launch is still running.
> ## Background
> Approving an epic plan runs two independent processes:
> 1. **Host side.** The gate side effect submits a detached background task
>    (`sase bead work <plan> --yes-to-all --artifacts-dir <dir> --cl-name <name>`) via `submit_epic_launch_task`
>    (`src/sase/bead/epic_launch.py:101`). The gate response is written _before_ side effects run

*See full plan file for details.*

