# Chat History - ace-run (toobig-5q.notification_utils.0)

- **TIMESTAMP:** 2026-09-21 00:44:28 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5q.notification_utils.0

## Prompt

%id(notification_utils.0, clan=toobig-5q)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/actions/agents/_notification_utils.py` file up into multiple files? Use your best
%wait:toobig-5q.loading_apply.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 886-line `_notification_utils.py` is now four focused modules plus a thin facade, all well under 500 lines. No caller changes were needed.

- [\_notification_agent_targeting.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/ace/tui/actions/agents/_notification_agent_targeting.py) (113 lines) — roster, agent resolution, cache refresh, `TabName`
- [\_notification_matching.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/ace/tui/actions/agents/_notification_matching.py) (242 lines) — suffix helpers, active predicates, agent keys, row matching, unread buckets
- [\_notification_delta_dirs.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/ace/tui/actions/agents/_notification_delta_dirs.py) (266 lines) — completion and pending-gate artifact-dir resolution
- [\_notification_gate_refresh.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/ace/tui/actions/agents/_notification_gate_refresh.py) (321 lines) — refresh orchestration, gate receipts, disappearance handling
- [\_notification_utils.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/ace/tui/actions/agents/_notification_utils.py) (112 lines) — compatibility facade re-exporting the full previous surface

Two judgment calls worth knowing:

1. Shared helpers are public now (e.g. `resolve_notification_agent`, `completion_notification_delta_dirs`). The symvision gate forbids importing `_`-private names across files, so keeping them private would fail `just check`. Two old private names tests import (`_request_gate_decision_refresh`, `_agent_settlement_notification_matches_agent`) stay importable as aliases.
2. `just check` still fails at symvision, but only on 5 pre-existing unused-public symbols in files this split never touched (`axe/desired_state.py`, `axe/lifecycle_journal.py`, `prompt_panel/_agent_bead_touches.py`). I filed that as bead `sase-150` (type ci, ready, linked to `sase-13s`) rather than fixing unrelated subsystems here.

Verification: 56/56 tests pass across the five notification-area test files; ruff check, ruff format, and mypy are clean on all five files; a script confirmed all 37 original definitions survived the move.
