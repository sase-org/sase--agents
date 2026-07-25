# Chat History - ace-run (hd--plan)

- **TIMESTAMP:** 2026-07-21 15:10:04 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** hd--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-hd__plan-260721_150252.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260721_150252.md`

**Plan:** /home/bryan/.sase/plans/202607/artifacts_viewport_follow.md


## Prompt

#gh:gh_sase-org__sase When I jump forward on the commits sub-tab (and probably other sub-tabs) using the `<ctrl+f/b>` keymaps, the pane's viewport doesn't scroll as my selected commit moves out of view. Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/artifacts_viewport_follow.md`

> # Plan: Keep Artifacts selections inside their list viewports
> ## Context and root cause
> The shared non-PR Artifacts navigation path routes `Ctrl+F`, `Ctrl+B`, `g`, `G`, and adaptive entry jumps through
> `select_relative_entry()` and each pane's stable-target `select_entry_target()` implementation. This correctly moves the
> selected model entry and avoids opening it, but it does not uniformly preserve the `OptionList` viewport invariant that
> the highlighted row remains visible.
> Textual 8.0.1 implements viewport following inside `OptionList.watch_highlighted()` by calling `scroll_to_highlight()`
> before emitting `OptionHighlighted`. `CommitsTimeline` and `BugIssueList` deliberately bypass that watcher while
> `_programmatic_update` is true so direct highlight assignments cannot echo back into navigation or detail updates. The
> guard is necessary, but it also suppresses Textual's scroll side effect. A headless reproduction with 50 entries shows

*See full plan file for details.*

