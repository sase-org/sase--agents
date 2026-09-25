# Chat History - ace-run (0r3--code)

- **TIMESTAMP:** 2026-09-24 15:02:11 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 0r3--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202609/completion_unread_same_tick.md

The above plan has been reviewed and approved. Implement it now.


## Response

Implemented the approved `202609/completion_unread_same_tick.md` plan.

New worker probe [\_notification\_completion\_arrival.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/tui/actions/agents/_notification_completion_arrival.py) runs on the existing notification-poll worker hop: mismatch-driven candidate selection, one batched read-only `load_artifact_delta_agents(dirs, update_index=False, patch_snapshot=[])`, terminal-only overlays with `tui_trace("notification.completion_arrival")`. The poll installs overlays onto live rows before the unread projection, schedules the paired authoritative delta, and repaints via extended `_patch_unread_completed_agent_changes(status_changed=...)`. Overlays survive exactly one stale in-flight apply in `_apply_loaded_agents_prepared_inner`, then drop; dismissed/killed identities pop them. The auto-refresh tick now queues the arrival delta before hint-mode/`_agents_loading` early exits. Docs extended in [notifications.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/docs/notifications.md).

Tests: new [test\_notification\_completion\_arrival.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/test_notification_completion_arrival.py) (standalone DONE/FAILED, family TALE DONE mirroring, in-flight family, heal-on-later-poll, no-scan cases, worker-thread check, readonly-loader args) and [overlay lifetime tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ace/tui/test_notification_completion_arrival_overlay.py), plus 3 auto-refresh drop tests. Verified: 80 passed across arrival/overlay/auto-refresh/unread/pending-gate/family suites; 11 dismiss/kill tests passed; ruff clean; mypy clean on all 7 touched source files; new symvision flags fixed.

Finding: `sase tool run check` still fails on pre-existing gates outside this change — 14 mypy errors in `_agent_detail_display.py`, `_agent_detail_state.py`, `_index_queries.py`, `run_agent_wait_deps.py`, plus pre-existing symvision unused symbols elsewhere.
