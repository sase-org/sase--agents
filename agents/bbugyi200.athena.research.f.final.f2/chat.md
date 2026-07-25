# Chat History - ace-run (research.f.final.f2--plan)

- **TIMESTAMP:** 2026-07-16 18:55:56 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.f.final.f2--plan

**Plan:** /home/bryan/.sase/plans/202607/xprompt_agent_families.md


## Prompt

#gh:gh_sase-org__sase #fork:research.f.final The research created by the previous agent (review it since I'm sure at least some parts are useful) seemed to be too focused on the two use cases that I provided. This feature (xprompt agent families) needs to be incredibly generic and definable only via xprompt syntax. Can you help me design and implement a solution for this? This should be an MVP but it should also be ambitious (but highly practical, intuitive, and every feature should solve a real user problem or objectively improve the user's experience), address all edge cases surfaced by the agent research referenced above, and reliable (do not break anything). Also, although you should not overfit your solution to the two use cases I gave in the previous chat, you should implement those two use cases. 

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/xprompt_agent_families.md`

> # Plan: xprompt agent families via a `%family` directive
> ## Context
> Today three uncoordinated grouping mechanisms exist: plan-chain families (`foo--code` +
> `agent_family`/`parent_timestamp` metadata, serial handoff semantics), hoods (`foo.bar`, navigation only), and tags
> (`%group`, a side panel per tag). Parallel agents launched from one multi-prompt (epic phase workers + the land agent;
> the chezmoi research swarm) have no way to group under one root row, so they sprawl across the Agents tab and their
> metadata is scattered.
> Prior research (`sase--research` sidecar,
> `202607/parallel_family_children_consolidated/parallel_family_children_consolidated.md`) established that parallel
> execution itself already works — both use cases spawn all agents up front and self-gate via `%wait`. The real work is

*See full plan file for details.*

