# Chat History - ace-run

- **TIMESTAMP:** 2026-07-19 01:56:01 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** split_file.src.sase.ace.tui.widgets.artifacts.plans_data.282e52fa-0

## Prompt

#gh:sase-org/sase
%name:split_file.src.sase.ace.tui.widgets.artifacts.plans_data.282e52fa-@
%tribe:chop
%wait:split_file.src.sase.ace.tui.widgets.artifacts.commits_pane.3abf0379-0
%auto Can you help me split the `src/sase/ace/tui/widgets/artifacts/plans_data.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I’ll inspect the module’s responsibilities and imports first, then split it along natural boundaries while preserving its public API. Afterward I’ll run focused tests plus the required `just install` and `just check`.

The file has three clean seams: immutable data models, linked-plan document loading, and project/proposal/archive sources. I’m also accounting for tests that monkeypatch private names on `plans_data`; the orchestration module will keep importing those names directly so that compatibility remains intact.

The split is now four focused modules, all between 111 and 313 lines. The original import surface is preserved, including monkeypatchable loader hooks; I’m moving into formatting and regression checks now.

`just install` is doing a first-time rebuild of the linked Rust core in this workspace, so it’s taking a little longer than the Python-only checks. The refactored modules already compile; once installation finishes I’ll run the Plans data/link-document tests and the full repository check.

Focused coverage is green: 71 tests passed, including multi-project snapshots, cache invalidation, archive merging, linked-document parsing, and the preserved monkeypatch hooks. I’m running the repository-wide required check now; any remaining work should be limited to static-analysis cleanup.

The full check found one structural issue: Symvision forbids importing underscore-prefixed symbols across production modules. I’m using the required `sase_memory_read` guidance for Symvision now, then I’ll rename the new cross-module interfaces to public internal APIs while retaining the old names on `plans_data` for compatibility.

The skill requires an audited long-term-memory read rather than opening the memory note directly; I’m following that workflow before changing the symbol layout.

The Symvision-specific naming cleanup is complete and its lint now passes. The compatibility façade still exposes the original private names, but the actual cross-file interfaces are explicitly public, which matches the repository’s symbol rules. I’m rerunning behavior tests and then the complete check from scratch.

All formatting, static analysis, Symvision, size limits, and SASE validation have passed in the full check. The remaining stage is the repository’s complete test suite, which is still running without failures so far.

The full suite is in its slower buffered pytest phase; there’s no failure output, and the process remains active. I’ll let it finish and then do one final diff/status review for accidental changes.

Split `plans_data.py` into four focused modules while preserving its existing import and monkeypatch surface:

- [plans_data.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/artifacts/plans_data.py) — orchestration and compatibility façade, 296 lines
- [plans_data_models.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/artifacts/plans_data_models.py) — immutable data models, 111 lines
- [plans_data_sources.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/artifacts/plans_data_sources.py) — project, proposal, bead, and archive loading, 313 lines
- [plans_data_documents.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/artifacts/plans_data_documents.py) — linked-plan resolution and parsing, 221 lines

The Symvision guidance shaped the cross-module interfaces while compatibility aliases preserve existing callers.

Validation passed:

- 71 focused Plans tests
- Full `just check`, including formatting, Ruff, mypy, Symvision, size checks, validation, and complete tests

The refactor changes are mine from this session, so I’m using the `sase_git_commit` skill now to commit exactly those four files with the required create-commit workflow.

The commit scope is clean: one refactor-only change, with the existing `plans_data` module retained as the compatibility façade and the three new modules holding models, data sources, and linked-document logic. I’m committing those exact paths now.

Committed the four-file refactor as:

`63dc8c6d2 refactor(ace): split plans data module`

The working tree is clean and synchronized with `origin/master`.
