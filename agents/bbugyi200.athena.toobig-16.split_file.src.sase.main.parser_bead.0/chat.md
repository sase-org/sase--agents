# Chat History - ace-run (toobig-16.split_file.src.sase.main.parser_bead.0)

- **TIMESTAMP:** 2026-07-30 16:50:38 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-16.split_file.src.sase.main.parser_bead.0

## Prompt

#gh:sase-org/sase
%id:toobig-16.split_file.src.sase.main.parser_bead.0
%clan(toobig-16, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 756  src/sase/main/parser_bead.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/main/parser_bead.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I’ll map the parser’s responsibilities and its call sites first, then split along cohesive boundaries while preserving the current public API. I’ll keep each resulting module under 500 lines and finish with the repository’s full check.

The file is one 762-line registration function, with no hidden runtime logic. I’m going to turn `parser_bead.py` into a stable facade and group registrations into three modules: issue lifecycle, querying/inspection, and relationships/store operations. That keeps imports unchanged for existing callers and gives each module a clear ownership boundary.

The split is now in place: the facade is 73 lines, and the largest extracted module is 307 lines. I’ve also preserved the original subcommand registration order and the existing `parser_bead.nonnegative_int` import surface; next I’m checking exact parser/help equivalence before running the full suite.

The required local install is rebuilding the Rust-backed dependency for this fresh workspace, so verification is still in progress. The refactor itself is complete; no unrelated files were touched.

The old and new implementations produce byte-for-byte identical help across all 33 parser nodes, including nested `dep`, `pages`, and `ref` commands. Formatting kept every extracted file below 300 lines; I’m starting the mandated full repository check now.

All code-quality gates passed, including mypy, Symvision, and the file-size check. The full check then stopped on two pre-existing external validation issues: stale generated provider skill files and a missing plan-link target under `202607/prompts`. I won’t mutate those unrelated areas; I’m isolating the parser tests and final diff instead.

The standalone full test suite is healthy so far—roughly three quarters of 24,510 tests have passed. This bypasses only the unrelated validation step that blocked `just check`; it exercises the actual codebase normally.

The full suite completed successfully: 24,504 passed and 7 skipped. I’m doing the final worktree audit now; the only incomplete gate remains the unrelated SASE metadata validation reported earlier.

Implemented the split. All resulting files are under 300 lines:

- [parser_bead.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/parser_bead.py) — stable 73-line facade
- [parser_bead_lifecycle.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/parser_bead_lifecycle.py) — lifecycle commands
- [parser_bead_queries.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/parser_bead_queries.py) — read-only commands
- [parser_bead_store.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/parser_bead_store.py) — store and relationship commands
- [parser_bead_common.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/parser_bead_common.py) — shared validation helper

Verification:

- Parser/help output matches the original across all 33 parser nodes.
- Full suite: 24,504 passed, 7 skipped.
- Formatting, Ruff, mypy, Symvision, and file-size checks passed.
- `just check` was blocked only by unrelated existing SASE validation issues: stale generated skill files and a missing plan-link target.

The refactor changes are mine, so I’m using the `sase_git_commit` workflow now to commit exactly those five parser files, as required by the finalizer.

The staged scope is clean: one facade plus four focused parser modules, with no unrelated worktree files included. I’m committing it as a behavior-preserving CLI refactor.

Committed and pushed the parser split:

`3b6f58960 refactor(cli): split bead parser registrations`

The worktree is clean and synchronized with `origin/master`.
