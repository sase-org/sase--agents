# Chat History - ace-run (toobig-0v.split_file.tests.test_bead.test_cli_work_epic_lifecycle.0)

- **TIMESTAMP:** 2026-07-29 06:14:40 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-0v.split_file.tests.test_bead.test_cli_work_epic_lifecycle.0
- **PROMPT:** `~/.sase/multi_prompts/202607/sase_org_sase-multiprompt-260729_060114.md`

## Prompt

#gh:sase-org/sase
%id:toobig-0v.split_file.tests.test_bead.test_cli_work_epic_lifecycle.0
%clan(toobig-0v, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 717  tests/test_bead/test_cli_work_epic_lifecycle.py[/#87D7FF]
[#87D7FF]• 706  tests/test_bead/test_cli_work_from_plan_store.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_bead/test_cli_work_epic_lifecycle.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I’ll map the test file’s logical sections and shared helpers first, then split it along behavior boundaries while preserving collection and imports. Afterward I’ll run the focused tests and the repository-required `just check`.

The file divides cleanly into three concerns: pre-launch checkpoint/push behavior, rollback/retry behavior, and input/locking validation. I’m keeping the rollback-focused tests in the original module and extracting the other two groups; each resulting file should land around 200–320 lines.

The split is now 300, 270, and 172 lines, with all 20 original test cases preserved. I’m moving into verification: install/refresh the workspace environment, run the three focused modules together, then run the full required check.

The workspace setup is rebuilding the local Rust/Python binding, which is the slow part of verification; it’s still progressing normally. The file split itself is complete and clean under `git diff --check`.

All 20 moved tests pass together. I’m starting the full repository check now to catch formatting, typing, or unrelated collection issues introduced by the new module boundaries.

The code-quality stages all passed (formatting, Ruff, mypy, scripts, Symvision, and file-size lint). `just check` then stopped at a pre-existing global skill-initialization drift outside this workspace—15 generated provider skill files need regeneration—so I’m leaving that unrelated user state untouched and running the full test suite separately.

The full suite reached 23,334 tests; only two event-loop watchdog timing tests failed under 28-way parallel load, far outside the bead-work area. I’m rerunning those two serially to distinguish load-sensitive flakes from a real regression before wrapping up.

Split the 717-line module into three cohesive files:

- [test_cli_work_epic_checkpoint.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_cli_work_epic_checkpoint.py) — 300 lines
- [test_cli_work_epic_lifecycle.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_cli_work_epic_lifecycle.py) — 270 lines
- [test_cli_work_epic_validation.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_cli_work_epic_validation.py) — 172 lines

All 20 moved tests pass. Formatting, Ruff, mypy, Symvision, and size checks pass.

`just check` remains blocked by unrelated global generated-skill drift. The full suite had two load-sensitive watchdog failures among 23,334 tests; both passed when rerun serially.

The split and verification are complete; the finalizer confirms these are the three files changed in this session. I’m using the required `sase_git_commit` workflow now to commit exactly those files, without touching unrelated workspace state.

The commit itself has been created successfully. The wrapper is finishing its post-commit synchronization; once it returns I’ll verify the branch is clean and not ahead of upstream.

Split the epic lifecycle tests into three files, all under 500 lines. All 20 focused tests pass.

Committed and pushed as:

`232e429f2 test(bead): split epic lifecycle tests`

The working tree is clean and synchronized with `origin/master`.
