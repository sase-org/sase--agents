# Chat History - ace-run (r0--plan)

- **TIMESTAMP:** 2026-08-01 08:05:22 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** r0--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-r0__plan-260801_080043.md`
- 2. --code — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-r0__code-260801_080043.md`

**Plan:** /home/bryan/.sase/plans/202608/default_epic_agent_priority.md


## Prompt

#gh:gh_sase-org__sase Can you help me stop adding `%wait(priority=15)` to epic phase / lander agent prompts? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/default_epic_agent_priority.md`

> # Plan: Use Default Runner Priority for Epic Agents
> ## Current behavior and scope
> `sase bead work` renders each epic phase and the final lander as separate prompt segments. Phase segments already rely
> only on their authored agent/bead dependency waits: the bundled `bd/work_phase_bead` xprompt does not set a runner-slot
> priority. The bundled `bd/land_epic` xprompt still contributes `%wait(priority=15)` when its segment is expanded, so the
> lander is assigned an explicit, worse-than-default queue priority in addition to the genuine waits that the epic
> renderer adds for every phase agent and phase bead.
> Remove that lander-only priority override so both kinds of epic worker use the normal implicit priority (`10`) when they
> become eligible. Do not remove or weaken the phase DAG waits, the lander's waits on all launched phases and phase beads,
> runner-slot admission itself, or support for user/plugin xprompt overrides. Keep the separate `bd/work_task` priority

*See full plan file for details.*

