# Chat History - ace-run (sase-1q2.4--mon-0)

- **TIMESTAMP:** 2026-10-30 18:52:37 EDT
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1q2.4--mon-0

## Prompt

sase monitor start --command 'run_index=1; while [ "$run_index" -le 20 ]; do printf "serial proof %s/20\\\\n" "$run_index"; TZ=UTC .venv/bin/python -m pytest -q -n 0 --maxfail=1 tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once tests/ace/tui/widgets/test_agent_bead_touch_rows_basic.py::test_narrow_created_row_moves_pill_to_its_own_line tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card || exit $?; TZ=UTC just fix-tui-screenshots --check -- -n 1 tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots || exit $?; run_index=$((run_index + 1)); done; run_index=1; while [ "$run_index" -le 3 ]; do printf "parallel suite proof %s/3\\\\n" "$run_index"; TZ=UTC .venv/bin/python -m pytest -q -n 8 --maxfail=1 tests/ace/tui tests/pager/test_app_navigation.py tests/footprint/test_tui.py || exit $?; run_index=$((run_index + 1)); done' --reason 'Run the TUI phase repeatability proof for sase-1q2.4'

## Response

sase tool run 36e325dc92ad309abfebb39d240008f0
serial proof 1/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.51s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.28s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.34s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.33s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.23s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.17s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.07s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.05s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 9.20s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
25.81s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.29s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.50s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.43s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.91s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 54.85s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.98s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.15s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.26s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/acf112b35ead4fef8ee53745e20f1ef4/manifest.json
run-dir: .pytest_cache/sase-visual/runs/acf112b35ead4fef8ee53745e20f1ef4
report: .pytest_cache/sase-visual/runs/acf112b35ead4fef8ee53745e20f1ef4/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/acf112b35ead4fef8ee53745e20f1ef4/report/summary.md
serial proof 2/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.40s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.22s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.37s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.36s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.24s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.18s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.08s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.03s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 8.96s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
24.65s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.39s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
5.30s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
3.90s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.86s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.24s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 53.57s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.15s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.79s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/e36a17dd274a4124aa9043f6ce58d959/manifest.json
run-dir: .pytest_cache/sase-visual/runs/e36a17dd274a4124aa9043f6ce58d959
report: .pytest_cache/sase-visual/runs/e36a17dd274a4124aa9043f6ce58d959/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/e36a17dd274a4124aa9043f6ce58d959/report/summary.md
serial proof 3/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
5.11s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.36s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.34s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.24s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.20s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.20s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.08s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.03s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 9.08s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
24.78s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.82s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
5.38s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
5.21s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
3.65s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.60s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 55.85s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.93s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 10.85s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/1929c08d0566435d80ac6c03722b1665/manifest.json
run-dir: .pytest_cache/sase-visual/runs/1929c08d0566435d80ac6c03722b1665
report: .pytest_cache/sase-visual/runs/1929c08d0566435d80ac6c03722b1665/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/1929c08d0566435d80ac6c03722b1665/report/summary.md
serial proof 4/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.37s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.57s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.37s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.37s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.26s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.19s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.06s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.04s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 9.57s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
25.25s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
6.80s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.74s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.60s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
3.50s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
0.15s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 56.10s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.84s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.11s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/689922d2490f46c99593bdddf0cfca60/manifest.json
run-dir: .pytest_cache/sase-visual/runs/689922d2490f46c99593bdddf0cfca60
report: .pytest_cache/sase-visual/runs/689922d2490f46c99593bdddf0cfca60/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/689922d2490f46c99593bdddf0cfca60/report/summary.md
serial proof 5/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.33s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.28s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.33s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.33s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.23s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.18s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.06s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.03s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 8.29s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
24.39s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.19s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.85s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
3.72s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.44s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.04s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 51.86s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.31s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.48s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/2e4c151dec4e40db89fc3cca753b87bc/manifest.json
run-dir: .pytest_cache/sase-visual/runs/2e4c151dec4e40db89fc3cca753b87bc
report: .pytest_cache/sase-visual/runs/2e4c151dec4e40db89fc3cca753b87bc/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/2e4c151dec4e40db89fc3cca753b87bc/report/summary.md
serial proof 6/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.03s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.14s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.32s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.31s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.22s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.19s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.06s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.03s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 7.58s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
25.27s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.60s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.96s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.35s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
4.35s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.63s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.28s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 56.08s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.78s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.19s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 10.71s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/ffd8a8f8371e4bf78d8744a289154e86/manifest.json
run-dir: .pytest_cache/sase-visual/runs/ffd8a8f8371e4bf78d8744a289154e86
report: .pytest_cache/sase-visual/runs/ffd8a8f8371e4bf78d8744a289154e86/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/ffd8a8f8371e4bf78d8744a289154e86/report/summary.md
serial proof 7/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
4.23s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.38s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.35s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.26s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.19s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.18s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.06s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.03s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 8.03s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
25.49s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.46s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.81s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
3.72s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.58s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.37s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.14s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 53.68s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.94s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.20s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 10.83s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/26fa1b8ad99643b790dbeb901bab394c/manifest.json
run-dir: .pytest_cache/sase-visual/runs/26fa1b8ad99643b790dbeb901bab394c
report: .pytest_cache/sase-visual/runs/26fa1b8ad99643b790dbeb901bab394c/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/26fa1b8ad99643b790dbeb901bab394c/report/summary.md
serial proof 8/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.27s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.22s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.32s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.31s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.24s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.17s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.07s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.04s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 8.19s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
27.19s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.97s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
5.09s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.37s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
4.09s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.56s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 58.88s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.53s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.20s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.78s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/656704e9b1e24b1aa844857498dae81b/manifest.json
run-dir: .pytest_cache/sase-visual/runs/656704e9b1e24b1aa844857498dae81b
report: .pytest_cache/sase-visual/runs/656704e9b1e24b1aa844857498dae81b/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/656704e9b1e24b1aa844857498dae81b/report/summary.md
serial proof 9/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.35s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.32s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.34s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.33s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.22s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.17s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.06s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.04s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 8.29s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
24.39s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.20s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
5.07s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
3.86s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
3.70s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.64s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
0.25s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 53.99s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.06s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.15s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.23s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/69d3c768f89a40fd83480cb97ad16e8d/manifest.json
run-dir: .pytest_cache/sase-visual/runs/69d3c768f89a40fd83480cb97ad16e8d
report: .pytest_cache/sase-visual/runs/69d3c768f89a40fd83480cb97ad16e8d/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/69d3c768f89a40fd83480cb97ad16e8d/report/summary.md
serial proof 10/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
2.93s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.15s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.34s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.32s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.23s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.18s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.08s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.03s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 7.57s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
26.51s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
6.12s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
5.13s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
3.64s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.46s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.42s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 55.34s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.02s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.15s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 10.71s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/6abc703633564ef6aefbf99bcd3ba2d6/manifest.json
run-dir: .pytest_cache/sase-visual/runs/6abc703633564ef6aefbf99bcd3ba2d6
report: .pytest_cache/sase-visual/runs/6abc703633564ef6aefbf99bcd3ba2d6/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/6abc703633564ef6aefbf99bcd3ba2d6/report/summary.md
serial proof 11/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.60s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.24s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.42s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.38s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.20s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.17s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.05s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.05s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 8.74s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
26.18s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.78s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
5.01s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.16s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.78s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.42s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 56.41s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.24s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.17s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.31s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/0b876fc51975437bb7815c558fb6b63f/manifest.json
run-dir: .pytest_cache/sase-visual/runs/0b876fc51975437bb7815c558fb6b63f
report: .pytest_cache/sase-visual/runs/0b876fc51975437bb7815c558fb6b63f/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/0b876fc51975437bb7815c558fb6b63f/report/summary.md
serial proof 12/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
4.14s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.35s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.32s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.26s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.21s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.18s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.06s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.05s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 9.07s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
24.80s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.20s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.74s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.58s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.75s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.31s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.22s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.02s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 54.36s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.45s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.20s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.73s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/cdedde3f01b6459591896cf3f9e3d399/manifest.json
run-dir: .pytest_cache/sase-visual/runs/cdedde3f01b6459591896cf3f9e3d399
report: .pytest_cache/sase-visual/runs/cdedde3f01b6459591896cf3f9e3d399/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/cdedde3f01b6459591896cf3f9e3d399/report/summary.md
serial proof 13/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
4.54s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.38s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.33s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.30s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.21s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.19s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.05s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.04s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 8.56s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
27.48s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.95s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.82s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.28s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.69s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.45s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot

(9 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 56.88s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.86s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.43s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/6dcef10e9bca46dbabf2b68ea6445bdb/manifest.json
run-dir: .pytest_cache/sase-visual/runs/6dcef10e9bca46dbabf2b68ea6445bdb
report: .pytest_cache/sase-visual/runs/6dcef10e9bca46dbabf2b68ea6445bdb/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/6dcef10e9bca46dbabf2b68ea6445bdb/report/summary.md
serial proof 14/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
4.38s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.35s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.33s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.23s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.19s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.18s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.07s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.03s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 8.32s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
27.56s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.79s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
5.21s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.31s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.75s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.26s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.28s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 59.15s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.50s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.22s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 12.02s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/c1feda6a2c5f43e69018ff78e5f7ac6c/manifest.json
run-dir: .pytest_cache/sase-visual/runs/c1feda6a2c5f43e69018ff78e5f7ac6c
report: .pytest_cache/sase-visual/runs/c1feda6a2c5f43e69018ff78e5f7ac6c/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/c1feda6a2c5f43e69018ff78e5f7ac6c/report/summary.md
serial proof 15/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.19s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.81s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.32s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.31s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.21s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.19s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.05s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.03s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 9.01s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
26.75s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.72s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
5.09s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
3.87s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.66s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.51s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.17s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 56.13s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.13s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.24s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.11s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/fc6215256a0742bc881ad4b351012afa/manifest.json
run-dir: .pytest_cache/sase-visual/runs/fc6215256a0742bc881ad4b351012afa
report: .pytest_cache/sase-visual/runs/fc6215256a0742bc881ad4b351012afa/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/fc6215256a0742bc881ad4b351012afa/report/summary.md
serial proof 16/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
4.17s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.32s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.30s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.23s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.21s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.18s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.06s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.05s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 7.92s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
26.03s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.08s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.98s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.52s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
4.01s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.32s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 56.76s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=14 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/f905afac47854ca0978ef433c451f3ac/manifest.json
run-dir: .pytest_cache/sase-visual/runs/f905afac47854ca0978ef433c451f3ac
report: .pytest_cache/sase-visual/runs/f905afac47854ca0978ef433c451f3ac/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/f905afac47854ca0978ef433c451f3ac/report/summary.md
serial proof 17/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.31s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
2.09s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.33s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.32s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.26s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.17s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.09s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.04s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 9.19s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
25.58s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.63s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
5.27s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.28s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.93s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.33s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 55.26s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.07s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.28s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/8eee286920ee4ee199950dfaa574c37c/manifest.json
run-dir: .pytest_cache/sase-visual/runs/8eee286920ee4ee199950dfaa574c37c
report: .pytest_cache/sase-visual/runs/8eee286920ee4ee199950dfaa574c37c/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/8eee286920ee4ee199950dfaa574c37c/report/summary.md
serial proof 18/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.25s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.31s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.37s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.33s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.25s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.17s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.05s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.04s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 9.85s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
25.72s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.67s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
5.23s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
3.98s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.94s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.77s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.23s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot

(10 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 56.05s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.24s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.21s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 12.00s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/6e37876d0f104f5ba75c80dd591864a1/manifest.json
run-dir: .pytest_cache/sase-visual/runs/6e37876d0f104f5ba75c80dd591864a1
report: .pytest_cache/sase-visual/runs/6e37876d0f104f5ba75c80dd591864a1/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/6e37876d0f104f5ba75c80dd591864a1/report/summary.md
serial proof 19/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
3.68s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.23s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.38s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.37s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.26s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.18s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.07s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.03s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 9.57s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
25.34s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.76s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
4.96s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
3.74s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
3.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.38s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.26s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 54.66s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
6.22s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.19s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 12.76s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/40f37955d47c4156b3fe724a3f35a306/manifest.json
run-dir: .pytest_cache/sase-visual/runs/40f37955d47c4156b3fe724a3f35a306
report: .pytest_cache/sase-visual/runs/40f37955d47c4156b3fe724a3f35a306/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/40f37955d47c4156b3fe724a3f35a306/report/summary.md
serial proof 20/20
.......                                                                  [100%]
============================= slowest 20 durations =============================
4.34s call     tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
1.87s teardown tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
0.34s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card
0.34s call     tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card
0.22s call     tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.18s call     tests/pager/test_app_navigation.py::test_past_eof_end_line_clamps_silently
0.06s setup    tests/pager/test_app_navigation.py::test_past_eof_line_clamps_with_information_toast
0.05s call     tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
7 passed in 11.10s
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [6 items]

......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
25.73s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
5.77s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
5.10s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
4.65s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_plans.py::test_agents_phase_bead_context_png_snapshot
4.00s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_created_by_agent_narrow_png_snapshot
3.24s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context_beads.py::test_agents_bead_closed_by_agent_narrow_png_snapshot
0.21s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 6 passed in 56.08s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, platformdirs-4.12.2, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.77s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.19s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 1 passed in 11.07s ==============================
fix-tui-screenshots: check clean
scope: targeted
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot after 2 attempt(s)
counts: created=0 updated=0 unchanged=13 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_help_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_single_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_grown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_live_reply_split_partial_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_all_unknown_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_area_narrow_light_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_footprint_map_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_macros_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_measuring_code_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_patch_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_repo_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
manifest: .pytest_cache/sase-visual/runs/6bd62aef49ed4bb9a6b6c750f3671179/manifest.json
run-dir: .pytest_cache/sase-visual/runs/6bd62aef49ed4bb9a6b6c750f3671179
report: .pytest_cache/sase-visual/runs/6bd62aef49ed4bb9a6b6c750f3671179/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/6bd62aef49ed4bb9a6b6c750f3671179/report/summary.md
parallel suite proof 1/3
bringing up nodes...
bringing up nodes...

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
................................                                         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:200: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    memo[id(x)] = y
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_lookup.py::test_queued_explicit_open_drains_on_idle_tick
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/ace/tui/actions/agents/_archive_view_parking.py:203: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    def flush_pending_archive_list_scroll(owner: Any) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_list_model.py::test_page_boundary_shows_exact_tail_and_next_page_removes_it
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/ace/tui/models/agent_archive_list.py:144: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    if all(isinstance(part, str) and part for part in (user, machine, run_id)):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_submit_happy_path_settles_on_exit_completion
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:189: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for k, j in zip(x, y):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:189: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    for k, j in zip(x, y):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
22.25s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
21.39s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
20.08s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
17.28s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
13.18s call     tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_fresh_app_instance_hides_removed_rows
12.88s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
12.73s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
11.61s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
11.41s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
10.71s call     tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
10.61s setup    tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
10.36s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
9.89s call     tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
9.70s call     tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
9.67s call     tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
9.31s call     tests/ace/tui/test_agents_filter_bar_session.py::test_slash_opens_the_bar_and_commits_like_f
9.22s call     tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
8.91s call     tests/ace/tui/test_update_restart_lifecycle.py::test_tool_run_survives_observer_stop_and_reconnect
8.82s call     tests/ace/tui/test_agents_tab_x_clan_race_e2e.py::test_clan_x_durable_stage_kills_orphans_of_runners_that_already_exited
8.77s call     tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_from_rail_is_flush_and_restores_rail
18608 passed, 30 warnings in 1083.45s (0:18:03)
parallel suite proof 2/3
bringing up nodes...
bringing up nodes...

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
................................                                         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:200: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    memo[id(x)] = y
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_lookup.py::test_coalesced_idle_does_not_publish_false_missing_for_queued_open
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:112: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    doc = getattr(func, "__doc__", None)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:1725: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return ((p, type(p)) for p in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:200: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    memo[id(x)] = y
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:146: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    rv = reductor(4)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/re/__init__.py:287: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def compile(pattern, flags=0):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
40.45s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
22.22s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
17.99s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
17.84s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_confirm_executes_and_restarts
16.32s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
15.75s call     tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
15.09s call     tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_submit_choice_all_submits_whole_stack[enter]
14.05s teardown tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_filter_types_brackets_and_tab_switches_main_tab
13.92s call     tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_fresh_app_instance_hides_removed_rows
13.63s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
12.37s call     tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
12.07s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
12.00s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
11.98s setup    tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
11.80s call     tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget
11.49s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
11.19s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
10.19s call     tests/ace/tui/test_tribe_panel_flicker.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
9.84s call     tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
9.71s call     tests/ace/tui/widgets/test_navigation_widgets.py::test_tab_bar_integration_tab_key
18608 passed, 30 warnings in 1068.35s (0:17:48)
parallel suite proof 3/3
bringing up nodes...
bringing up nodes...

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
..
