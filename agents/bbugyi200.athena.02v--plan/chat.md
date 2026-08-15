# Chat History - ace-run (02v--plan)

- **TIMESTAMP:** 2026-08-15 17:37:21 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 02v--plan

**Plan:** /home/bryan/.sase/plans/202608/safe_bead_work_relaunch_2.md


## Prompt

#gh:gh_sase-org__sase Can you help me have the `sase bead work` command start only killing agents that are waiting/failed and assigned to beads corresponding with the current launch? Currently, we seem to kill running agents as well (so we lose work and waste tokens by launching another agent to work the same bead). Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/safe_bead_work_relaunch_2.md`

> # Plan: Preserve active bead workers during safe relaunch
> ## Problem and safety contract
> `sase bead work` renders deterministic phase, land, and task agent names with
> force-reuse directives. The current cleanup preview treats every live owner as `KILL`,
> and the preparation path wipes every planned name regardless of the owner's status. An
> epic retry can therefore terminate a phase or land agent that is already running, then
> launch another agent for the same bead. The standalone-task path has a separate
> live-assignee shortcut, so its behavior is inconsistent and cannot distinguish a
> genuinely running worker from one parked in `WAITING`.
> Use the bead association already carried by each rendered `%id(..., bead=...)` directive

*See full plan file for details.*

