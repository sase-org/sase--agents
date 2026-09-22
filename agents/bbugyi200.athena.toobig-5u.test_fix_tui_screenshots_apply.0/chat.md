# Chat History - ace-run (toobig-5u.test_fix_tui_screenshots_apply.0)

- **TIMESTAMP:** 2026-09-22 17:16:10 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5u.test_fix_tui_screenshots_apply.0

## Prompt

%id(test_fix_tui_screenshots_apply.0, clan=toobig-5u)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/test_fix_tui_screenshots_apply.py` file up into multiple files? Use your best
%wait:toobig-5u.visual_maintenance_salvage.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 746-line `tests/test_fix_tui_screenshots_apply.py` is now three files, each well under 500 lines, with all 18 test functions preserved byte-for-byte (verified via AST comparison):

- [tests/test_fix_tui_screenshots_apply_basic.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/test_fix_tui_screenshots_apply_basic.py) (248 lines) — happy-path outcomes: clean noops, missing-golden creation, pixel mismatch, encoding-only, dimension-only, stale removal, targeted runs.
- [tests/test_fix_tui_screenshots_apply_failures.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/test_fix_tui_screenshots_apply_failures.py) (270 lines) — skipped/failed runs: pytest failure, zero tests, unstable verification, dirty-before state, concurrent edits, check-mode without verification.
- [tests/test_fix_tui_screenshots_apply_recovery.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/test_fix_tui_screenshots_apply_recovery.py) (297 lines) — apply robustness: report-before-apply, write-failure rollback, journal recovery, journal conflict, and the `apply_changes` unit test.

Each file carries only the imports it uses, and the shared `_manifest` helper is duplicated per file (matching the existing convention of self-contained test modules sharing `tests/_fix_tui_screenshots_helpers.py`).

Verification: all 18 tests pass in the project venv (6.84s), `tests/test_test_shards.py` passes (33 passed), so the committed `shard_timings.json` needs no update — unknown new files fall back to the default duration and coverage stays at ~100%. `just fmt`, `ruff`, and `mypy` are clean. One note: `sase tool run check` fails on a pre-existing `symvision` finding (`delete_paths_in_background` in `src/sase/_linked_repo_workspaces.py`), a file this change does not touch — left alone as out of scope.
