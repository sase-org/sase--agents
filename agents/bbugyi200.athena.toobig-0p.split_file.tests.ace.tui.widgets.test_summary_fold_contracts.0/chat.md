# Chat History - ace-run (toobig-0p.split_file.tests.ace.tui.widgets.test_summary_fold_contracts.0)

- **TIMESTAMP:** 2026-07-28 10:55:48 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-0p.split_file.tests.ace.tui.widgets.test_summary_fold_contracts.0
- **PROMPT:** `~/.sase/multi_prompts/202607/sase_org_sase-multiprompt-260728_095437.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.ace.tui.widgets.test_summary_fold_contracts.0, clan=toobig-0p)
%wait:toobig-0p.split_file.tests.ace.tui.widgets.test_agent_slow_tools.0
%auto %wait(priority=20) Can you help me split the `tests/ace/tui/widgets/test_summary_fold_contracts.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I’ll map the test file’s sections and shared fixtures first, then split it along behavioral boundaries while preserving imports and test discovery. I’ll keep each resulting file at or under 500 lines and run the targeted tests plus the required full check.

The file naturally divides into two independent contract suites: cross-kind summary behavior (family/clan/tribe) and lane-header behavior (neighbors/slow tools). I’m checking the surrounding test naming conventions before extracting shared builders, so the split stays easy to navigate and doesn’t introduce a generic helper module unnecessarily.

The split is now in place: the original file owns family/clan/tribe document contracts, while neighbors and slow-tool lane contracts have focused test modules. Shared construction/rendering code lives in one private helper to avoid duplicating the family setup. I’m validating collection, line counts, and that the move didn’t alter the test set.

The workspace dependencies are being rebuilt because this checkout’s environment was stale; the split itself is complete and all four touched files are comfortably below the 500-line target (378, 229, 156, and 124 lines). Once installation finishes I’ll run the three focused modules, then the repository-wide check.

All 27 parametrized cases pass after the move, matching the original suite’s coverage. I’m starting the mandatory full repository check now; this is the final verification pass.

The full check found only two Ruff line-wrap differences in the newly moved code. I’m applying the formatter to those files and will rerun the complete check.

Formatting and all lint stages passed. The full check is blocked by three existing SDD plan-link validation errors in `plan_header_provenance.md` and its prompt links, outside this test-only change. I’m doing a final targeted rerun and diff review so I can separate the verified split from that unrelated repository validation issue.

Split the 805-line test module into focused files:

- [test_summary_fold_contracts.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/ace/tui/widgets/test_summary_fold_contracts.py) — 376 lines
- [test_summary_fold_lane_neighbors.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/ace/tui/widgets/test_summary_fold_lane_neighbors.py) — 229 lines
- [test_summary_fold_slow_tools.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/ace/tui/widgets/test_summary_fold_slow_tools.py) — 156 lines
- [_summary_fold_contract_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/ace/tui/widgets/_summary_fold_contract_helpers.py) — 123 lines

Verification:

- All 27 targeted tests pass.
- Formatting, Ruff, mypy, Symvision, and size checks pass.
- `just check` reaches SASE validation but is blocked by three unrelated existing plan-link errors involving `plan_header_provenance.md`.

The listed files are the completed split from this session, so the finalizer requires me to commit them. I’m using the `sase_git_commit` skill now with those four files explicitly scoped.

The commit was created successfully; the wrapper is still finishing its post-commit checks and push bookkeeping. I’m waiting for that to complete, then I’ll verify the branch is clean and synchronized.

Committed and pushed the test split:

- Commit: `973445674 test: split summary fold contract suites`
- Working tree is clean and synchronized with `origin/master`.
- The commit wrapper noted three pre-existing quarantined publication requests; they did not affect the commit.
