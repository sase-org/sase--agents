# Chat History - ace-run (018--plan)

- **TIMESTAMP:** 2026-08-14 11:26:05 EDT
- **MODEL:** claude/opus
- **AGENT:** 018--plan

**Plan:** /home/bryan/.sase/plans/202608/monitor_followup_prompt_escaping.md


## Prompt

#gh:gh_sase-org__sase Can you help me make sure that, when a sase monitor finishes and a next action was specified, that we escape the entire prompt (as much of it as we can without breaking things at least) of the command using the `%xprompts_enabled` directive? This will prevent agents from accidently introducing validation errors (e.g. by not escaping directive names, for example). If not, use your /sase_plan skill to plan the appropriate changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/monitor_followup_prompt_escaping.md`

> # Escape the monitor follow-up prompt body with `%xprompts_enabled`
> ## Problem
> When a monitor with `--next` reaches a terminal state,
> `sase.monitor.followup_prompt.compose_followup_prompt` composes the follow-up agent's
> initial prompt and `sase.monitor.followup.launch_followup_agent` hands it to
> `spawn_agent_subprocess`. That prompt goes through the same directive/xprompt pipeline
> as any user-typed prompt, and the follow-up agent's own runner boot calls
> `extract_prompt_directives` on it (`src/sase/axe/run_agent_directives.py:126`) with no
> `try`/`except` around it.
> Today only three fields are protected: `Command` and `Directory` are rendered as real

*See full plan file for details.*

