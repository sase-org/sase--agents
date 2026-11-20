# Chat History - ace-run (toobig-a8.state_scheduler.0)

- **TIMESTAMP:** 2026-11-19 19:04:52 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-a8.state_scheduler.0

## Prompt

%id:toobig-a8.state_scheduler.0
%clan(toobig-a8, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 815  src/sase/axe/_state_scheduler.py[/#87D7FF]
[#87D7FF]• 706  tests/ace/tui/test_launchable_mru.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/axe/_state_scheduler.py` file into multiple files? Use your best
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

Split complete. The 815-line `src/sase/axe/_state_scheduler.py` is now five files, all under 500 lines, with behavior preserved.

**New layout** (335 lines is the largest):

| File | Lines | Contents |
|---|---|---|
| [_state_scheduler.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/_state_scheduler.py) | 68 | Facade re-exporting the original public surface plus `__all__`; no `_private` names |
| [_state_scheduler_status.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/_state_scheduler_status.py) | 189 | `AxeStatus`, `CycleResult`, `AxeMetrics`, pid/status/cycle/metrics/output-log functions |
| [_state_scheduler_shared.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/_state_scheduler_shared.py) | 335 | Error-interval state and helpers under public names (lock, counter/ring loaders, pending buffers, `record_counter_write_failure`, …); file-local helpers kept `_private` |
| [_state_scheduler_errors.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/_state_scheduler_errors.py) | 181 | `append_error`, `read_errors`, `read_error_counts` |
| [_state_scheduler_digests.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/_state_scheduler_digests.py) | 191 | `rotate_error_interval`, `mark_error_digest_sent`, digest-ts functions |

No `_`-prefixed name is imported across the new modules; shared helpers got public names in the already-private shared module, and helpers used by only one module (`_evict_ring_fair`, `_snapshot_interval`, …) moved into that module. `src/sase/axe/state.py` is untouched — its import list still resolves through the facade. The two test files were retargeted: private-buffer resets and `ERROR_*` constants now address `_state_scheduler_shared`, the `write_json_value_atomic` failure patch targets `_state_scheduler_errors`, and fixture writes go through `sase.core.atomic_json` directly.

One real bug surfaced by the split and fixed: `from shared import pending_write_failures` copied the immutable int, so the errors module would have bumped its own copy instead of shared state. All cross-module buffer mutation now happens inside shared-module functions (`record_counter_write_failure`, `bump_write_failures`, …).

**Verification:** `just _lint-mypy` clean; `just _lint-toobig` passes (only informational notes on untouched files); `just _lint-symvision` flags only pre-existing `LaunchPromptContext` in an untouched file. `sase tool run check -k` passes everything except that same symvision item and 5 test failures; all 5 reproduce on the stashed pristine base (agents_sync `remaining_timeout` TypeError, 2 bootstrap-error tests, macro terminology, artifact-dir audit), so they are pre-existing and unrelated. The 17 tests covering the split pass, and the checkout is one commit behind `origin/master` — that commit touches only doctor/publication files, none of which this split touched.

Declaration accepted for the `commit` finalizer.
