# Chat History - ace-run (toobig-1b.split_file.tests.test_bead.test_cli_show.0)

- **TIMESTAMP:** 2026-07-31 13:50:22 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-1b.split_file.tests.test_bead.test_cli_show.0

## Prompt

#gh:sase-org/sase
%id:toobig-1b.split_file.tests.test_bead.test_cli_show.0
%clan(toobig-1b, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 726  tests/test_bead/test_cli_show.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_bead/test_cli_show.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I’ll map the test file’s sections and shared helpers, then split it along behavioral boundaries while preserving test discovery and fixtures. Afterward I’ll run the focused tests and the required full check.

The file has four clean seams: parser/contract tests, full-format rendering, compact-format rendering, and JSON/machine-output tests. I’m checking the surrounding test package now so shared fixtures land in the narrowest sensible place and don’t create accidental coupling.

The split is in place: shared setup is centralized, while the original file now owns parser/full-output behavior and two new files own compact and JSON behavior. I’m verifying that every original test survived the move and that each resulting file stays comfortably below 500 lines.

All four show-test support/test files are under 311 lines, and the moved suite still contains all 39 test functions. The workspace dependency install is rebuilding the local Rust binding; once that finishes I’ll run the focused three-file suite, then `just check`.

The focused suite passes: 32 tests, matching the original file’s collected coverage. I’m starting the repository-mandated full validation now; any failures unrelated to this refactor will be separated from actual regressions.

The code-quality checks passed, but `just check` stopped at SASE validation because five generated `sase_beads` provider skill files in the linked chezmoi source are stale. This is outside the test split. Per the project’s discovered-work policy, I’m using the `sase_beads` skill to record that pre-existing maintenance item, then I’ll do a final diff audit.

The `sase_beads` workflow calls for a draft task followed by `ready` status. I’ll record only the stale generated-skill validation issue, without touching those external files.

Split complete. The show tests are now organized by behavior:

- [test_cli_show.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_cli_show.py) — parser/full output, 311 lines
- [test_cli_show_json.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_cli_show_json.py) — JSON output, 270 lines
- [test_cli_show_compact.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_cli_show_compact.py) — compact output, 59 lines
- [cli_show_test_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/cli_show_test_helpers.py) — shared helpers, 58 lines
- Shared nested-store fixture moved into [conftest.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/conftest.py).

Verification:

- All 31 original test functions preserved.
- Focused suite: 32 passed.
- Formatting, Ruff, mypy, Symvision, and size checks passed.
- `just check` stopped on an unrelated stale generated-skills validation issue. Recorded as ready task bead `sase-cm`.

The listed changes are the test split from this session, so I’m using the required `sase_git_commit` workflow to commit exactly those five files.

The diff confirms this is a test-only reorganization with no production changes. I’m committing it as `test:` and limiting staging to the five finalizer-listed files.

Committed and pushed the test split:

`2ce282049 test: split bead show CLI tests by output format`

Working tree is clean and synchronized with `origin/master`.
