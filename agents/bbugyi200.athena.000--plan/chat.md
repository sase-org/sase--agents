# Chat History - ace-run (000--plan)

- **TIMESTAMP:** 2026-08-13 17:18:06 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 000--plan

**Plan:** /home/bryan/.sase/plans/202608/background_tasks_to_procs.md


## Prompt

#gh:gh_sase-org__sase I want to migrate the name for sase's Background Tasks from Tasks to Procs. Can you help me make this migration? Make sure you update every relevant (take care to make sure that each reference you update truly is related since "task" is such a generic term) reference:

- every file name
- every comment
- every skill
- every memory
- everything...

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/background_tasks_to_procs.md`

> # Plan: Rename SASE Background Tasks to Procs
> ## Background
> SASE's durable background-execution feature is currently called **Background Tasks**. It
> consists of:
> - a Rust-owned JSONL store and wire (`../sase-core/crates/sase_core/src/tasks/`),
> - a Python facade package (`src/sase/tasks/`, 8 modules, ~1,390 lines),
> - the `sase task` CLI command tree (`list`, `show`, `run`, `kill`),
> - the ACE TUI's tracked-task runtime (`TaskQueue`, `TaskMirror`, `TaskReporter`, the
>   `TaskActionsMixin`) and its Admin Center **Tasks** tab,
> - the `tasks.history_limit` config key and the `~/.sase/tasks/tasks.jsonl` store.

*See full plan file for details.*

