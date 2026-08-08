# Chat History - ace-run (toobig-1r.split_file.tests.test_test_selection_contexts.0)

- **TIMESTAMP:** 2026-08-06 17:17:02 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-1r.split_file.tests.test_test_selection_contexts.0

## Prompt

#gh:sase-org/sase
%id:toobig-1r.split_file.tests.test_test_selection_contexts.0
%clan(toobig-1r, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 806  tests/test_test_selection_contexts.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_test_selection_contexts.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I'll create the shared helper module and the five split test files.

Now the baseline resolution + breadth file:

Now the selection-behavior file:

Now remove the original file and update the stale cross-reference in `test_test_selection.py`:

All 42 tests carried over (58 collected with parametrization). Now the repo gates:

All 51 are the same fixture-shadowing issue. I'll register the fixtures under distinct function names so the parameters don't shadow the imports.

Split done — `tests/test_test_selection_contexts.py` (806 lines) is now five topic files plus a shared helper module, all well under 500 lines:

| File | Lines | Contents |
|---|---|---|
| `tests/_test_selection_contexts_helpers.py` | 79 | `repo`/`contexts_dir` fixtures, `head`, `store_for`, `add_dynamic_pair`, `select` |
| `tests/test_test_selection_contexts_diff.py` | 154 | diff → baseline-side lines, and reading rows out of the database |
| `tests/test_test_selection_contexts_baseline.py` | 242 | baseline resolution + breadth ranking/pruning |
| `tests/test_test_selection_contexts_selection.py` | 204 | what a resolved baseline contributes to a selection |
| `tests/test_test_selection_contexts_depth_boost.py` | 107 | no-baseline / stale-baseline depth compensation |
| `tests/test_test_selection_contexts_reporting.py` | 119 | `consulted` bookkeeping + the `context_line` summary |

Notes on the mechanics:

- All 42 test functions (58 with parametrization) moved unchanged; the run is green.
- The shared fixtures register under `name="repo"` / `name="contexts_dir"` but are defined as `repo_fixture` / `contexts_dir_fixture`, so importing them for discovery doesn't collide with the parameter names — importing them under their fixture names tripped 51 ruff `F811` errors.
- Dropped the module-local `_write_baseline` alias in favor of calling `write_contexts_baseline` directly; its comment claimed it was shared with `tests/test_test_selection.py`, which is stale (that file uses `install_fresh_baseline`).
- Section banner comments became module docstrings, and the one cross-reference to the old filename in `tests/test_test_selection.py:79` now points at `..._depth_boost.py`.

`just check` passes (all lint gates + scoped tests). Since this touches test-selection tests, `just check-full` before landing is the safer call — say the word and I'll run it.

I made these changes. Committing them now.

123 passed. Now the commit.

Committed as `2e6ba3dff`, working tree clean and in sync with `origin/master`.

**The split:** `tests/test_test_selection_contexts.py` (806 lines) → five topic modules plus a shared helper module, all under 500 lines:

| File | Lines | Contents |
|---|---|---|
| `_test_selection_contexts_helpers.py` | 79 | `repo`/`contexts_dir` fixtures, `head`, `store_for`, `add_dynamic_pair`, `select` |
| `..._diff.py` | 154 | diff → baseline-side lines, and reading rows out of the database |
| `..._baseline.py` | 242 | baseline resolution + breadth ranking/pruning |
| `..._selection.py` | 204 | what a resolved baseline contributes to a selection |
| `..._depth_boost.py` | 107 | no-baseline / stale-baseline depth compensation |
| `..._reporting.py` | 119 | `consulted` bookkeeping + the `context_line` summary |

**Mechanics worth knowing:**
- All test functions moved unchanged. Shared fixtures are defined as `repo_fixture`/`contexts_dir_fixture` and registered under `name="repo"`/`name="contexts_dir"`, so importing them for discovery doesn't shadow the parameter names (importing them under the fixture names tripped 51 ruff `F811` errors).
- Dropped the module-local `_write_baseline` alias for direct `write_contexts_baseline` calls — its comment claimed it was shared with `test_test_selection.py`, which was stale.
- The cross-reference at `tests/test_test_selection.py:79` now points at `..._depth_boost.py`.

**Verification:** the venv was stale, so I re-ran `just install` first. All 123 tests across the six files pass. The commit's `just fix` pre-hook ran clean. I did not run the full `just check-full` this pass — since this touches test-selection tests, that's the safer gate before landing anything downstream.
