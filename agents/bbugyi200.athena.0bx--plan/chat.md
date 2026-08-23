# Chat History - ace-run (0bx--plan)

- **TIMESTAMP:** 2026-08-23 14:00:14 EDT
- **MODEL:** claude/opus
- **AGENT:** 0bx--plan

**Plan:** /home/bryan/.sase/plans/202608/proc_shell_selection_jump.md


## Prompt

#gh:gh_sase-org__sase There seems to be some kind of bug with stand-alone procs (launched with the `%proc` directive). Namely when I have one focused in the agents tab and the TUI is auto-refreshed, the selected node is changed (I think its the `0bh` or `0bd` sase agent node that gets selected). Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/proc_shell_selection_jump.md`

> # Plan: Keep a focused stand-alone proc shell selected across Agents-tab refreshes
> ## Symptom
> Focus a stand-alone `%proc` shell row (`AgentType.PROC_SHELL`) in the Agents tab and
> wait for the TUI auto-refresh. The cursor silently jumps off the proc row onto a
> neighboring sase agent node. The proc row itself is still there afterwards — only the
> selection moved.
> ## Root cause (verified)
> The disk loader never produces proc-shell rows. They exist only as a presentation
> projection of the proc observer, built by `proc_shell_agents_from_observed` and merged
> into the roster by `_sync_proc_shell_agents_from_projection`

*See full plan file for details.*

