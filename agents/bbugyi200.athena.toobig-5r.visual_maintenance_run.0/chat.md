# Chat History - ace-run (toobig-5r.visual_maintenance_run.0)

- **TIMESTAMP:** 2026-09-21 22:36:32 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.visual_maintenance_run.0

## Prompt

%id(visual_maintenance_run.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/visual/_visual_maintenance_run.py` file up into multiple files? Use your best
%wait:toobig-5r.visual_capture_store.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 923-line `_visual_maintenance_run.py` is now four modules, all under 500 lines:

- [run.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/visual/_visual_maintenance_run.py) (435 lines) — `main`, `run_maintenance`, `_run_locked` orchestration only
- [_visual_maintenance_exec.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/visual/_visual_maintenance_exec.py) (197 lines) — governed pytest invocation, determinism verification, pruning guard
- [_visual_maintenance_guards.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/visual/_visual_maintenance_guards.py) (103 lines) — CI refusal, renderer preflight, renderer identity
- [_visual_maintenance_manifest.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/visual/_visual_maintenance_manifest.py) (287 lines) — manifest building, console summary, review-report publishing

Behavior is unchanged: moved helpers got public names in their new homes (`run_pytest`, `verify_changes`, `default_is_ci`, `build_manifest`, …), while `run.py` re-exports the existing import paths (`_default_is_ci`, `build_run_pytest_command`, `print_summary`, `apply_changes`, …) so the façade, the `fix_tui_screenshots` tool, and the existing tests and monkeypatch targets keep working untouched.

Verified with `just fmt`, the 50 visual-maintenance outcome tests (all passed), and `sase tool run check` (all lint gates including symvision/toobig plus diff-scoped tests succeeded). Final declaration submitted and accepted.
