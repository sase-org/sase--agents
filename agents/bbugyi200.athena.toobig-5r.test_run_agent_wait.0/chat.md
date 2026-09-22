# Chat History - ace-run (toobig-5r.test_run_agent_wait.0)

- **TIMESTAMP:** 2026-09-22 02:37:53 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_run_agent_wait.0

## Prompt

%id(test_run_agent_wait.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/test_run_agent_wait.py` file up into multiple files? Use your best
%wait:toobig-5r.test_run_agent_runner_slot_capacity.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 709-line `tests/test_run_agent_wait.py` into three themed modules plus a shared helper, with all 16 test bodies byte-identical (only helper names de-prefixed):

- [tests/_run_agent_wait_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/_run_agent_wait_helpers.py) (69 lines) — shared `patch_index_updates`, `make_waiter`, `make_submitted_planner`, following the repo's `tests/_*_helpers.py` convention
- [tests/test_run_agent_wait_resolved.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_run_agent_wait_resolved.py) (210 lines) — fast-path tests: resolved named wait, submitted plan row, identity exclusion, slow-path marker, time-floor parametrize
- [tests/test_run_agent_wait_blocking.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_run_agent_wait_blocking.py) (310 lines) — blocking tests: bead-only, hood-only, ready-marker arrival, stale cancelled marker, failed-identity kill, duration-after-deps
- [tests/test_run_agent_wait_completion.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_run_agent_wait_completion.py) (164 lines) — completion/kill/index tests

The original file is deleted. Verified with the project venv: 17 passed, and `sase tool run check` (all lint gates + diff-scoped tests) succeeded.
