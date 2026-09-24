# Chat History - ace-run (chop.refresh_docs.sase.1_365885.2)

- **TIMESTAMP:** 2026-09-23 22:44:21 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.1_365885.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.1_365885.2, tribe=chop)
%wait:chop.refresh_docs.sase.1_365885.1
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

I'll spot-check the most important finding (the Patch glob claim) before editing.

All five verification passes are done, and I'm now checking one query-syntax detail in the Rust core before I start editing the docs.

Confirmed. Now editing `docs/query_language.md`.

Next, `docs/xprompt.md`, `docs/cli.md`, `docs/pager.md`, and `docs/workspace.md`.

Provider and install docs are fixed. Now working through `docs/ace.md`, `docs/configuration.md`, and `docs/agent_families.md`.

`docs/ace.md` is done. Next I'm fixing `docs/configuration.md` and `docs/agent_families.md`.

All the edits are in. Next I'll look up the repo's lint rules so I can run the documentation checks.

The Markdown format check and the docs build both pass. `just lint` also includes a terminology audit that may scan docs, so I'll run that next.

All the checks pass and only documentation files are modified. Now I'll submit the final declaration.

I checked every description the update agent changed in `b4daeddfe` against the current code, including the Rust `sase-core` where the behavior lives there. Most claims were accurate. I fixed about two dozen that were wrong or imprecise across 11 doc files. The Markdown format check (`just fmt-md-check`), the docs build (`just docs-check`), the terminology audit and the flag-registry lint all pass. I did not run the full `just check`, since only docs changed. The host will commit the changes.

**Claims that were wrong:**
- **`query_language.md`:** it said only `name:` and `project:` treat `*` as a wildcard in Patch queries. In fact all six Patch filters do in the Patches tab and `sase search`. I also rewrote the Wildcards section so it separates the two query styles (panes that allow `-` and comma lists, and those that need `NOT`/`OR`). It now gives the actual rule for which unquoted values are allowed, and the examples use fields that exist.
- **`xprompt.md`:** `sase prompt show -f markdown` prints project tags without color. The JSON output of `sase prompt list` and `sase prompt search` also keeps the exact stored text.
- **`ace.md`, Agent Decks:** pressing `p` with decks on shows no warning; the key just does nothing.
- **`ace.md`, PROMPTS entries:** the xprompt chips are green, not dim.

**Claims that were imprecise:**
- **`ace.md`:**
  - The traceback sits above `AGENT CHAT` (not `AGENT REPLY`) once an agent is done or failed.
  - In a deck, the traceback leads either the Reply or the Output card, and the `N/M` position only shows when there is more than one card.
  - On the Updates tab, `Esc` first clears marks and only closes on a second press.
  - npm install previews also show the target directory and PATH status.
  - I also corrected the hood query spelling, the reasons the jump toast can give, when `Enter` runs a tale plan directly (only with no Patch), and that artifact `z` zooms only inside tmux.
- **`agent_families.md`:**
  - The stored `%clan(...)` is rewritten only when the declaring member itself is the one edited.
  - `CLAN SUMMARIES` is part of the `TRIBE` document.
  - The tribe roster lives in the jump panel.
- **`configuration.md`:** the `agent_decks` flag also replaces the File/LLM Calls panel, and the TUI needs a restart after toggling it.
- **`pager.md`:** project tags are only colored when the pager runs inside the TUI.
- **`workspace.md`:** the 10-second retry covers any authentication refusal, not only `publickey`, and counts toward the three total attempts.
- **Smaller fixes:**
  - **`cli.md`:** only `accent` is `null` for disabled projects; `tag` is `null` when the name doesn't fit tag syntax.
  - **`llms.md`:** the fast refresh interval can't exceed the normal one.
  - **`INSTALL.md`:** `A` works from any row, and the second core package is `sase-core`.

**Clarity fixes for new users:**
- **`agent_providers.md`:** the intro contradicted itself about OpenCode, first listing it apart from the npm-installed CLIs and then calling it npm-packaged. It now lists OpenCode with the other npm CLIs.
- **`agent_providers.md`:** "active use" now links to the page that defines it.
- **`ace.md`:** the Agent Decks section now links forward to the panels it mentions.

**Suspected code bugs (not fixed, also listed in the commit message):**
1. The older Python Patch matcher (`src/sase/ace/query/matchers.py`, used by `patches_probe.py`) only handles `*` in `name` and `project`, while the Rust core handles all six filters.
2. The npm dry-run adds "(on PATH)" to the `package:` and `command:` lines, not only to `target:` (`src/sase/agent_clis/cli_install.py`).
3. The failure messages for npm installs say "install script".
4. The command palette still describes `za` as cycling members (`src/sase/ace/tui/commands/_mode_commands.py:44`).
5. Changing a tribe from the clan row (`N`) returns before the panel cache is cleared (`_tribe_assignment.py`), so the clan may stay in its old tribe panel until the next refresh.
6. Possible, not confirmed: clearing a tribe from the clan row may revert to the declared tribe after a rescan (`core/agent_clan_context.py`).

The first update agent had already flagged bug 5, plus a few others: a mypy error in `file_panel/_content.py`, stale Services `?` help rows, the `sase doctor` OpenCode hint, and the `--yes` help text.
