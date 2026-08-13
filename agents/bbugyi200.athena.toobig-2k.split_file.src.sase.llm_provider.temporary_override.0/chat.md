# Chat History - ace-run (toobig-2k.split_file.src.sase.llm_provider.temporary_override.0)

- **TIMESTAMP:** 2026-08-13 11:42:14 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-2k.split_file.src.sase.llm_provider.temporary_override.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260813_104227.md`

## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.llm_provider.temporary_override.0, clan=toobig-2k)
%wait:toobig-2k.split_file.src.sase.artifact_providers.registry.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/llm_provider/temporary_override.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by reading the file to understand its structure.

Now I'll create the new modules. Starting with the persistence layer:

Now the main module, rewritten as the public API surface:

Now updating the tests that reach into the moved internals:

Now the `test_alias_overrides.py` import block and its `_atomic_write_json` patch:

Now the peek test fixture and the completion-lock test:

All 156 pass. Now the full gate:

Symvision only counts `from x import name` as a consumer. Let me switch to direct imports and rework the peek fixture's patch point:

Now the facade:

Now fix the peek test fixture to patch a stable point:

Split done — 703 lines became four modules, all well under 500. `just check` passes clean (all lint gates + 570 scoped test files).

**The layering**, each file a single concern:

| File | Lines | Role |
|---|---|---|
| `temporary_override.py` | 288 | Public API: duration parsing, get/set/clear per alias, `default` back-compat wrappers |
| `temporary_override_state.py` | 312 | The `~/.sase/llm_override.json` store: locking, atomic writes, v1→v2 migration, entry validation, self-cleaning reads |
| `temporary_override_defaults.py` | 113 | `resolve_effective_default_provider_model{,_with_effort}` — `@default` alias precedence |
| `temporary_override_peek.py` | 97 | Lock-free, time-gated display cache for keystroke paths |

**Key decisions:**

- `temporary_override.py` stays the public entry point and re-exports `TemporaryLLMOverride`, `peek_active_alias_overrides`, and both `resolve_effective_default_*` functions via `__all__`. Every existing `src/` import site — including `llm_provider/__init__.py` — is unchanged.
- The API module no longer touches the file directly. Lock-and-write cycles became two state-module operations, `store_alias_override()` and `remove_alias_override()`, so all persistence lives behind one boundary (`src/sase/llm_provider/temporary_override_state.py:264`).
- `temporary_override_defaults.py` reaches back for the active `default` override through a lazy import (`_active_default_override`, line 104), matching the file's existing cycle-breaking style and keeping `get_active_temporary_override` patchable in one place.
- Symvision's rule against cross-file private imports drove which helpers became public: `state_path`, `extract_raw_entries`, `entry_from_dict`, `load_active_overrides`, `store_alias_override`, `remove_alias_override`. Everything else stayed `_`-private. Symvision only credits `from x import name` as a consumer, not `module.name` attribute access, so callers import symbols directly.

**Test updates** (7 files) were confined to internals that moved: `_state_path` → `temporary_override_state.state_path`, the `_atomic_write_json` concurrency patch and the `_locked_state` "peek never locks" patch retargeted to the state module. The peek fixture now patches `override_state.sase_home` instead of `_state_path`, which survives the direct-import style.

One thing I did not run: `just check-full`. `just check`'s scoped lane selected 570 of 2590 test files and reported `contexts baseline stale` — normal for this workspace, but selection is a heuristic. Worth a monitored `just check-full` before landing, since this touches a module imported across the TUI, axe, and xprompt.

I'll verify the current state of the changes before committing.

All gates pass. Committing now.

Committed as `4f22634fe`, tree clean and pushed (`master` level with `origin/master`).

## What was split

`src/sase/llm_provider/temporary_override.py` was 703 lines mixing four concerns. It's now four modules, each with a single job:

| File | Lines | Role |
|---|---|---|
| `temporary_override.py` | 288 | Public API: duration parsing, per-alias get/set/clear, `default` back-compat wrappers |
| `temporary_override_state.py` | 312 | `~/.sase/llm_override.json` store: locking, atomic writes, v1→v2 migration, entry validation, self-cleaning reads |
| `temporary_override_defaults.py` | 113 | `resolve_effective_default_provider_model{,_with_effort}` — `@default` alias precedence |
| `temporary_override_peek.py` | 97 | Lock-free, time-gated display cache for keystroke paths |

Key structural change: the API module no longer touches the file directly. Its lock-and-write cycles became two state-module operations, `store_alias_override()` and `remove_alias_override()`, so all persistence lives behind one boundary. `temporary_override.py` remains the public entry point and re-exports the moved symbols via `__all__`, so every existing import site — including `llm_provider/__init__.py` — is unchanged. Test edits (7 files) were confined to internals that moved.

## Verification

`just check` passed clean before committing — all lint gates (ruff, mypy, symvision, toobig, keep-sorted, changelog, terminology) plus the scoped test lane, which selected 570 of 2590 test files. The commit hook's `just fix` ran without further changes.

Two things worth knowing:

- **I did not run `just check-full`.** The scoped lane is a heuristic backstopped by CI, and it reported `contexts baseline stale`. This module is imported across the TUI, ace, and xprompt, so a monitored `just check-full` is worth doing before this goes further.
- **The commit printed a pre-existing warning:** this project has 2 quarantined agent-hood publication requests, so the link written to this commit may stay unavailable until `sase agent sync --retry-quarantined` clears the outbox. Unrelated to this change — the commit itself succeeded.
