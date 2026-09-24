# Chat History - ace-run (toobig-5y.test_plugins_browser_rows.0)

- **TIMESTAMP:** 2026-09-23 20:54:54 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5y.test_plugins_browser_rows.0

## Prompt

%id(test_plugins_browser_rows.0, clan=toobig-5y)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/test_plugins_browser_rows.py` file up into multiple files? Use your best
%wait:toobig-5y.test_agent_tribe_assignment.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 794-line `tests/ace/tui/test_plugins_browser_rows.py` into four files, all well under 500 lines:

- [tests/ace/tui/_plugins_browser_rows_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/_plugins_browser_rows_helpers.py) (187 lines) — shared factories (`_entry`, `_core_package`, CLI status builders, `_load_result`, plus `_installable_cli_status`/`_cli_row` moved up from the install section), following the repo's `_helpers` convention
- [tests/ace/tui/test_plugins_browser_rows_build.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/test_plugins_browser_rows_build.py) (247 lines, 14 tests) — row building, plugin/agent-CLI capabilities, error field, haystack
- [tests/ace/tui/test_plugins_browser_rows_labels.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/test_plugins_browser_rows_labels.py) (143 lines, 10 tests) — version labels and dev-state labels
- [tests/ace/tui/test_plugins_browser_rows_scopes.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/test_plugins_browser_rows_scopes.py) (285 lines, 13 tests) — select/scope filtering, install routes, available scope

No test logic changed — I diffed the sorted test names before/after (identical, 37 total) and the original file is deleted. Verified with the project venv: all 37 tests pass, and `ruff check` plus `ruff format --check` pass on all four files.

Declaration submitted — commit authorized for the test split work.
