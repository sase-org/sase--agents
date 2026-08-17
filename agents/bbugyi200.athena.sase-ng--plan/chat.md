# Chat History - ace-run (sase-ng--plan)

- **TIMESTAMP:** 2026-08-17 15:16:15 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ng--plan

**Plan:** /home/bryan/.sase/plans/202608/retire_dead_ace_launch_cleanup_bodies.md


## Prompt

#gh:gh_sase-org__sase
%id(sase-ng, bead=sase-ng)
%m:@large
Can you complete the work for task bead sase-ng by running the `sase bead show sase-ng` command,
reviewing the command's output, doing the work, and then closing the bead by running the
`sase bead close sase-ng --note "<what you verified>"` command?

If you discover genuinely distinct follow-up work that is outside this task, use `/sase_new_task` with details
identifying the current bead; it will corroborate a duplicate, attach a causally related active-epic issue, or
create a sized task as appropriate.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/retire_dead_ace_launch_cleanup_bodies.md`

> # Plan: Retire dead ACE in-process launch and cleanup bodies
> ## Problem
> Commit `0835b38d2` migrated ACE's launch and cleanup producers to durable argv
> submission. Both submission helpers still accept a `proc_callable` and both delete it
> before submitting:
> - `LaunchProcMixin._submit_launch_proc()` — `del proc_callable`, then
>   `submit_agent_launch()` (`src/sase/ace/tui/actions/agent_workflow/_launch_procs.py`).
> - `CleanupProcMixin._submit_cleanup_proc()` — `del proc_callable`, then
>   `submit_agent_cleanup()` (`src/sase/ace/tui/actions/agents/_cleanup_procs.py`).
> Everything reachable only through those two discarded callables is dead in production:

*See full plan file for details.*

