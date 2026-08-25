# Chat History - ace-run (0dk--plan)

- **TIMESTAMP:** 2026-08-25 12:35:50 EDT
- **MODEL:** claude/opus
- **AGENT:** 0dk--plan

**Plan:** /home/bryan/.sase/plans/202608/feature_task_type_default.md


## Prompt

#gh:gh_sase-org__sase The `builtin@feature` task bead type should NOT be disabled for projects by default (see the sase/sase.yml file for context). Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/feature_task_type_default.md`

> # Plan: restore `feature` as an agent-creatable task type in every project
> ## Goal
> `feature` is one of SASE's five shipped builtin task types and it is agent-creatable by
> default (`src/sase/task_types/_models.py:57-58` — `spec.get("agent_creatable", True)`).
> Today that default is overridden off for every project on this machine, and the override
> has leaked into SASE's shipped source. After this epic:
> - no config layer disables `builtin@feature`;
> - `sase/sase.yml` carries no `feature` entry at all;
> - the builtin's `create_refusal` copy is policy-neutral, so a project that _does_
>   disable the type gets a useful refusal instead of one machine's history.

*See full plan file for details.*

