# Chat History - ace-run (76--plan)

- **TIMESTAMP:** 2026-07-12 16:22:14 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 76--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-76__plan-260712_160859.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260712_160859.md`

**Plan:** /home/bryan/.sase/plans/202607/hold_failed_agent_workspaces.md


## Prompt

#gh:gh_sase-org__sase Currently when an agent fails, its workspace directory is still released. Often when an agent fails, it has not made any commits although it finished all of the work that it needed to successfully. The problem is that because we release the workspace, there's a strong possibility that another agent will start running and claim the workspace. The workspace preparation process will clear any file changes that the previous failed agent made, making it impossible to recover those changes or difficult at least. Can you help me stop releasing the workspace directory when agents fail and instead only release that workspace directory after the user dismisses that failed agent from the agents tab?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/hold_failed_agent_workspaces.md`

> # Hold Failed-Agent Workspaces Until Dismissal
> ## Problem
> When an axe agent fails, the runner still releases its workspace claim during shutdown. A failed agent frequently has
> finished (or nearly finished) its work without committing, so its uncommitted file changes live only in the workspace
> checkout. Because the claim is released immediately, the next agent launch can claim the same workspace number, and
> workspace preparation (`prepare_workspace` in `src/sase/axe/runner_utils.py:147`, via `run_sase_hg_clean`) discards the
> previous run's changes. Recovering that work is difficult (only the best-effort backup diff written by
> `run_sase_hg_clean` remains). The `revert_agent_workspace.py` module docstring already calls out this hazard: "that
> directory can be reclaimed by other agents and accumulate unrelated changes."
> **Goal:** when an agent fails, keep its workspace claim (a "workspace hold") so no other agent can claim/clear the

*See full plan file for details.*

