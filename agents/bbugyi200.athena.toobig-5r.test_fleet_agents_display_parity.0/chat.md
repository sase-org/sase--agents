# Chat History - ace-run (toobig-5r.test_fleet_agents_display_parity.0)

- **TIMESTAMP:** 2026-09-21 22:09:50 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_fleet_agents_display_parity.0

## Prompt

%id(test_fleet_agents_display_parity.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/test_fleet_agents_display_parity.py` file up into multiple files? Use your best
%wait:toobig-5r.test_event_handlers_auto_refresh_dirty_flags.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 716-line `test_fleet_agents_display_parity.py` is now four files, all under 500 lines:

- [test_fleet_agents_display_parity.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/test_fleet_agents_display_parity.py:27) (458 lines) — keeps the main render-parity test plus its local/remote fixture builders, which only it uses.
- [_fleet_display_parity_shared.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/_fleet_display_parity_shared.py:1) (138 lines) — parity constants plus the render/signature comparison helpers. Underscore-prefixed per the repo's test-helper convention, imported relatively like the other `_helpers` modules.
- [test_fleet_agents_display_panels.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/test_fleet_agents_display_panels.py:27) (113 lines) — default-tribe panel-counts test, moved verbatim.
- [test_fleet_agents_display_runtime.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/test_fleet_agents_display_runtime.py:12) (60 lines) — family elapsed/current-run test, moved verbatim.

Test bodies are unchanged; only imports moved. Verified with the project venv (3 passed) and `sase tool run check`, which succeeded across all lint gates and the scoped test lane.
