# Chat History - ace-run (1db--code)

- **TIMESTAMP:** 2026-11-17 08:11:05 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 1db--code

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202611/axe_missing_script_during_code_swap.md

The above plan has been reviewed and approved. Implement it now.


## Response

Implemented the approved plan in [`202611/axe_missing_script_during_code_swap.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/sase/repos/plans/202611/axe_missing_script_during_code_swap.md). A job whose script vanishes mid code swap is now recorded as a non-advancing `skipped` run and retried, instead of a `missing_script` error reaching the digest.

**Changes** (6 files, `git diff` reviewed, no collateral):

- [`src/sase/dev_update/code_swap_lock.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/dev_update/code_swap_lock.py) — new public `code_swap_writer_holder()` probe: no `flock`, honors the disable env var, requires a live pid (stale payloads read as no swap), never raises. `_display_op` now renders `install.dev`/`install.pypi` as `just install-dev`/`just install`. `prebuild.py` untouched per plan.
- [`src/sase/axe/chop_runner_script.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/axe/chop_runner_script.py) — missing-script branch probes first (probe exceptions fall back to `missing_script`); on a live writer it writes a `skipped` entry with `reason` as both reason and log output, keeps `record_checkpoint_best_effort(..., "action_failed")` so the trigger stays retryable, and returns `advances_cadence=False, skip_reason="inhibited"`. No-swap path is byte-for-byte the old behavior.
- [`src/sase/axe/chop_runner.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/axe/chop_runner.py) — forwards the seam through `run_configured_chop_once`/`_run_script_chop_once` so tests can inject it; defaults need no consumer changes.
- Tests: 6 new probe cases in [`tests/dev_update/test_code_swap_lock.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/tests/dev_update/test_code_swap_lock.py) (live writer, release, empty file, dead pid, malformed JSON, disabled env, installer payload); 2 new runner tests in [`tests/test_axe_chop_runner_script.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/tests/test_axe_chop_runner_script.py) (defer-to-skipped with entry/log assertions, probe-raises fallback). The existing missing-script test is unchanged. No routine-level test: `lumberjack.py`'s `skipped` branch is pre-existing and reads only `reason`/`skip_reason`/`advances_cadence`, as do the CLI and TUI consumers.
- Docs: one sentence in [`scheduler-jobs.md`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/docs/reference/automation/scheduler-jobs.md).

**Two deliberate deviations from the plan's letter** (intent preserved): the plan's top-level `from sase.dev_update.code_swap_lock import ...` eagerly pulls `sase.dev_update/__init__` (update backend) onto the TUI first-paint path and trips the `test_tui_app_import_stays_under_startup_budget` gate — confirmed failing with the top-level import, passing on base. So the probe is a use-site import via `_default_code_swap_writer_holder()`, and the seam default is `None` resolving to it (the repo's prescribed deferral pattern). Everything else follows the plan.

**Verification observed**: `pytest tests/test_axe_chop_runner_script.py tests/dev_update/test_code_swap_lock.py tests/ace/tui/test_app_import_budget.py` → 54 passed; `sase tool run check` (run `79d68d3d…`) → `VERDICT pass`, `EXIT 0`, including mypy, symvision, and the scoped test lane. An earlier full-lane run showed one unrelated flaky timing test (`test_run_supervisor_chatty_command_does_not_hit_idle_timeout`) that passes in isolation.

Declaration submitted: commit for the 6 implemented files.
