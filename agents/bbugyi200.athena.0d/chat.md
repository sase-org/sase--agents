# Chat History - ace-run (0d--plan)

- **TIMESTAMP:** 2026-07-07 02:06:16 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 0d--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-0d__plan-260707_015431.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260707_015431.md`

**Plan:** /home/bryan/.sase/plans/202607/telegram_project_display_names_1.md


## Prompt

The user sent an image via Telegram with the following caption:

#gh:gh_sase-org__sase I still see the full project directory name being used instead of just, for example, "sase". Can you help me fix this once and for all? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %m:claude/claude-fable-5

The image has been saved to: /home/bryan/.sase/telegram/images/20260707_055429_AgACAgEAAxkB.jpg
Please read the image file and respond to the user's request.

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/telegram_project_display_names_1.md`

> # Fix Telegram surfaces showing canonical project directory keys instead of display names
> ## Problem
> Telegram messages still show the canonical project directory key (e.g. `gh_sase-org__sase`, or its filename-sanitized
> form `gh_sase_org__sase`) instead of the project display name (`sase`). Prior fixes (`1cbe79f91`, `b7e982967`,
> `91d6a4f18`, `228fc78af`) covered the ACE TUI, but the `sase-telegram` plugin never got the same treatment.
> Confirmed leak sites (from a live screenshot + a full audit of the `sase-telegram` repo):
> 1. **Prompt echoes in messages** — the workflow-complete "📝 Prompt:" block, the `/list` prompt snippet, the `/kill` and
>    `/fork` selection descriptions, and the launch-notification prompt snippet all show `#gh:gh_sase-org__sase ...`
>    verbatim.
> 2. **Copy-text buttons** — Fork/Wait buttons (workflow-complete message, launch notification, `/fork` command),

*See full plan file for details.*

