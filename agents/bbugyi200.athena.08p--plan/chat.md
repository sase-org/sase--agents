# Chat History - ace-run (08p--plan)

- **TIMESTAMP:** 2026-08-20 13:31:57 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 08p--plan

**Plan:** /home/bryan/.sase/plans/202608/prompt_stash_cursor_restore.md


## Prompt

#gh:gh_sase-org__sase Can you help me add support to prompt stashes for remembering the users line and cursor position when they stashed the prompt? We should then restore that line/cursor position when the stash is loaded into the prompt input widget. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/prompt_stash_cursor_restore.md`

> # Plan: Restore prompt-stash pane and cursor position
> ## Goal and user-visible contract
> When ACE stashes a prompt draft, persist the active prompt pane and its cursor location
> with the stash row. Restoring that row must focus the corresponding restored pane and
> place the cursor at the same logical zero-based `(row, column)` within the text that was
> actually persisted. This applies to `Ctrl+S` current-pane stashes, `gs` / `Ctrl+G s`
> bundle stashes, restart recovery, stash-before-loading-an-xprompt, and `gS` pinned-stash
> replacement. Restore must work both when drafts are appended to an already-mounted
> prompt bar and when the app mounts a fresh home prompt bar.
> Keep the current interaction semantics around the new position:

*See full plan file for details.*

