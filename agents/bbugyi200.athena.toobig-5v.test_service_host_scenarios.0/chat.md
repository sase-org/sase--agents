# Chat History - ace-run (toobig-5v.test_service_host_scenarios.0)

- **TIMESTAMP:** 2026-09-22 22:30:26 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5v.test_service_host_scenarios.0

## Prompt

%id(test_service_host_scenarios.0, clan=toobig-5v)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/service/test_service_host_scenarios.py` file up into multiple files? Use your best
%wait:toobig-5v.test_agent_enter_targets.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 1246-line `tests/service/test_service_host_scenarios.py` is now 4 themed modules plus a shared helper, all under 500 lines. Test bodies are verbatim — only imports and helper placement changed.

- [test_service_host_lifetime.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/service/test_service_host_lifetime.py) (284 lines) — lock convergence, racing starts, stale records, signal handling (4 tests)
- [test_service_host_reconcile.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/service/test_service_host_reconcile.py) (290 lines) — config reloads, stop-marker races, crash backoff, config outages (6 tests)
- [test_service_host_proc_requests.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/service/test_service_host_proc_requests.py) (246 lines) — oneshot settle plus explicit start/restart requests (7 tests)
- [test_service_host_restart_policy.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/service/test_service_host_restart_policy.py) (313 lines) — give-up parking, revive paths, crash notifications (7 tests)
- [service_host_scenario_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/service/service_host_scenario_helpers.py) (209 lines) — shared scaffolding (`_compose`, `_service_host`, `_wait_for`, spawn/stale/oneshot fakes), following the existing `*_helpers.py` convention in that directory

Verification: all 24 tests collect; 22 pass. The 2 failures (`crash_loop_notifies…`, `give_up_notification…`) fail identically on the original file — this environment's TMPDIR sits under `/home/bryan/.sase`, so the state-write guard refuses the notification writes. Pre-existing and unrelated to the split. `just check` passes every gate except symvision, which fails identically on the clean tree (`delete_paths_in_background` in `src/sase/_linked_repo_workspaces.py`, untouched by this change).

One fix worth noting: my first helper draft imported `record_service_host` from `sase.service.control`; it's actually in `sase.service.state` — caught by collection and corrected.
