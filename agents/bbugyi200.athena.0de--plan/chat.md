# Chat History - ace-run (0de--plan)

- **TIMESTAMP:** 2026-08-25 08:36:19 EDT
- **MODEL:** claude/opus
- **AGENT:** 0de--plan

**Plan:** /home/bryan/.sase/plans/202608/kill_and_edit_prompt_latency.md


## Prompt

#gh:gh_sase-org__sase We recently fixed the ability to kill and edit a sase agent from the agents tab using the `,x` keymap. This fix worked and needs to be preserved but as an effect we've seemed to have added a noticable delay between when the agent is dismissed/killed and when thet agent's prompt is loaded in the prompt input widget. Can you help me fix this (the prompt should load into the prompt input widget as quickly as possible while maintaining reliability)?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/kill_and_edit_prompt_latency.md`

> # Plan: Make `,x` load the relaunch prompt immediately
> ## Problem
> Pressing `,x` (kill & edit) on the Agents tab now has a noticeable pause between the
> agent disappearing from the list and its prompt appearing in the prompt input widget.
> The pause was introduced deliberately by `1b2381366` ("fix(ace): make family-root
> kill-and-edit name reuse deterministic"), which changed both `,x` branches to defer
> mounting the prompt bar/stack until the kill/dismiss persistence proc settles:
> - `src/sase/ace/tui/actions/agent_workflow/_entry_relaunch.py:271`
>   (`_finish_kill_and_edit_agent`) passes `on_settled=mount_prompt_bar` to
>   `_dismiss_done_agent` / `_do_kill_agent`.

*See full plan file for details.*

