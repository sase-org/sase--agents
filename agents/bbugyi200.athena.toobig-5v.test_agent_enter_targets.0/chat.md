# Chat History - ace-run (toobig-5v.test_agent_enter_targets.0)

- **TIMESTAMP:** 2026-09-22 22:17:06 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5v.test_agent_enter_targets.0

## Prompt

%id(test_agent_enter_targets.0, clan=toobig-5v)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/test_agent_enter_targets.py` file up into multiple files? Use your best
%wait:toobig-5v.host.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 884-line `tests/ace/tui/test_agent_enter_targets.py` into a shared helpers module plus four focused test files, with no test logic changed:

- [helpers](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ace/tui/_agent_enter_targets_helpers.py) (201 lines): `_notification`, `_gate_row`, `_resolve`, `_sources`, `_family`, `_remote_agent`, `_EnterApp`
- [scope tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ace/tui/test_agent_enter_targets_scope.py) (165 lines): patch-only, gate-row labels, settled/settling, clan, monitor/proc rows
- [family tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ace/tui/test_agent_enter_targets_family.py) (240 lines): containers, member matching, dedup, ordering
- [legacy tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ace/tui/test_agent_enter_targets_legacy.py) (122 lines): HITL/question markers, remote attention, label table, notification index
- [executor tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ace/tui/test_agent_enter_targets_executor.py) (210 lines): dispatch, toasts, async detail fallback, snapshot caching

Verification: all 63 tests pass before and after the split (confirmed via stash comparison); `just fmt`, ruff, and mypy pass. Note: `just check` reports a symvision failure on `src/sase/_linked_repo_workspaces.py::delete_paths_in_background`, which I confirmed also fails on the clean tree, so it is pre-existing and unrelated to this change.
