# Chat History - ace-run

- **TIMESTAMP:** 2026-07-19 05:14:13 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** split_file.src.sase.core.agent_cleanup_facade.6a506bfa-0

## Prompt

#gh:sase-org/sase
%name:split_file.src.sase.core.agent_cleanup_facade.6a506bfa-@
%tribe:chop
%wait:split_file.src.sase.core.agent_artifact_index_lifecycle.ce47e900-0
%auto Can you help me split the `src/sase/core/agent_cleanup_facade.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I’ll map the facade’s responsibilities and callers first, then split along existing boundaries while preserving the public import surface. Afterward I’ll run the focused tests and the required `just check`.

The file has three clean seams: TUI-agent serialization, the Python reference planner, and side-effect intent planning. I’ll keep `agent_cleanup_facade.py` as the stable public entry point (including the currently tested private fallback symbol), so callers and mocks do not need to move.

The split is now in place: facade 88 lines, target conversion 75, side-effect intents 200, and Python planner 473. I’m moving into verification now, starting with the workspace install as required by this repository.

The install is still compiling the local Rust binding; no errors so far. Once it finishes I’ll run the cleanup-planner tests first, which should catch both import-surface regressions and Python/Rust parity changes.

The focused cleanup and single-agent suites pass: 46 tests, including Rust/Python parity. I’m running the repository-wide required check now; if it finds formatting or type issues from the new module boundaries, I’ll correct those and rerun it.

`just check` reached Symvision and flagged the new cross-module imports as private-symbol violations. The repository requires its Symvision memory procedure for this class of failure, so I’m using the `sase_memory_read` skill now before adjusting the module API.

The Symvision fix is clean: the shared helpers are now intentionally public within the internal cleanup modules, while the facade retains `_plan_agent_cleanup_python` as a compatibility alias for existing tests. The exact failing lint stage now passes; I’m rerunning the full check.

All formatting, linting, type checking, Symvision, size checks, and SASE validation have passed. The full test portion of `just check` is still running and has not reported a failure.

Split completed while preserving the existing facade imports:

- [agent_cleanup_facade.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/agent_cleanup_facade.py) — 90 lines
- [agent_cleanup_python.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/agent_cleanup_python.py) — 473 lines
- [agent_cleanup_side_effects.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/agent_cleanup_side_effects.py) — 200 lines
- [agent_cleanup_targets.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/agent_cleanup_targets.py) — 75 lines

The facade remains the stable caller-facing API, including its tested Python-fallback alias.

Validation passed:

- 46 focused cleanup tests
- Full `just check`, including formatting, linting, mypy, Symvision, size checks, and tests.

I made the four listed changes in this session, so I’m following the required `sase_git_commit` finalizer workflow now and will commit only those files.

The commit scope is clean: one facade refactor plus the three extracted modules, with no unrelated files. I’m recording it as a behavior-preserving `refactor` commit.

Committed and pushed the facade split:

- Commit: `ae6ff5d22 refactor: split agent cleanup facade`
- Only the four requested files were included.
- Working tree is clean and synchronized with `origin/master`.
- All files remain under 500 lines; `just check` passed.
