# Chat History - ace-run (2t.f1--plan)

- **TIMESTAMP:** 2026-07-08 16:04:14 EDT
- **MODEL:** claude/opus
- **AGENT:** 2t.f1--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-2t_f1__plan-260708_155947.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260708_155947.md`

**Plan:** /home/bryan/.sase/plans/202607/vcs_log_project_name.md


## Prompt

#gh:gh_sase-org__sase #fork:2t The output of the `sase vcs log` command is showing invalid project names (see #sshot). For example, as we have gone over MANY times, the user should NEVER see a project spec file name like "gh_sase-org__sase". Instead, they should see the project name (configured with the PROJECT_NAME field in the project spec file), which is "sase" in this example. Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/vcs_log_project_name.md`

> # Plan: `sase vcs log` — show the project name, not the spec-file slug
> ## 1. The bug (what the user sees vs. what they should see)
> `sase vcs log` renders a per-repo "badge" for every repo in the constellation (legend counts + a colored label on every
> commit row). For the **primary** repo the badge currently reads the raw project-directory slug — e.g.
> `gh_sase-org__sase` — instead of the configured project name `sase` (the `PROJECT_NAME` field of the project spec).
> This is the recurring "never show the on-disk project key to a human" problem: `gh_sase-org__sase` is the GitHub
> workspace-provider directory key (`gh_` prefix, `__` owner/repo separator), not a name any user typed or should read.
> The correct label is the project's display name, `sase`.
> Linked-repo badges (`chezmoi`, `sase-core`, `sase-github`, …) are already correct — they use the linked repo's own
> `name`. Only the **primary** badge is wrong.

*See full plan file for details.*

