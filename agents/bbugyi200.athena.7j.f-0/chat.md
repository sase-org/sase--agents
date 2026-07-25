# Chat History - ace-run (7j.f-0--plan)

- **TIMESTAMP:** 2026-07-13 07:42:12 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 7j.f-0--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-7j_f_0__plan-260713_072018.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260713_072018.md`

**Plan:** /home/bryan/.sase/plans/202607/chop_agent_drain_barriers.md


## Prompt

#gh:gh_sase-org__sase #fork:7j Can you now help me add the `%w(runners=0)` (see the sase-5u epic bead for context) directive to every agent prompt that belongs to an agent that is launched from a chop (for example, this directive should be added to the prompts used for the agents launched by the `toobig_split` chop, but look for all of the other chop agents that could possibly be launched and update them too)? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/chop_agent_drain_barriers.md`

> # Plan: Add `%w(runners=0)` Drain Barriers to Chop-Launched Agents
> ## Goal
> Ensure every root user agent launched by an Athena axe chop carries the exact `%w(runners=0)` directive, so chop work
> uses the `sase-5u` runner-slot admission system as a FIFO drain barrier: the agent starts only after earlier root agents
> have stopped, and later barrier agents cannot jump ahead of it.
> This is a prompt/configuration change, not a new admission-control feature. Preserve all existing chop cadences,
> ChangeSpec guards, project/workspace selection, names, `%group:chop` tagging, auto/proposal behavior, conditional launch
> logic, and multi-prompt dependency ordering.
> ## Launch-Surface Inventory and Scope
> The implementation must cover every current Athena path that can create a root user agent from a chop, including both

*See full plan file for details.*

