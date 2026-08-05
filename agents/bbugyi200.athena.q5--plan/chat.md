# Chat History - ace-run (q5--plan)

- **TIMESTAMP:** 2026-07-31 08:25:09 EDT
- **MODEL:** claude/opus
- **AGENT:** q5--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-q5__plan-260731_081657.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-q5__code-260731_081657.md`

**Plan:** /home/bryan/.sase/plans/202607/bead_prefix_project_display_name.md


## Prompt

#gh:gh_sase-org__sase I don't understand why this epic bead (for the enabled `bob-cli` sase project) was named using the `gh_bobs-org__` prefix (see the output below for context). This epic bead was created by the `sase bead work` command, which was run as a sase background task after I approved an epic from the TUI. Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus 
```
bryan in 🌐 athena in bob-cli on  master is 📦 v0.1.0 via 🦀 v1.97.1
❯ pwd
/home/bryan/projects/github/bobs-org/bob-cli

bryan in 🌐 athena in bob-cli on  master is 📦 v0.1.0 via 🦀 v1.97.1
❯ sase bead list
◐ bob-cli-b · Capture sub-bullets onto existing Obsidian tasks
◐ bob-cli-b.3 · bob capture-tasks discovery command ← bob-cli-b
◐ bob-cli-b.4 · Hammerspoon task picker ← bob-cli-b
```

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/bead_prefix_project_display_name.md`

> # Plan: Derive bead issue prefixes from PROJECT_NAME instead of the ProjectSpec key
> ## Observed symptom
> In the enabled `bob-cli` project (ProjectSpec key `gh_bobs-org__bob-cli`, `PROJECT_NAME: bob-cli`), the epic bead that
> `sase bead work` created after an epic was approved from the TUI is named with the key, not the project name:
> ```
> ❯ pwd
> /home/bryan/projects/github/bobs-org/bob-cli
> ❯ sase bead list
> ◐ bob-cli-b · Capture sub-bullets onto existing Obsidian tasks
> ◐ bob-cli-b.3 · bob capture-tasks discovery command ← bob-cli-b

*See full plan file for details.*

