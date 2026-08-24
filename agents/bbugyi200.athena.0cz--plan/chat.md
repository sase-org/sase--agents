# Chat History - ace-run (0cz--plan)

- **TIMESTAMP:** 2026-08-24 17:31:25 EDT
- **MODEL:** claude/opus
- **AGENT:** 0cz--plan

**Plan:** /home/bryan/.sase/plans/202608/fork_failed_agents.md


## Prompt

#gh:gh_sase-org__sase Can you help me add support to the `#fork` xprompt for forking failed agents (e.g. via the `F` keymap on the "Agents" tab)? Make sure that it's clear that the agent failed and that the failure message is clearly rendered in the conversation transcript that is given to the agent when the `#fork` xprompt is used with a failed sase agent.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/fork_failed_agents.md`

> # Plan: Fork failed agents
> ## Symptom
> Forking a failed agent does not work today, at every layer:
> 1. **The TUI refuses.** `F` (`edit_hooks`) on a `FAILED` row notifies
>    `"Agent not finished yet"` and opens nothing — `resolve_agent_prompt_target_scope()`
>    in `src/sase/ace/tui/actions/agents/_wait_helpers.py:281`. `FAILED` is in
>    `DISMISSABLE_STATUSES`, so it skips the running-agent branch
>    (`_wait_helpers.py:250`), is not a plan handoff (`:260`), and is not in
>    `RESUMABLE_DONE_STATUSES` (`src/sase/ace/tui/models/agent_status.py:27`). The footer
>    never advertises the action either: the fork hint is explicitly suppressed for

*See full plan file for details.*

