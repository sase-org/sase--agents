# Chat History - ace-run (chop.refresh_docs.sase.5_036393.1)

- **TIMESTAMP:** 2026-08-18 09:44:53 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.5_036393.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.5_036393.1, tribe=chop)
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

I'll start by getting oriented in the repo and figuring out what documentation exists and when it was last refreshed.

Now let me apply the Launch Control label fixes.

Now the axe.md and notifications.md references:

Now fix the two stale chop descriptions inside that block:

Now let me apply the help-key and leader-mode corrections.

Now fix the help-key prose and add a note to each leader table:

Now fix `docs/configuration.md`'s inverted claim and the stale YAML sample:

Now let me add the missing `gf`/`Ctrl+G` rows:

Now let me rewrite that stale llms.md section:

Now let me document this gate in `docs/development.md`:

Documentation refresh is done. Both repository docs checks pass: `just docs-check` (mkdocs `--strict`) and `just docs-pdf-check` (757-page handbook built and validated). `just validate` also passes. Only documentation files were touched — `git status` shows 11 modified `docs/*.md` files and nothing else.

## What I did

I diffed the repo against `5411f5d4a` ("docs: refresh user-facing docs against current behavior", 2026-08-17), the last full refresh — 70 commits — and then verified doc claims against source rather than trusting the commit log, which surfaced older drift too.

**Corrections (docs contradicted current behavior):**

- **Help is bare `?`, not `,?`** — `show_help` is an app-level binding (`ace.keymaps.app.show_help: question_mark`); `leader_mode.keys.show_help` is in `_RETIRED_LEADER_KEYS` and is dropped at load (pinned by `tests/test_keymaps_registry_loading.py`). `docs/configuration.md` stated this exactly backwards, and `docs/ace.md` told new users to press `,?` in its second screenful. Fixed in both, plus the leader-mode tables and the YAML sample.
- **Claude tool-call capture** (`docs/llms.md`) described SASE writing `PreToolUse`/`PostToolUse` entries into the user's `.claude/settings.local.json` via a `sase_claude_tool_hook` console script. That was removed in `628581f29` (2026-05-16); capture is now stream-json parsing, and neither the script nor `_claude_hooks.py` ships. Rewrote the section against `_tool_call_claude.py`.
- **Launch Control row labels** — `launch model` → `default model`, `running agents` → `max runners` (`5c748697f`). 14 stale occurrences in `ace.md`/`llms.md`.
- **Per-type `+1` triage bar** (`66b884434`) — `beads.md`, `axe.md`, `notifications.md`, and the `configuration.md` chop descriptions still presented `bead.task_triage.min_plus_ones` as *the* bar. It is now the fallback for untyped/unregistered beads; a typed bead uses its own `triage.min_plus_ones` (`flake` ships `1`, every other builtin `0`).
- **Glossary terms rendering** (`445afde7c`) — no longer a prepended `**GLOSSARY TERMS:**` block; it is a `### Glossary Terms` H3 after `Long-Term Memory Files`. Fixed in `memory.md` and `init.md`, along with the Tier 2 nesting description.
- Smaller: `sase bead create --tier` is `-r, --tier`; `cycle_commits` shown as the canonical fold action (it is a legacy alias for `cycle_stitches`); `tests/test_core_agent_scan.py` was split into `test_core_agent_scan_*.py`; a bogus `,H` leader row (it is app-level `H`, already documented elsewhere).

**Completeness gaps filled:**

- `ace.keymaps.glossary` — an entire undocumented fifth keymap scope (22 actions). Added the defaults table to `configuration.md`, a remapping section and cross-links to `ace.md`.
- Undocumented leader keys `,@` (prompt stash picker) and `,Ctrl+G` (prompt history, edit newest); undocumented prompt-bar `gf` / `Ctrl+G f` (Prettier reformat) and missing `Ctrl+G d` / `Ctrl+G w` rows.
- `just check-full`'s flake-baseline gate (`selection-health --fail-on-new-flake` against `tests/reproducible_flake_baseline.txt`) was entirely undocumented despite being a stage a contributor hits — new subsection in `development.md`.
- A Glossary entry in the Getting Started component map.

## For a human to pick up

I found no code bugs — every discrepancy resolved to documentation drift. Two process notes:

1. The `axe:` YAML block in `docs/configuration.md` is a hand-maintained copy that has drifted: it omits the `external_mirror` lane, the `epic_resume` / `external_issue_mirror` / `external_pr_mirror` chops, and four `axe.lumberjack_*` top-level keys. I labeled it abridged and pointed at `axe.md` (which is complete) rather than syncing 240 lines that will drift again — generating that block from `default_config.yml` would be the durable fix.
2. The Claude tool-hook section was wrong for three months because `628581f29` changed provider behavior without touching `docs/`.

One scope note: I verified TUI keybindings by reading `src/sase/default_config.yml`, the keymap registry, and the pinning tests — not by driving the TUI.

These are my documentation changes from this session. Committing them now.

Committed as `4b6fcc031` — working tree clean, `master` in sync with `origin/master`.

## Summary

The documentation refresh is committed as a docs-only change: 11 files under `docs/`, +275/−160, nothing outside the docs tree.

**Corrections** (docs contradicted current behavior):

- Help is the bare `?` app binding, not `,?` — the leader variant is in `_RETIRED_LEADER_KEYS` and dropped at config load. `docs/configuration.md` had this exactly backwards and `docs/ace.md` told new users to press `,?`.
- `docs/llms.md` still described a `sase_claude_tool_hook` console script writing `PreToolUse`/`PostToolUse` entries into `.claude/settings.local.json`; that was removed in `628581f29` and capture is now stream-json parsing.
- Launch Control labels: `launch model` → `default model`, `running agents` → `max runners` (14 occurrences).
- Per-type `+1` triage bar: `bead.task_triage.min_plus_ones` is now the fallback for untyped/unregistered beads, not the rule.
- Glossary terms render as a `### Glossary Terms` H3, not a prepended `**GLOSSARY TERMS:**` block.
- Smaller: `-r, --tier`, `cycle_stitches` over the legacy `cycle_commits` alias, split `test_core_agent_scan_*.py`, removed a bogus `,H` row.

**Gaps filled:** the undocumented `ace.keymaps.glossary` scope (22 actions), leader keys `,@` and `,Ctrl+G`, prompt-bar `gf`/`Ctrl+G f`/`Ctrl+G d`/`Ctrl+G w`, the `just check-full` flake-baseline gate, and a Glossary entry in the component map.

**Checks:** `just docs-check` (mkdocs `--strict`), `just docs-pdf-check`, and `just validate` all pass. The `just fix` pre-commit hook ran clean.

**For a human to pick up:** no code bugs — every discrepancy was documentation drift. One maintenance item: the `axe:` YAML block in `docs/configuration.md` is a hand-maintained copy that has drifted (missing the `external_mirror` lane, three chops, four `axe.lumberjack_*` keys). I labeled it abridged and pointed at the complete `docs/axe.md` rather than syncing 240 lines that will drift again; generating it from `default_config.yml` is the durable fix.

Two things outside my scope, for your awareness: the commit printed a warning that this project has **15 quarantined agent-hood publication requests** (pre-existing, unrelated to these changes) — clear with `sase agent sync --retry-quarantined`. And I verified TUI keybindings by reading `src/sase/default_config.yml`, the keymap registry, and the pinning tests, not by driving the TUI.
