# Chat History - ace-run (ql--plan)

- **TIMESTAMP:** 2026-07-31 13:26:18 EDT
- **MODEL:** claude/opus
- **AGENT:** ql--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-ql__plan-260731_131752.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-ql__code-260731_131752.md`

**Plan:** /home/bryan/.sase/plans/202607/notification_sent_at.md


## Prompt

#gh:gh_sase-org__sase Can you help me start showing the date and time that the currently selected notification in the TUI's notification panel was sent somewhere in the panel? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/notification_sent_at.md`

> # Show when the selected notification was sent in the notification panel
> ## Problem
> The notification panel (`NotificationModal`, opened with `i` from any ACE tab) tells you only how _old_ a notification
> is. Every row in the left list ends with a relative age token — `4m ago`, `2h ago`, `3d ago` — produced by
> `format_relative_time()`. Nowhere in the panel can you see the actual wall-clock date and time a notification was sent.
> That hurts in three concrete ways:
> 1. **Ambiguity at the coarse end.** `3d ago` covers a 24-hour window; `2h ago` cannot be correlated with a log line, a
>    commit, or an agent run whose timestamps are absolute.
> 2. **Staleness.** The relative token is computed when the list is built. Leave the panel open for twenty minutes and
>    every row still claims the age it had on open. There is no authoritative, non-decaying time anywhere on screen.

*See full plan file for details.*

