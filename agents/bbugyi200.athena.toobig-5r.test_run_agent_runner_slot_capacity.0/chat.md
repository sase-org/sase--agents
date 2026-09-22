# Chat History - ace-run (toobig-5r.test_run_agent_runner_slot_capacity.0)

- **TIMESTAMP:** 2026-09-22 02:25:41 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_run_agent_runner_slot_capacity.0

## Prompt

%id(test_run_agent_runner_slot_capacity.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/test_run_agent_runner_slot_capacity.py` file up into multiple files? Use your best
%wait:toobig-5r.test_notification_toast_polling_agent_refresh.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 824-line `tests/test_run_agent_runner_slot_capacity.py` into three thematic files, following the existing `test_run_agent_runner_slot_capacity_<topic>.py` naming convention. All 14 test bodies are verbatim — only the module docstrings and import headers differ per file (unused `os`/`datetime` imports dropped where unneeded):

- [tests/test_run_agent_runner_slot_capacity_weights.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_run_agent_runner_slot_capacity_weights.py) (283 lines) — fractional weight admission: live config raise, exact-fill blocking, heavy-weight, explicit-capacity bypass, lighter-waiter pass-through (5 tests)
- [tests/test_run_agent_runner_slot_capacity_holds.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_run_agent_runner_slot_capacity_holds.py) (344 lines) — hold-barrier admission: active-hold threading, held-by marker write/self-heal, deadlock notification dedup, real end-to-end hold/release (4 tests)
- [tests/test_run_agent_runner_slot_capacity_parking.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_run_agent_runner_slot_capacity_parking.py) (221 lines) — monitor occupancy and `park_on_block=False`: monitor parks newcomer, monitor release admits waiter, three no-parking cases (5 tests)

The original file is removed. Verification: `sase tool run check` passed (all lint gates + scoped tests), and the three new files run green directly — 14 passed.
