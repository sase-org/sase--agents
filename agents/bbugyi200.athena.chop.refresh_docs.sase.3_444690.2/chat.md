# Chat History - ace-run (chop.refresh_docs.sase.3_444690.2)

- **TIMESTAMP:** 2026-09-28 20:54:05 EDT
- **MODEL:** grok/grok-4.7
- **AGENT:** chop.refresh_docs.sase.3_444690.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.3_444690.2, tribe=chop)
%wait:chop.refresh_docs.sase.3_444690.1
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

I'll inspect the update agent's documentation changes and check each claim against the current system, then edit only docs. First I'm locating those changes and the repo's documentation checks.

The workspace is a full SASE checkout. Next I’ll find the update agent’s doc diff and the checks that apply to it.

The polish pass follows the update agent’s docs commit. I’ll pull that diff and the agent transcript, then check each claim against the code.

The update agent’s diff is in one commit. I’m checking the quit-stash, tab, and archive claims against the code while the transcript loads.

The update agent’s new draft-recovery and quit text mixes up Stash, Trash, and the archive, and it treats restart as if it had quit’s save-failure protection. I’m correcting those passages to match the code.

The documentation edits are already in the tree. I'll confirm they are still docs-only, then run the repository's documentation checks before submitting.

Docs changes are still uncommitted and limited to the seven handbook files. I'll check which documentation recipes the repo expects, then run them.

Handbook pages changed, so the strict site build is the check that has to pass. I'll start that and the Markdown format check together.

The strict site build and Markdown format check both passed. The handbook text changed, so the PDF handbook check is next.

The handbook now matches how Stash, Trash, and the stash archive actually behave. The documentation commit has been submitted.

**Draft recovery.** Stash, Trash, and `~/.sase/prompt_stash_archive.jsonl` are three stores. Trash is a view of the Stash tab in the Prompts overlay, opened with `t` or the trash chip. From Trash, `t` or `Esc` returns to the Stash list. `[` and `]` cycle only Stash and History; leaving Trash for History and coming back restores Trash, because the Stash tab remembers its view. `Esc` on the Stash list or on History closes the overlay.

A copy is archived when a draft permanently leaves Stash or Trash, or when a Stash row's text, frontmatter, or cursor is replaced. The reason names are `popped`, `purged`, `evicted`, and `overwritten`. Moving a row into Trash, or bringing it back, writes no archive copy. An unpinned load archives as `popped` and removes the row. A pinned load stays in Stash and is not archived. `gS` keeps the updated row in Stash and archives the previous version. A pin-only change does not archive. With `trash_limit` set to `0`, a discard is archived immediately as `evicted` and never appears in Trash.

`sase prompt stash-archive` with no subcommand lists the newest 20 rows. `show` and `restore` use a full id or a unique prefix and always take the newest archived copy of that id. Older copies of the same id stay visible in `list -j`. That newest-copy rule is intentional. `restore` only appends the draft back onto Stash. Load it afterward with `@` or the overlay. `@` loads immediately only when that draft is the sole unpinned row.

**Quit and restart.** An open unsent agent prompt does not by itself ask you to confirm. Plain `q` and menu quit (`1` / `s`) write every non-empty pane, or frontmatter alone when the panes are empty, to one Stash row. Plan Feedback and Coder Prompt bars are omitted. If that write fails, the TUI stays open with `Failed to stash prompt draft — staying so no text is lost`, and `1` / `s` leaves the scheduler running. Restart (`2` / `r`, or `3` / `a`) tries the same save and, on success, says `Prompt draft stashed; press @ to restore after restart`.

A submitted prompt still waiting to launch is separate from an in-flight scheduler launch batch. When a quit or restart actually exits, each waiting prompt is recorded in prompt history as cancelled and copied to Stash. The exit still finishes if that copy fails or runs longer than 3 seconds. Declining a confirmation writes nothing.

**Goals and ToolRuns.** A Goal is created, reshaped, and settled by a person. Agents can read it and cite `@goal:<id>`. Its status and timeline are independent of beads and of a plan's `goal:` frontmatter. ToolRuns cover declared project tools and ad-hoc `sase tool run -- argv`, including output and diagnostics.

**Suspected bug, left unfixed.** Restart still exits when the pre-restart stash write fails. `_restart_tui` in `src/sase/ace/tui/actions/axe.py` sets `_quit_draft_stash_attempted` even when `_stash_prompt_bar_before_restart` returns failure or raises. The quit path in `lifecycle.py` then skips its retry, so the TUI does not stay open and does not show the quit error. The draft can be lost. `test_restart_tui_still_quits_when_restart_stash_raises` encodes that exit. Quit itself still stays open on a failed write.

`just docs-check` and `just fmt-md-check` passed. `just docs-pdf-check` under this environment's `CI=true` stopped immediately because Playwright tried to install browser dependencies with sudo. The same recipe with `CI` unset completed: the handbook validated at 1040 pages.
