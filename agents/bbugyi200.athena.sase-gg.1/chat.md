# Chat History - ace-run (sase-gg.1)

- **TIMESTAMP:** 2026-08-06 12:40:35 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-gg.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-gg.1, bead=sase-gg.1)
%clan(sase-gg, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-gg.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-gg.1 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-gg.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now I'll write the shared helper.

Now route the six modules through it.

Still used. Now `test_core_rust.py`:

Now `test_core_vcs_log.py`, `test_core_git_query.py`, `test_core_agent_scan_facade.py`, `core_agent_scan_helpers.py`:

Now add the missing imports and clean up now-unused ones.

Now the regression test pinning the helper's contract.

Now prove the fix reaches the reported failure by constructing the poisoning order under pytest.

The plan listed six modules, but `tests/test_core_facade/` has the same pattern in 8 more files. Same defect window — I'll route those too.

Now add imports to those files.

Now clean up newly-unused `sys`/`types` imports in the core_facade files and run the suite.

Clean. Now run `just check`.

Done. `sase-gg.1` is closed.

## What changed

**New shared helper — `tests/_rust_extension_module_helpers.py`**

Three functions that patch the extension parent and its compiled submodule as a unit, all through `monkeypatch` so teardown restores both together:

- `patch_rust_extension(monkeypatch, module)` — install a prebuilt fake
- `install_fake_rust_extension(monkeypatch, **bindings)` — build + install
- `evict_rust_extension(monkeypatch)` — remove both

Each evicts `sys.modules["sase_core_rs.sase_core_rs"]` alongside the parent, so any re-import takes the cache-miss path and importlib's `setattr(parent, child, module)` rebinds the name the maturin `__init__.py` reads on line 3.

**Call sites routed through it — 14, not 6.** The plan named six modules; `tests/test_core_facade/` had eight more (`_helpers.py`, `test_status.py`, `test_query.py`, `test_parser.py`, `test_project_lifecycle.py`, `test_prompt_stash.py`, `test_notification_store.py`, `test_agent_cleanup_facade.py`) with the identical parent-only pattern and the same poisoning window. Routing them is the same containment change, not the refactor the plan put out of scope. I recorded a `PROPOSED FOLLOW-UP:` note so the land agent can correct the plan's file list.

**Regression test — `tests/test_rust_extension_module_helpers.py`.** Asserts the helper's contract (submodule evicted with parent, re-import while patched rebinds the extension, extension still importable after teardown), so it stays green on both the current wheel and the hardened one from the `coreinit` phase.

## Verification

The plan explicitly warned that a green ordinary run isn't evidence here, so I built the poisoning order directly in a scratch pytest probe:

- old `monkeypatch.delitem`/`setitem` pattern → `NameError: name 'sase_core_rs' is not defined` at `site-packages/sase_core_rs/__init__.py:3`, both tests failed
- same sequence through the new helper → 2 passed

Also: `just install` then `just check` exit 0 (every lint gate plus the scoped test lane), and 328 tests across the touched modules pass serially and under `-n 4`.

I did not run `just check-full` — the epic's `verify` phase owns that, and the full suite gets env-killed in this sandbox.

The bead was already closed and the notes published. Now committing.

Committed and pushed; working tree clean, branch level with `origin/master`.

**sase-gg.1** — extension parent/submodule sync across `sys.modules` patches:

- **`tests/_rust_extension_module_helpers.py`** (new) — `patch_rust_extension`, `install_fake_rust_extension`, `evict_rust_extension`. Each evicts `sase_core_rs.sase_core_rs` alongside the parent via `monkeypatch`, so a re-import while patched takes the cache-miss path and importlib's `setattr(parent, child, module)` rebinds the name the maturin `__init__.py` reads on line 3. Teardown restores both together.
- **14 patch sites routed through it** — the six modules the plan named plus eight more in `tests/test_core_facade/` with the identical parent-only pattern. A `PROPOSED FOLLOW-UP:` note on the bead flags the plan's file list as non-exhaustive for the land agent.
- **`tests/test_rust_extension_module_helpers.py`** (new) — pins the contract: submodule evicted with parent, re-import while patched rebinds, real extension still imports after teardown.

Verification from the prior pass: a scratch pytest probe reproducing the poisoning order failed with `NameError: name 'sase_core_rs' is not defined` under the old pattern and passed under the helper; `just check` exited 0; 328 tests across the touched modules passed serially and under `-n 4`. `just check-full` was not run — the epic's `verify` phase owns it, and the full suite gets env-killed in this sandbox.

The bead was already closed at 16:38:52Z (`done`); the commit confirmed it as already closed. One non-blocking warning: prompt-archive/agent-hood publication was deferred on a busy agents sync lock and will retry automatically — the code commit itself pushed successfully.
