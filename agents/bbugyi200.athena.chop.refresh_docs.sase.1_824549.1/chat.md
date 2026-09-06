# Chat History - ace-run (chop.refresh_docs.sase.1_824549.1)

- **TIMESTAMP:** 2026-09-06 09:19:44 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.1_824549.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.1_824549.1, tribe=chop)
%wait(runners=0)
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

I'll start by getting oriented in the repository and understanding what documentation exists and what's changed since the last docs refresh.

Let me read the required memory notes and survey what's changed since the last docs refresh.

Now let me make the documentation edits. Starting with the stale Agent Cleanup panel description:

Now the query-dialect updates for the new identity fields:

Now the Files pane dialect — it gained an `id:` key and its negation claim is stale:

Now the Procs tab `K` behavior:

Now let me add the `sase migrate` documentation to `docs/configuration.md`:

Now add the new sections to the configuration.md table of contents and the CLI index:

Now let me update the Agent-pane dialect docs with the new archive-capability booleans:

I found a real rendering bug in the docs — let me confirm and fix it:

Let me check every docs page for the same class of rendering breakage:

Now let me run the repository's verification gate as required:

Passed (exit 0). Now a final run covering the last edits:

All checks pass. Let me submit the required finalizer declaration:

Documentation refresh complete. `just check` and `just docs-check` (mkdocs `--strict`) both pass, and only documentation files were touched.

## What I found and fixed

**A rendering bug that broke ~1,400 lines of `docs/xprompt.md`.** A blank line had crept inside an inline code span, leaving `<script>` at the start of a line. Python-Markdown read that as an HTML block, so everything from the "Syntax" section onward rendered as raw text on the site and 15 cross-page anchor links resolved to nothing. The built page now emits 96 headings instead of 63. The source change is whitespace-only — content is byte-identical after normalization.

**`sase migrate` was entirely undocumented.** The offline local-state cutover kit (backup/plan/run/resume/status/verify/restore, the four-operation catalog, the backup root outside every runtime root, journals and receipts) now has a "Local State Cutover" section in `docs/configuration.md`, a `SASE_CUTOVER_BACKUP_DIR` env-var row, and an index row in `docs/cli.md`.

**The whole sase-w3 link-follow epic had landed with no docs.** `docs/ace.md` gains "The Reveal Ladder" — the ordered rungs (fold expansion → `limit:` drop → identity query → minimal widening → neutral `limit:all` → targeted hydration), when each is skipped, the reversible lens chip and its `^` return, and the honest exhaustion toasts — plus the Links-panel `⊘`/`↻` pre-flag glyphs. `docs/artifacts_pane_contract.md` gains a matching "Identity field" section.

**Stale prose corrected against current behavior:**

- The Agent Cleanup `C` clan chooser was deleted; docs still described it. Replaced with how clan containers now expand into their live members.
- Files-pane filters *do* support negation (docs said a leading `-` is rejected — I verified both the parser and the query evaluator).
- New query keys documented: Stitches `sha:` (prefix-matched), Plans `path:`, Beads `id:`, Files `id:`, and the auto-injected provider `path:`.
- `revivable:` was redefined and three archive-capability booleans added.
- Procs `K` now acts-or-explains and answers to `Shift+K`.
- `ace.artifact_viewer.video` is really `ace.artifact_file_viewer.video` — following the old docs would silently do nothing.
- `ace.lumberjack` and `sase stats` don't exist; replaced with `axe.lumberjacks` and a link to the Statistics tab.

Also added: SDD connect-only sidecar auto-connect on first launch, imported-agent owner badges and family containers, and the Projects init-plan modal's own keys.

## Suspected code issues (not fixed, per scope)

1. `src/sase/ace/link_reveal.py` — `HostQueryProbe.matches` and `build_host_query_probe` catch `(ProfileQueryError, LimitTokenError, Exception)`. The bare `Exception` makes the specific types dead and swallows genuine programming errors into a silent "no match", which would degrade the reveal ladder invisibly rather than failing.
2. `src/sase/ace/tui/widgets/artifacts/shell.py:124` — `build_reveal_chip`'s docstring points at `sase.ace.relation_reveal.is_relation_reveal_active`, but the link-follow path that actually drives it uses `link_reveal.is_link_reveal_active`. Stale cross-reference only; no behavior impact.

Both are noted in the commit message body as well.
