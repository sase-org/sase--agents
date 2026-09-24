# Chat History - ace-run (chop.refresh_docs.sase.1_365885.1)

- **TIMESTAMP:** 2026-09-23 22:26:04 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.1_365885.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.1_365885.1, tribe=chop)
%queue(capacity=1)
Refresh the documentation for sase.

Review the current repository behavior and the changes since the last documentation
refresh. Update user-facing documentation so it is accurate, complete, and clear to
someone new to the project. You may only create, modify, or delete documentation
files, such as Markdown or other docs-tree content, READMEs, and doc-adjacent assets.
You MUST NOT create, modify, or delete source code, tests, build configuration, or any
other non-documentation file, even to fix a bug you are confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

Checking which of the 84 commits since the last docs refresh (6799f33d0) already updated their own docs.

Launching three parallel doc-audit agents, each owning a separate set of doc files so their edits don't collide.

Agents are done. Now I'm handling the remaining gaps myself: the `agent_decks` flag table, `sase prompt run --prefix`, and the `I` key claim in the Updates tab docs.

Verifying how the Updates tab `I` key really behaves before I touch that wording.

Confirmed: `I` is a plain alias of `Space` in the code. Fixing both spots in `configuration.md`, then running the docs checks.

Markdown formatting and the strict mkdocs build both pass. Next: the PDF size gate (we added content), then the repo's `check` gate.

`check` failed in mypy on a source file. I only changed docs, so I'm confirming the failure is already on master.

The mypy error is already on master: commit 00ee51996 (HEAD, deck panel) introduced it and my changes don't touch it. I'll file it as a CI task bead.

Epic sase-17d (agent decks) is in progress and caused this, so the skill says to note it on that epic rather than file a new task.

I updated 14 doc files to cover what landed since the last docs refresh (commit `6799f33d0`, 84 commits ago). Only documentation changed, and the host will commit it. The Markdown format check, the strict mkdocs build and the PDF size check all pass. `sase tool run check` fails on a mypy error in source code that was already on master before my edits.

**What the docs now cover**
- **`docs/ace.md` and `docs/agent_families.md`:**
  - A new **Agent Decks (beta)** section: how to turn it on and what it does today.
  - Jumps and link reveals, the `CLAN MEMBERS` roster in the jump panel, and the tribe `CLAN SUMMARIES` / `PROMPTS` sections.
  - Filter counts, `Ctrl+K` prompt-history scope seeded from `+project` tags, and `Enter` on a tale-plan family.
  - Corrected key descriptions for the Services, Updates, Procs and prompt-stash views.
- **`docs/configuration.md`:**
  - Three flags were missing from the flag table: `agent_decks`, `bgcmd_legacy_slots` and `muse_synchronous_shell`.
  - The Updates tab's `I` key is documented as an alias of `Space`, matching the code; the docs had said it only marks installable rows.
  - Added the undocumented `H` history key, the `[manual]` badge, and how npm installs are previewed.
- **`docs/agent_providers.md`, `docs/llms.md`, `docs/getting_started.md`, `INSTALL.md`:** installing npm-packaged agent CLIs (including OpenCode) with `sase agent-cli install`, how often usage is re-checked while a provider is in use, and each provider's minimum check interval.
- **`docs/cli.md`, `docs/xprompt.md`, `docs/pager.md`, `docs/query_language.md`, `docs/beads.md`, `docs/workspace.md`, `docs/architecture.md`:**
  - Where `+<project>` tags are shown and colored.
  - Wildcard rules that differ between query dialects (quoting, `NOT`/`OR`).
  - Retries of failed `git fetch` when preparing a workspace, and where clan records are stored.

**Failing check:** mypy reports `src/sase/ace/tui/widgets/file_panel/_content.py:132: "FilePanelContentMixin" has no attribute "parent"`. It comes from `00ee51996`, the agent-decks commit at HEAD. I added a note on the in-progress agent-decks epic `sase-17d` rather than filing a duplicate task.

**Possible code bugs I found but did not fix:**
1. On the Agents tab, pressing `N` to edit a clan's tribe returns early in `_tribe_assignment.py` (around lines 320–331). It skips clearing marks, refreshing the panel and re-applying the filter, so the clan may stay under its old tribe until the next refresh. I found this by reading the code and did not run it.
2. With `agent_decks` on, there are no keys yet to switch decks or cards, so the Reply card can't be reached. This looks like an unfinished stage of the epic, and the docs say so.
3. The `?` help on the Services tab still lists `/`, `V`, and update sub-tabs switched with `]`/`[`, which no longer match what the tab does.
4. `sase doctor`'s install hint for OpenCode points to the OpenCode website, while `sase agent-cli install` installs it through npm (`opencode-ai`).
5. The help for `sase agent-cli install -y/--yes` mentions only install scripts, but the flag also applies to npm installs.
6. Wildcards like `path:*tags*` work unquoted only in the simple (flat) query syntax. The query syntaxes that use `AND`/`OR`/`NOT` need them quoted. That may be intended; the docs now spell it out.
7. `sase pager` colors `+<project>` tags only when the project list has already been loaded, as it is inside the TUI. Run on its own, the pager shows them uncolored.

The commit message lists the same suspected code issues.
