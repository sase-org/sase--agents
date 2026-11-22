# Chat History - ace-run (toobig-ag.gc_policy_policy.0)

- **TIMESTAMP:** 2026-11-21 23:44:54 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-ag.gc_policy_policy.0

## Prompt

%id:toobig-ag.gc_policy_policy.0
%clan(toobig-ag, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 757  tests/test_stale_running_cleanup_monitor_claims.py[/#87D7FF]
[#87D7FF]• 737  src/sase/ace/tui/util/_gc_policy_policy.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/util/_gc_policy_policy.py` file into multiple files? Use your best
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

Done. The 737-line `src/sase/ace/tui/util/_gc_policy_policy.py` is now four modules, each under 500 lines, with behavior preserved.

New layout (all line counts via `wc -l`):

- [`_gc_policy_common.py`](/absolute/path/to/src/sase/ace/tui/util/_gc_policy_common.py) (14 lines) — public `safe_probe`, the one helper needed by both new modules.
- [`_gc_policy_gate.py`](/absolute/path/to/src/sase/ace/tui/util/_gc_policy_gate.py) (240 lines) — public `PolicyGateMixin` plus private `_classic_thresholds`: duty floor, thresholds, `combined_last_full_mono`, `collection_due`, `idle_gate`, and the idle/allocated-blocks probes.
- [`_gc_policy_sweep.py`](/absolute/path/to/src/sase/ace/tui/util/_gc_policy_sweep.py) (453 lines) — public `PolicySweepMixin(PolicyGateMixin)`: cost gate, `tick`/`tick_safe`, census runner, trim; owns the `gc_trigger`/`queue_row`/`emit_row` and census-name bindings.
- [`_gc_policy_policy.py`](/absolute/path/to/src/sase/ace/tui/util/_gc_policy_policy.py) (104 lines, was 737) — facade defining `GCPolicy(PolicySweepMixin)` with the original `__init__`; keeps the public import path (`gc_policy.py` and `_gc_policy_lifecycle.py` still do `from ._gc_policy_policy import GCPolicy`). Private `_NullRecorder`/`_allocated_blocks` live here since only `__init__` uses them. No `_`-prefixed name is imported across the new modules.

Tests retargeted (no `policy_module` patching remains): `gc_trigger`/`queue_row`/`CENSUS_INTERVAL_S`/`survivor_census_safe` patches now target the sweep module; `latest_rss_bytes` patches target both gate and sweep, since the gate's `idle_gate` and the sweep's `tick`/`_note_full_collection` each import it directly from `gc_telemetry`.

Verification observed:

- `pytest` on the six gc-policy test files: 49 passed.
- `just _lint-toobig`: exit 0.
- `tools/check_epic_symbol_freshness` and `symvision src/sase` (the `just _lint-symvision` body): "All public/private classes/functions are used properly!"
- `.venv/bin/mypy` (6688 files) and `typecheck_extensionless_tools` (the `just _lint-mypy` body): no issues.
- `sase tool run check`: every Python gate passes including ruff, mypy, and symvision; the single failure is `lint (docs contract)` on `reference/automation/notification-gates.md` word budget, which I confirmed also fails on the stashed base — pre-existing and untouched by this split.

Declaration submitted — commit staged for the gc-policy split.
