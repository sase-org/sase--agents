# Chat History - ace-run (toobig-35.split_file.src.sase.plugins.github_source.0)

- **TIMESTAMP:** 2026-08-19 01:00:47 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-35.split_file.src.sase.plugins.github_source.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_225904.md`

## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.plugins.github_source.0, clan=toobig-35)
%wait:toobig-35.split_file.src.sase.main.project_handler.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/plugins/github_source.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file and understanding its structure.

Now I'll create the split modules.

Now the facade:

Now update the two test files that referenced the renamed error classes:

Now install deps and run the lint + test gates:

Split done. `github_source.py` went from 755 lines to a 59-line facade over four private sibling modules, matching the existing `operations.py` / `_operations_*.py` pattern in this package.

| File | Lines | Owns |
|---|---|---|
| `github_source.py` | 59 | Stable public import surface (re-exports only) |
| `_github_source_errors.py` | 34 | Failure hierarchy + `GH_INSTALL_HINT` |
| `_github_source_gh.py` | 97 | Search constants, endpoint building, the `gh api` subprocess call |
| `_github_source_parse.py` | 149 | JSON envelope decoding + entry-payload normalization |
| `_github_source_shards.py` | 166 | `stars:`/`created:` shard tree for over-cap queries |
| `_github_source_fetch.py` | 364 | Paging/sharding driver, fetch state, warnings, `fetch_catalog_payload` |

Dependencies stay acyclic: `errors` ← `gh` ← `shards`, and `fetch` pulls from all three plus `parse`.

One forced rename: symvision forbids importing `_`-prefixed symbols across files, so `_GhCommandError` → `GhCommandError` and `_CatalogParseError` → `CatalogParseError` (they were only referenced by `tests/test_plugin_catalog.py` and `tests/test_plugin_catalog_github_source.py`, both updated). They're now in `github_source.__all__`. `WhichFn`/`RunFn`/`GH_SEARCH_MAX_PAGES` moved to `_github_source_gh.py` and are no longer re-exported from the facade — nothing outside the module imported them.

`just check` passes clean (all lint gates including symvision and toobig, plus the scoped test lane); the four plugin-catalog test files pass directly, 56 tests.

These are my changes from this session. Committing them now.

Committed and pushed. Now verifying the gates within this turn.

Committed as `f6e37e01b`, pushed, and `just check` passes clean (all 12 lint gates including symvision and toobig, plus the scoped test lane over 49 selected test files).

## What the split looks like

`src/sase/plugins/github_source.py` went from 755 lines to a 59-line re-export facade over five private sibling modules, matching the existing `operations.py` / `_operations_*.py` pattern in this package:

| File | Lines | Owns |
|---|---|---|
| `github_source.py` | 59 | Stable public import surface |
| `_github_source_errors.py` | 34 | Failure hierarchy + `GH_INSTALL_HINT` |
| `_github_source_gh.py` | 97 | Search constants, endpoint building, the `gh api` subprocess call |
| `_github_source_parse.py` | 149 | JSON envelope decoding + entry-payload normalization |
| `_github_source_shards.py` | 166 | `stars:`/`created:` shard tree for over-cap queries |
| `_github_source_fetch.py` | 364 | Paging/sharding driver, fetch state, warnings, `fetch_catalog_payload` |

Dependencies stay acyclic: `errors` ← `gh` ← `shards`, with `fetch` pulling from all three plus `parse`.

## One forced rename

Symvision forbids importing `_`-prefixed symbols across files, so `_GhCommandError` → `GhCommandError` and `_CatalogParseError` → `CatalogParseError`. Both are now in `github_source.__all__`; their only callers were `tests/test_plugin_catalog.py` and `tests/test_plugin_catalog_github_source.py`, both updated. `WhichFn`, `RunFn`, and `GH_SEARCH_MAX_PAGES` moved into `_github_source_gh.py` and are no longer re-exported — nothing outside the module imported them.

One note on the commit: the primary commit and push succeeded, but the tool warned that agent-hood publication for the `research` hood is queued for retry due to a pre-existing duplicate container name (`bbugyi200.athena.research.h.final`). That's unrelated to this change and retries automatically.
