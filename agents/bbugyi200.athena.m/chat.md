# Chat History - ace-run (m--plan)

- **TIMESTAMP:** 2026-07-06 15:52:15 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** m--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-m__plan-260706_154912.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260706_154912.md`

**Plan:** /home/bryan/.sase/plans/202607/telegram_project_display_names.md


## Prompt

#gh:gh_sase-org__sase We recently replaced the raw project directory name with the configured project name in user-visible text all throughout our codebase. See recent git commits for context. I think we maybe overlooked some references in the sase-telegram repo. Can you help me confirm this and fix those references as well? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/telegram_project_display_names.md`

> # Plan: Telegram Project Display Names
> ## Context
> Recent SASE changes replaced raw project directory keys in user-visible output with configured project display names
> while preserving canonical identifiers for lookup, storage, JSON, and command/callback payloads. The main repo now
> exposes `sase.project_display_names` helpers such as `project_display_name_for`, `humanize_cl_name`, and
> `humanize_cl_names_in_text`.
> The `sase-telegram` repo still has several Telegram-visible surfaces that can render raw project keys or
> project-prefixed ChangeSpec/agent names. Raw identifiers are also used as routing data, so the fix must be display-only.
> ## Confirmed Overlooked Surfaces
> In `src/sase_telegram/scripts/sase_tg_inbound.py`:

*See full plan file for details.*

