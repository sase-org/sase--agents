# Chat History - ace-run (toobig-23.split_file.tests.test_bead.test_project.0)

- **TIMESTAMP:** 2026-08-08 23:15:18 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-23.split_file.tests.test_bead.test_project.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260808_212010.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.test_bead.test_project.0, clan=toobig-23)
%wait:toobig-23.split_file.tests.test_artifact_ref_preprocessing.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_bead/test_project.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I’ll first map the test file’s structure and fixtures, then split it along behavioral boundaries while preserving imports and test collection. Afterward I’ll run focused tests plus the required repository checks.

The file divides cleanly into three areas: core create/read/update behavior, lifecycle mutations (close/remove/readiness), and storage/initialization/counter behavior. I’ll keep `test_project.py` for the core API and move the other two groups into focused modules, with one shared fixture in the existing bead-test `conftest.py`.

The split now preserves all 63 original tests exactly once, and the three resulting modules are 261, 218, and 237 lines. I’m moving into verification now: dependency install, focused pytest collection/execution, then the repository’s full scoped check.

The split itself is complete and structurally clean. The required install is rebuilding the local Rust/Python binding in this fresh workspace; once that finishes, the actual test runs should be comparatively quick.

Focused verification passes: all 63 tests were collected across the three modules and all 63 passed. I’m running the required repository check now, which will cover formatting/lint/type gates and the diff-selected test lane.

All static gates have passed, including formatting, Ruff, mypy, Symvision, and file-size checks. The remaining part of `just check` is the selected test lane; it is still running without failures so far.

Split the 713-line test module into:

- [test_project.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_bead/test_project.py) — core API tests, 261 lines
- [test_project_lifecycle.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_bead/test_project_lifecycle.py) — close/remove/readiness tests, 218 lines
- [test_project_storage.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_bead/test_project_storage.py) — initialization, persistence, doctor, and counter tests, 237 lines

Moved the shared `project` fixture into [conftest.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_bead/conftest.py:43).

Verification:

- All 63 original tests preserved and passing
- `just check` passed, including formatting, linting, mypy, Symvision, size checks, and scoped tests

The requested split and verification are already complete; the finalizer now requires committing those four test-file changes. I’m using the `sase_git_commit` skill to create the scoped commit exactly as requested.

The commit scope matches the completed refactor: one shared fixture, the reduced core module, and the two new lifecycle/storage modules. All three test modules remain below 500 lines.

Split and committed the project tests:

- Core API: `test_project.py` — 261 lines
- Lifecycle behavior: `test_project_lifecycle.py` — 218 lines
- Storage behavior: `test_project_storage.py` — 237 lines
- Shared fixture moved to `conftest.py`

All 63 tests and `just check` passed.

Commit: `1b77908e4 test(bead): split project tests by concern`
