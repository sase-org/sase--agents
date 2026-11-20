# Chat History - ace-run (toobig-a8.test_launchable_mru.0)

- **TIMESTAMP:** 2026-11-19 19:24:28 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** toobig-a8.test_launchable_mru.0

## Prompt

%auto
%id(test_launchable_mru.0, clan=toobig-a8)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/test_launchable_mru.py` file into multiple files? Use your best
%wait:toobig-a8.state_scheduler.0
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

I’ll inspect the test module and nearby conventions, then split it along its natural test groups while preserving the original import path and patch targets. I’ll run each requested lint command separately, fix findings in the touched files, then run `sase tool run check`.

The module has four clear groups: snapshot data building, background refresh and freshness triggers, prompt cycling, and project identity warming. I’ll keep `test_launchable_mru.py` as the pytest collection facade, with the test bodies in private modules and shared public helpers in one private helper module. That keeps the import path and monkeypatches intact without importing private symbols across modules.

The split is in place: the original module now re-exports the same 21 test functions, while the shared helper names are public inside a private helper module. All six resulting files are under 500 lines. I’m checking the requested lints now; after that I’ll run the wrapped project check as requested.

The requested `mypy` and line-count checks pass. `symvision` reports two pre-existing unused symbols in `src/sase`; none of the split test files are in its scan. I’m formatting and linting only the changed Python files next, so the final check can focus on any remaining issues in this split.

The facade collects all 20 original tests under the original `test_launchable_mru.py` node IDs. The touched files also pass Ruff. I’m reviewing the final diff and the required check’s run guidance before launching that last gate.

The final review confirms the split preserves the original test names and node IDs; all six files stay below 500 lines. The check recipe includes the same `symvision` stage that surfaced two unrelated existing symbols in `src/sase`, so I’ll leave those untouched and verify that every finding in the changed test files is resolved.

The final `symvision` rerun reports the same two untouched source findings; `mypy` and `toobig` pass. I’m starting the requested `sase tool run check` now.

The check has passed formatting, keep-sorted, Ruff, mypy, feature flags, and Python script validation. It’s continuing through the remaining lint stages and scoped test lane.

The wrapped check stopped at `symvision`, before the scoped test lane. Its failure is limited to `LaunchPromptContext` (classified NEW) and `OutboxGroup` (classified KNOWN), both in untouched source files. I’ll run the split module’s 20 tests directly so the behavior is exercised despite the check stopping early, then record the independent lint finding per this repo’s task workflow.

The focused test run passed all 20 tests. I’m recording the separate NEW `LaunchPromptContext` symvision finding now; the other finding was classified KNOWN by triage.

The independent finding is recorded as ready task `sase-1u3` with a source snapshot attached. The split’s focused tests pass; I’m doing the final workspace review and then handing the repository change to SASE completion.

All 20 tests passed through `sase tool run test -- tests/ace/tui/test_launchable_mru.py`. The requested `sase tool run check` ran but stopped at the unrelated NEW `LaunchPromptContext` symvision finding; `OutboxGroup` was KNOWN. I’ve recorded the NEW finding as `sase-1u3`. I’m submitting the completed test split for host finalization now.

Split the 20 tests into focused build, refresh, cycling, and identity modules, with shared helpers in a private module. The original [test module](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_launchable_mru.py) remains a facade, preserving the test names and collection paths. Every resulting file is under 500 lines; the largest is 210.

**Verification:** the focused test run passed all 20 tests. `just _lint-mypy` and `just _lint-toobig` passed. `sase tool run check` stopped at `symvision`: it reported `LaunchPromptContext` as NEW and `OutboxGroup` as KNOWN in untouched source files, before reaching the scoped test lane. The NEW finding is recorded in ready task `sase-1u3`.

SASE accepted the commit declaration; the host will commit the changes after this turn.
