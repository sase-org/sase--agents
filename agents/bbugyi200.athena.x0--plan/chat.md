# Chat History - ace-run (x0--plan)

- **TIMESTAMP:** 2026-08-10 09:46:03 EDT
- **MODEL:** claude/opus
- **AGENT:** x0--plan

**Plan:** /home/bryan/.sase/plans/202608/task_launch_drop_commit_rollover.md


## Prompt

#gh:gh_sase-org__sase Can you help me remove the `IMPORTANT:` line from the `#bd/work_task` xprompt definition? Also, let's stop adding the `#commit` xprompt to the prompt used when launching sase agents to work task beads. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/task_launch_drop_commit_rollover.md`

> # Drop the `#commit` rollover and the redundant no-commit line from task-bead launches
> ## Goal
> Two coupled changes to how `sase bead work <task-id>` launches a task worker:
> 1. Remove the
>    `IMPORTANT: Do not commit your changes unless/until the finalizer asks you to.` line
>    from the bundled `bd/work_task` xprompt body.
> 2. Stop prefixing the rendered task-launch prompt with the `#commit` xprompt.
> After this change a task-bead launch prompt is exactly the VCS ref, the identity / model
> directives, the `bd/work_task` reference, an optional `#plan`, and optional feedback.
> ## Background and why these two go together

*See full plan file for details.*

