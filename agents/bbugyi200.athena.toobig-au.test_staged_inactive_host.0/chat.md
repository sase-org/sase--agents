# Chat History - ace-run (toobig-au.test_staged_inactive_host.0)

- **TIMESTAMP:** 2026-11-27 21:43:29 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-au.test_staged_inactive_host.0

## Prompt

%auto
%id(test_staged_inactive_host.0, clan=toobig-au)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_staged_inactive_host.py` file into multiple files? Use your best
%wait:toobig-au.cli_work_from_plan_launch.0
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

I'll start by reading the split constraints, the test file, and the lint/memory notes so the split stays under 500 lines without breaking imports.

I'll read the rest of the test file, the lint notes, and similar splits so the new modules follow existing conventions.

I'll inspect similar test-package splits and the rest of this 1366-line file so the new modules stay under 500 lines.

I'll map the test functions and helpers, then look at a recent split package to match that layout.

I'll convert the original module into a facade and move tests into focused private modules with shared public helpers.

`just fmt` is still running; I’ll wait for it to finish before the lint gates.

I'll run the three lint gates next, each as its own command.

The three lints passed. I'll collect and run the split tests next, then start `sase tool run check`.

Collection still uses the original module path. I'll run `sase tool run check` inline next.

Check failed on one NEW scoped test. I'll inspect that failure and confirm the split tests themselves passed.

The TUI GC test passed on rerun, so that check failure is a flake. I'll look up the named owner bead and confirm the split tests themselves pass.

Split `tests/test_staged_inactive_host.py` (1366 lines) into a facade plus focused private modules, each under 500 lines. The original import path and pytest node ids stay the same.

**Layout**
- `tests/test_staged_inactive_host.py` — public collection facade; re-exports all 36 `test_*` names
- `tests/_staged_inactive_host_helpers.py` — shared public helpers (`artifact_dir`, `write_monitor_stage`, …)
- `tests/_test_staged_inactive_host_stranded.py` — stranded collector / origin reporting
- `tests/_test_staged_inactive_host_settlement.py` — settlement eligibility and admission
- `tests/_test_staged_inactive_host_owner.py` — lane, pending owner, cleanup
- `tests/_test_staged_inactive_host_recovery.py` — readopt, tool-run, join reservation
- `tests/_test_staged_inactive_host_reconcile.py` — reconcile and finalize-loop

Helpers used by more than one module have public names in the already-private helpers module. Single-module helpers stay private in that module. No `_`-prefixed names are imported across files.

**Verification**
- `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all passed
- 36 tests collected from `tests/test_staged_inactive_host.py`; all 36 passed
- `sase tool run check` (`dc0e9a511821239fc5435565327b26c9`): every lint stage passed; scoped tests were 63887 passed, 1 NEW flake in `tests/ace/tui/test_refresh_warmup_gc.py::test_auto_refresh_merge_live_hints_and_warmup_release_obsolete_payloads` (leftover `FinalizerInventoryWorkerResult`). Isolated rerun of that node passed. It is already tracked as `sase-1v2`; I did not +1 it because triage already named that bead as the possible owner.
