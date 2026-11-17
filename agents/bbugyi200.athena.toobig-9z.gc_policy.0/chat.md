# Chat History - ace-run (toobig-9z.gc_policy.0)

- **TIMESTAMP:** 2026-11-17 10:38:33 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9z.gc_policy.0

## Prompt

%id:toobig-9z.gc_policy.0
%clan(toobig-9z, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 955  src/sase/ace/tui/util/gc_policy.py[/bold #FFAF5F]
[#87D7FF]• 701  src/sase/ace/tui/util/gc_telemetry.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/util/gc_policy.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

Done. The 955-line `gc_policy.py` is now six files, each under 500 lines, with behavior preserved.

**New layout** (all in `src/sase/ace/tui/util/`):

| File | Lines | Contents |
|---|---|---|
| [gc_policy.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/gc_policy.py) | 67 | Facade: original docstring plus `X as X` re-exports of public names only |
| [_gc_policy_config.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/_gc_policy_config.py) | 48 | All constants plus public `is_enabled()` |
| [_gc_policy_census.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/_gc_policy_census.py) | 279 | Census: public `TypeCensus`, `census_enabled`, `survivor_census_safe`, `top_types`, `known_cache_census`; single-use helpers stayed private |
| [_gc_policy_policy.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/_gc_policy_policy.py) | 428 | Public `GCPolicy` (logic verbatim); logger pinned to `sase.ace.tui.util.gc_policy` so log capture is unchanged |
| [_gc_policy_trim.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/_gc_policy_trim.py) | 75 | Trim worker: public `spawn_trim_thread`/`start_trim_worker`/`stop_trim_worker`, private globals |
| [_gc_policy_lifecycle.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/_gc_policy_lifecycle.py) | 161 | Public `install_gc_policy`/`uninstall_gc_policy`, private `_active` and `_modal_text_input_active` |

Rules honored: no `_`-prefixed name is imported across the new modules (shared helpers use public names inside the `_`-prefixed modules); the facade re-exports no private names; `install_gc_policy` is the identical function object through facade and lifecycle, so the `_startup` identity check holds.

**Tests:** retargeted to patch where names are looked up (`policy_module` for `CENSUS_INTERVAL_S`/`gc_trigger`/`latest_rss_bytes`/`survivor_census_safe`, `trim_module` for `trim_allocator`/worker, `lifecycle_module` for `_active`). Symvision required making `snapshot_cache_census`, `lru_cache_census`, and `modal_text_input_active` private (test-only public use), which the tests now import directly. All 41 gc-policy tests pass.

**Verification:** `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` each pass individually (the one toobig info note is pre-existing `gc_telemetry.py`, untouched), and `sase tool run check` (run `33f31847…`) passes every stage including the scoped test lane (605 files).

One note: `gc_policy.latest_rss_bytes` / `gc_trigger` / `trim_allocator` no longer exist as facade attributes (they were incidental imports, used nowhere outside this module); tests now patch the modules that actually use them.

Declaration submitted. The `gc_policy` split work is declared for commit; the host will preserve it after this turn.
