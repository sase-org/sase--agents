# Chat History - ace-run (toobig-5y.test_install.0)

- **TIMESTAMP:** 2026-09-23 21:47:20 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5y.test_install.0

## Prompt

%id(test_install.0, clan=toobig-5y)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/agent_clis/test_install.py` file up into multiple files? Use your best
%wait:toobig-5y.test_agent_jump_panel.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split `tests/agent_clis/test_install.py` (794 lines) into four files, all under 500 lines:

- [install_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/agent_clis/install_helpers.py) (147 lines) — shared constants (`SCRIPT_BODY`, `SCRIPT_DIGEST`, `SCRIPT_URL`) and helpers (`_FakeResponse`, `_urlopen`, `_status`, `_npm_status`, `_npm_bin`, `_npm_probe`, `_never_run`, `_script`, `_fetch`), moved verbatim; test files import via `from .install_helpers import ...`, matching the existing `tests/file_hook_engine/helpers.py` convention.
- [test_install_fetch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/agent_clis/test_install_fetch.py) (59 lines) — 5 fetch tests.
- [test_install_plan.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/agent_clis/test_install_plan.py) (274 lines) — 14 plan/classifier/npm-plan/cleanup tests.
- [test_install_execute.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/agent_clis/test_install_execute.py) (375 lines) — 12 execute/install-dir/PATH tests.

Test bodies are unchanged; verified all 31 test names match the original set exactly.

Verification: all 31 split tests pass, and the full `tests/agent_clis/` suite passes (128 passed). `just fmt`, keep-sorted, and ruff pass. One note: `just check` fails at the mypy gate on `src/sase/ace/tui/widgets/file_panel/_content.py` (`FilePanelContentMixin has no attribute parent`), a file this change doesn't touch — that failure is pre-existing and unrelated.
