# Chat History - ace-run (f0--plan)

- **TIMESTAMP:** 2026-07-19 10:53:32 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** f0--plan

**Plan:** /home/bryan/.sase/plans/202607/tribe_agent_count_projection.md


## Prompt

#gh:gh_sase-org__sase The `TRIBE MEMBERS` section is still showing invalid agent status counts and invalid agent counts (ex: there are 10 agents in the agent tribe selected in #sshot, not 12--i.e. 2 top-level agents and 4 agent families each containing 2 agents == 10 total agents, not 12 total agents). Can you help me fix these issues and any others that you see in the screenshot file I provided? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/tribe_agent_count_projection.md`

> # Plan: Concrete-agent counting and settled family-member status projection
> ## Problem
> The Agents-tab tribe detail document (whole-panel focus) reports wrong agent counts and wrong agent status counts.
> Reference scenario (observed live): an untagged tribe containing 4 sequential agent families (each a `--plan` planner +
> `--code` coder) and 2 single-agent workflow units — 10 concrete agents total. The TUI currently shows:
> 1. **`Composition: … 12 agents` instead of 10.** `tribe_unit_real_rows()`
>    (`src/sase/ace/tui/models/agent_tribe_summary.py`) returns, for a non-container unit, the workflow aggregate root
>    **plus** all descendant step rows. A single-agent workflow (root + `main` agent step) therefore counts as 2 agents,
>    and `agent_count = len(real_rows)` inherits the double count.
> 2. **`… 10 nested` instead of 8.** `nested_count = sum(len(unit.children))` counts workflow step rows as nested agents.

*See full plan file for details.*

