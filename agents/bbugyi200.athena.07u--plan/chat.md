# Chat History - ace-run (07u--plan)

- **TIMESTAMP:** 2026-08-19 11:04:57 EDT
- **MODEL:** claude/opus
- **AGENT:** 07u--plan

**Plan:** /home/bryan/.sase/plans/202608/feature_task_type_scoping.md


## Prompt

#gh:gh_sase-org__sase No enabled sase project should use the "feature" task type except for the
"sase" sase project (indicated by the fact that only this repo defines this task type in
its project-local sase/sase.yml file), so I don't understand why the bob-cli project
seems to support the "feature" task type anyway (see the command output below and the
task type sections in the bob-cli project repo's agent instruction files for context).
Can you help me diagnose the root cause of this issue and fix it?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/feature_task_type_scoping.md`

> # Scope the `feature` task type to the sase project
> ## Problem
> The reported symptom: the `bob-cli` project advertises and accepts the `feature` task
> type even though only the `sase` project is supposed to use it.
> ### Root cause: `feature` is a builtin, not a sase-local type
> `feature` is one of the five **builtin host task types** declared in
> `src/sase/task_types/_builtin.py` (`_feature_spec()` at line 144, returned by
> `_builtin_task_type_specs()` at line 269) and registered through `BuiltinTaskTypes` for
> **every** project by `discover_task_type_specs()`
> (`src/sase/task_types/_discovery.py:38-50`). `assemble_task_type_registry()`

*See full plan file for details.*

