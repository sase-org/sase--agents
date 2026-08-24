# Chat History - ace-run (0d5--plan)

- **TIMESTAMP:** 2026-08-24 19:21:17 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0d5--plan

**Plan:** /home/bryan/.sase/plans/202608/restore_chop_wait_chains.md


## Prompt

#gh:gh_sase-org__sase We've done some work on the `toobig_split` chop recently and everything is working almost perfectly now but there is one problem. Namely we seem to no longer be running the agents launched by these chops in a chain by having each one wait for the previous. Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/restore_chop_wait_chains.md`

> # Plan: Restore sequential AXE chop agent wait chains
> ## Problem and root cause
> The `toobig_split` chop is still emitting a correct linear `wait_on` chain, and the
> ordinary chop planner still renders each dependency as `%wait:<full-agent-name>`. The
> regression begins when an active `%if` routes the batch through typed admission:
> - the typed planner converts an in-batch named wait into a logical-unit edge;
> - that edge becomes satisfied when the predecessor reaches a terminal admission state,
>   including `launched` (the process was spawned), rather than when the agent finishes;
> - AXE dispatch rebuilds the agent prompt with `agent_unit_dispatch_prompt()`, which
>   intentionally omits typed waits because generic admission normally owns them.

*See full plan file for details.*

