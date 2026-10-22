# Chat History - ace-run (chop.refresh_docs.sase.5_332802.2)

- **TIMESTAMP:** 2026-09-27 05:19:32 EDT
- **MODEL:** grok/grok-4.7
- **AGENT:** chop.refresh_docs.sase.5_332802.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.5_332802.2, tribe=chop)
%wait:chop.refresh_docs.sase.5_332802.1
%queue(capacity=1)
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where terminology or
workflow ordering could be misunderstood. You may only create, modify, or delete
documentation files, such as Markdown or other docs-tree content, READMEs, and
doc-adjacent assets. You MUST NOT create, modify, or delete source code, tests, build
configuration, or any other non-documentation file, even to fix a bug you are
confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I'll inspect the update agent's documentation changes and check each claim against the code that actually runs today. Only documentation files will be edited.

The worktree is clean, so the update agent's documentation changes are already committed. I'll locate those commits and compare them with the code.

This turn is the docs polish step after the update agent. I'll read that agent's diff and the chop instructions, then check each claim against the code.

The update agent changed the README, the TUI guide, and Getting Started. I'll read those passages next to the code that implements prompt history, stash, and Trash.

The update agent's History shortcut does not open after a `+home` launch, and the Trash limit note hides a stale first view. I'll correct those descriptions to match the code.

The update agent's prompt-recall notes were partly right, and the Getting Started shortcut was wrong for the tour it sits in. I corrected the docs to match the current TUI and left two code bugs unfixed. `just docs-check` passed.

**Reopening the Step 3 launch.** Pressing `,` then `.` does not open History after a `+home` run. That launch is stored as `#git:home`, and sase keeps that default prefix off the recent-workspace list the shortcut reads. With nothing else on the list, the TUI warns `No previously launched VCS xprompt` and stays put. Getting Started now uses `sase prompt list`, then `Space` and `Ctrl+K`, and says what each Prompts tab does:

- **History** `Enter` launches the stored prompt. `Tab` loads it into the prompt input.
- **Stash** holds drafts saved with `Ctrl+S` from a non-empty prompt. `Ctrl+S` on an empty prompt only opens Stash.
- **Trash** holds drafts discarded from Stash. Restoring one puts it back in Stash.
- `[` and `]` cycle Stash, History, Trash. From Stash, `[` opens Trash and `]` opens History.

**Stash `@`.** A lone pinned draft loads into the prompt bar and stays in Stash. A lone unpinned draft loads and is then removed from Stash. An empty Stash, or more than one draft, opens the overlay. Plan Feedback and Coder Prompt bars warn `Restore is only available for agent prompts` and stop.

**Trash limit.** Lowering `ace.prompt_stash.trash_limit` deletes the oldest over-limit rows the next time the overlay opens, and the toast names the count. That first window still shows the rows and `Trash M/N` count from before the deletion. Close it and open it again to see what remains. `Enter` on an already-deleted row does not restore it. The same note is now in the configuration guide.

**README.** Production use assumes a supported agent CLI that is installed and authenticated. The new link is the Prompts overlay, which covers past launches, saved drafts, and drafts discarded from Stash.

Two code bugs are documented and not fixed:

- Overlay open deletes over-limit Trash rows, then builds the Trash tab from the list it read before that deletion, so the first window can show more rows than the new limit. The builder is `_prompt_bar_stash_restore_overlay.py`.
- The empty Stash placeholder says `switch with ]`, but `]` moves from Stash to History. `[` wraps to Trash. The text is in `stash_pane_widget.py`.
