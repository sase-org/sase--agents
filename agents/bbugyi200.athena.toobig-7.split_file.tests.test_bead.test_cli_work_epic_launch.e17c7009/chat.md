# Chat History - ace-run

- **TIMESTAMP:** 2026-07-20 19:40:05 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-7.split_file.tests.test_bead.test_cli_work_epic_launch.e17c7009
- **PROMPT:** `~/.sase/multi_prompts/202607/sase_org_sase-multiprompt-260720_183501.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.test_bead.test_cli_work_epic_launch.e17c7009, clan=toobig-7)
%wait:toobig-7.split_file.tests.test_axe_run_agent_runner_deferred_workspa.fcfb4a7f
%auto %wait(priority=20) Can you help me split the `tests/test_bead/test_cli_work_epic_launch.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I’ll inspect the test module’s structure and fixtures, then split it along behavioral boundaries while keeping collection semantics intact. Afterward I’ll run the focused tests and the repo-required `just check`.

The module is 413 lines, but it contains three distinct concerns: the initial launch contract, successful relaunch/name-reuse paths, and cleanup failure handling. I’m separating those into three focused modules; this keeps each well below the target without introducing shared abstractions just for the split.

The split is now 135, 181, and 133 lines. Test bodies are unchanged; only module-level imports and descriptions were adjusted for their new homes. I’m installing this workspace’s current dev dependencies before validation, as required by the repository workflow.

Dependency setup is still compiling the linked Rust core for this fresh workspace; no errors so far. Once it finishes, I’ll run the three affected modules together so pytest collection also verifies the move.

All nine moved test cases pass in their new modules. I’m running the full repository check now to catch formatting, typing, and any collection issues outside the focused set.

Formatting, Ruff, mypy, Symvision, size checks, and SASE validation have all passed. The remaining full test phase is still running.

Split the test suite into three focused modules:

- [test_cli_work_epic_launch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_cli_work_epic_launch.py) — launch contract, 135 lines
- [test_cli_work_epic_relaunch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_cli_work_epic_relaunch.py) — relaunch/name reuse, 181 lines
- [test_cli_work_epic_launch_cleanup.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_cli_work_epic_launch_cleanup.py) — cleanup failures, 133 lines

Validation passed:

- Focused tests: 9 passed
- Full `just check`: passed
- `git diff --check`: clean

The listed changes are the split completed in this session, so the finalizer requires me to commit them. I’m using the `sase_git_commit` workflow with only those three test files included.

The diff is limited to moving the existing nine tests into launch-contract, relaunch, and cleanup modules. I’m committing exactly those files with a test-only conventional commit.

Committed the test split:

`07dba8941 test: split epic work launch tests`

The working tree is clean and synchronized with `origin/master`.
