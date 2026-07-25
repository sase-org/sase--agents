# Chat History - ace-run (4q--plan)

- **TIMESTAMP:** 2026-07-10 15:47:01 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 4q--plan

**Plan:** /home/bryan/.sase/plans/202607/changespec_project_name_query.md


## Prompt

#gh:gh_sase-org__sase We currently don't respect the PROJECT_NAME project spec field when using the `project:<project>` ChangeSpec query filter. For example, in #sshot, the `project:gh_sase-org__sase` query should match no ChangeSpecs. Instead, `project:sase` should match the ChangeSpecs shown in the screenshot. Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/changespec_project_name_query.md`

> # Make ChangeSpec project queries respect `PROJECT_NAME`
> ## Problem and root cause
> `project:<project>` currently filters on the ProjectSpec storage directory derived from each ChangeSpec's `file_path`.
> That is why `project:gh_sase-org__sase` matches ChangeSpecs stored under `~/.sase/projects/gh_sase-org__sase/`, even
> though the active ProjectSpec declares `PROJECT_NAME: sase` and ACE groups those ChangeSpecs under `sase`.
> The inconsistency spans the full query pipeline:
> - Project lifecycle discovery already parses `PROJECT_NAME` into `ProjectRecordWire.display_name`, but ChangeSpec file
>   discovery discards that metadata and returns only active/archive paths.
> - The Python `ChangeSpec.project_name` property and reference `project:` matcher derive identity from the parent
>   directory.

*See full plan file for details.*

