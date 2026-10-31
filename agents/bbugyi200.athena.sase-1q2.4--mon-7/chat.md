# Chat History - ace-run (sase-1q2.4--mon-7)

- **TIMESTAMP:** 2026-10-30 23:54:38 EDT
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1q2.4--mon-7

## Prompt

sase monitor start --command 'run_index=1; while [ "$run_index" -le 20 ]; do printf "serial screenshot proof %s/20\\\\n" "$run_index"; TZ=UTC just fix-tui-screenshots --check -- -n 1 tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot || exit $?; .venv/bin/python -c \'import json; p=json.load(open(".pytest_cache/sase-visual/latest-report.json")); m=json.load(open(p["manifest"])); c=m["counts"]; print("manifest",m["run_id"],"counts",c,"unstable",len(m["unstable"]),"errors",len(m["errors"])); assert m["mode"] == "check" and m["status"] == "clean" and m["complete"] and c["created"] == 0 and c["updated"] == 0 and c["stale"] == 0 and not m["unstable"] and not m["errors"]\' || exit $?; run_index=$((run_index + 1)); done' --reason 'Prove screenshot convergence for the renamed session and stranded modal nodes'

## Response

sase tool run d70a2fb8fbc1073ae28fc774fd29e754
serial screenshot proof 1/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
9.36s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
6.26s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.38s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.08s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.02s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
============================== 2 passed in 23.71s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/0939897f2713450e9cd2280b56ea3733/manifest.json
run-dir: .pytest_cache/sase-visual/runs/0939897f2713450e9cd2280b56ea3733
report: .pytest_cache/sase-visual/runs/0939897f2713450e9cd2280b56ea3733/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/0939897f2713450e9cd2280b56ea3733/report/summary.md
manifest 0939897f2713450e9cd2280b56ea3733 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 2/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
8.04s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.56s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.17s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 19.50s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/84bff1880190413ea03a3bf63ac3eb62/manifest.json
run-dir: .pytest_cache/sase-visual/runs/84bff1880190413ea03a3bf63ac3eb62
report: .pytest_cache/sase-visual/runs/84bff1880190413ea03a3bf63ac3eb62/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/84bff1880190413ea03a3bf63ac3eb62/report/summary.md
manifest 84bff1880190413ea03a3bf63ac3eb62 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 3/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
9.39s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
4.89s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot

(2 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 20.53s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/17415783e4594e3fbfdf043e2c6800cb/manifest.json
run-dir: .pytest_cache/sase-visual/runs/17415783e4594e3fbfdf043e2c6800cb
report: .pytest_cache/sase-visual/runs/17415783e4594e3fbfdf043e2c6800cb/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/17415783e4594e3fbfdf043e2c6800cb/report/summary.md
manifest 17415783e4594e3fbfdf043e2c6800cb counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 4/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
7.25s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.51s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.19s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 19.01s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/0159dbc53cb64ecf8462c500bb5f0a8b/manifest.json
run-dir: .pytest_cache/sase-visual/runs/0159dbc53cb64ecf8462c500bb5f0a8b
report: .pytest_cache/sase-visual/runs/0159dbc53cb64ecf8462c500bb5f0a8b/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/0159dbc53cb64ecf8462c500bb5f0a8b/report/summary.md
manifest 0159dbc53cb64ecf8462c500bb5f0a8b counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 5/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
8.94s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.16s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 20.31s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/ca971b82298745179694ffc4fbe53938/manifest.json
run-dir: .pytest_cache/sase-visual/runs/ca971b82298745179694ffc4fbe53938
report: .pytest_cache/sase-visual/runs/ca971b82298745179694ffc4fbe53938/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/ca971b82298745179694ffc4fbe53938/report/summary.md
manifest ca971b82298745179694ffc4fbe53938 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 6/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
6.53s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.36s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.19s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot

(2 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 18.50s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/0fc36a0df4bc444297815f185d184e5e/manifest.json
run-dir: .pytest_cache/sase-visual/runs/0fc36a0df4bc444297815f185d184e5e
report: .pytest_cache/sase-visual/runs/0fc36a0df4bc444297815f185d184e5e/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/0fc36a0df4bc444297815f185d184e5e/report/summary.md
manifest 0fc36a0df4bc444297815f185d184e5e counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 7/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
7.42s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.37s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.24s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot

(2 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 19.27s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/5548f38214c14ca7bff486a10718b503/manifest.json
run-dir: .pytest_cache/sase-visual/runs/5548f38214c14ca7bff486a10718b503
report: .pytest_cache/sase-visual/runs/5548f38214c14ca7bff486a10718b503/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/5548f38214c14ca7bff486a10718b503/report/summary.md
manifest 5548f38214c14ca7bff486a10718b503 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 8/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
7.41s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.01s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 19.39s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/9e2e2a1ecd6f43acbf8b51bd51d0c597/manifest.json
run-dir: .pytest_cache/sase-visual/runs/9e2e2a1ecd6f43acbf8b51bd51d0c597
report: .pytest_cache/sase-visual/runs/9e2e2a1ecd6f43acbf8b51bd51d0c597/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/9e2e2a1ecd6f43acbf8b51bd51d0c597/report/summary.md
manifest 9e2e2a1ecd6f43acbf8b51bd51d0c597 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 9/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
6.64s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.46s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.22s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.04s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot

(2 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 18.26s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/387fbfd43a7c4f6cb75ab36541e17e56/manifest.json
run-dir: .pytest_cache/sase-visual/runs/387fbfd43a7c4f6cb75ab36541e17e56
report: .pytest_cache/sase-visual/runs/387fbfd43a7c4f6cb75ab36541e17e56/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/387fbfd43a7c4f6cb75ab36541e17e56/report/summary.md
manifest 387fbfd43a7c4f6cb75ab36541e17e56 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 10/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
9.65s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.35s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(2 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 21.36s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/bb89e596b1814998980cc8dd396b647f/manifest.json
run-dir: .pytest_cache/sase-visual/runs/bb89e596b1814998980cc8dd396b647f
report: .pytest_cache/sase-visual/runs/bb89e596b1814998980cc8dd396b647f/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/bb89e596b1814998980cc8dd396b647f/report/summary.md
manifest bb89e596b1814998980cc8dd396b647f counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 11/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
7.29s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.33s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.17s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 19.28s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/b600346e2cb0446ea6ad8dd2872482d6/manifest.json
run-dir: .pytest_cache/sase-visual/runs/b600346e2cb0446ea6ad8dd2872482d6
report: .pytest_cache/sase-visual/runs/b600346e2cb0446ea6ad8dd2872482d6/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/b600346e2cb0446ea6ad8dd2872482d6/report/summary.md
manifest b600346e2cb0446ea6ad8dd2872482d6 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 12/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
8.75s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.70s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 21.12s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/ede36f1eee8e48c58d377c83930191e6/manifest.json
run-dir: .pytest_cache/sase-visual/runs/ede36f1eee8e48c58d377c83930191e6
report: .pytest_cache/sase-visual/runs/ede36f1eee8e48c58d377c83930191e6/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/ede36f1eee8e48c58d377c83930191e6/report/summary.md
manifest ede36f1eee8e48c58d377c83930191e6 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 13/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
8.32s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.51s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.17s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.03s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
0.02s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
============================== 2 passed in 20.76s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/838550ef908d4a20b59bed76dda6355f/manifest.json
run-dir: .pytest_cache/sase-visual/runs/838550ef908d4a20b59bed76dda6355f
report: .pytest_cache/sase-visual/runs/838550ef908d4a20b59bed76dda6355f/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/838550ef908d4a20b59bed76dda6355f/report/summary.md
manifest 838550ef908d4a20b59bed76dda6355f counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 14/20
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core to origin/master
[core-source] linked sase-core source changed since the extension was built; flagging an extension rebuild.
[setup] Rebuilding sase_core_rs: linked sase-core source changed since the extension was built.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
# Capture the source identity after the checkout refresh above and before
# the build below. It is written to the venv only after a successful
# install (wheel-cache hit or `maturin develop` alike), so an edit made
# during the build still reads as stale on the next check.
[sase-core-wheel-cache] miss: no exact cached wheel
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling proc-macro2 v1.0.106
   Compiling quote v1.0.45
   Compiling unicode-ident v1.0.24
   Compiling libc v0.2.186
   Compiling cfg-if v1.0.4
   Compiling shlex v1.3.0
   Compiling find-msvc-tools v0.1.9
   Compiling zerocopy v0.8.48
   Compiling memchr v2.8.0
   Compiling serde_core v1.0.228
   Compiling autocfg v1.5.0
   Compiling itoa v1.0.18
   Compiling crossbeam-utils v0.8.21
   Compiling once_cell v1.21.4
   Compiling pin-project-lite v0.2.17
   Compiling regex-syntax v0.8.10
   Compiling bytes v1.11.1
   Compiling log v0.4.29
   Compiling serde v1.0.228
   Compiling siphasher v1.0.4
   Compiling version_check v0.9.5
   Compiling zmij v1.0.21
   Compiling futures-core v0.3.32
   Compiling crossbeam-epoch v0.9.21
   Compiling smallvec v1.15.1
   Compiling serde_json v1.0.149
   Compiling stable_deref_trait v1.2.1
   Compiling futures-sink v0.3.32
   Compiling crossbeam-deque v0.8.8
   Compiling target-lexicon v0.12.16
   Compiling hashbrown v0.17.0
   Compiling equivalent v1.0.2
   Compiling iana-time-zone v0.1.65
   Compiling slab v0.4.12
   Compiling futures-io v0.3.32
   Compiling futures-task v0.3.32
   Compiling tower-service v0.3.3
   Compiling ucd-trie v0.1.7
   Compiling bitflags v2.11.1
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling heck v0.5.0
   Compiling untrusted v0.9.0
   Compiling libm v0.2.16
   Compiling litemap v0.8.2
   Compiling same-file v1.0.6
   Compiling typenum v1.20.0
   Compiling icu_normalizer_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling deunicode v1.6.2
   Compiling parking_lot_core v0.9.12
   Compiling httpdate v1.0.3
   Compiling lazy_static v1.5.0
   Compiling tower-layer v0.3.3
   Compiling fnv v1.0.7
   Compiling encoding_rs v0.8.35
   Compiling vcpkg v0.2.15
   Compiling percent-encoding v2.3.2
   Compiling scopeguard v1.2.0
   Compiling sync_wrapper v1.0.2
   Compiling cc v1.2.61
   Compiling walkdir v2.5.0
   Compiling ryu v1.0.23
   Compiling clap_lex v1.1.1
   Compiling ahash v0.8.12
   Compiling num-traits v0.2.19
   Compiling generic-array v0.14.7
   Compiling phf_shared v0.11.3
   Compiling unicode-segmentation v1.13.3
   Compiling rayon-core v1.13.0
   Compiling futures-channel v0.3.32
   Compiling either v1.19.0
   Compiling rustls v0.21.12
   Compiling thiserror v1.0.69
   Compiling pkg-config v0.3.33
   Compiling anstyle v1.0.14
   Compiling num-conv v0.2.1
   Compiling try-lock v0.2.5
   Compiling rustix v1.1.4
   Compiling powerfmt v0.2.0
   Compiling time-core v0.1.8
   Compiling thiserror v2.0.18
   Compiling winnow v1.0.4
   Compiling rustversion v1.0.22
   Compiling indexmap v2.14.0
   Compiling getrandom v0.4.2
   Compiling colored v2.2.0
   Compiling slug v0.1.6
   Compiling pyo3-build-config v0.22.6
   Compiling tracing-core v0.1.36
   Compiling atomic-waker v1.1.2
   Compiling winnow v0.7.15
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling linux-raw-sys v0.12.1
   Compiling cpufeatures v0.2.17
   Compiling mime v0.3.17
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling home v0.5.12
   Compiling http v1.4.0
   Compiling http v0.2.12
   Compiling grep-matcher v0.1.9
   Compiling crossbeam-channel v0.5.17
   Compiling getrandom v0.2.17
   Compiling memoffset v0.9.1
   Compiling humansize v2.1.3
   Compiling lock_api v0.4.14
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling fallible-streaming-iterator v0.1.9
   Compiling itertools v0.11.0
   Compiling base64 v0.21.7
   Compiling tinyvec v1.13.3
   Compiling want v0.3.1
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling clap_builder v4.6.7
   Compiling form_urlencoded v1.2.2
   Compiling socket2 v0.5.10
   Compiling memmap2 v0.9.11
   Compiling libsqlite3-sys v0.30.1
   Compiling time-macros v0.2.27
   Compiling term_size v0.3.2
   Compiling unsafe-libyaml v0.2.11
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling phf v0.11.3
   Compiling serde_spanned v1.1.2
   Compiling base64 v0.22.1
   Compiling fastrand v2.4.1
   Compiling fallible-iterator v0.3.0
   Compiling serde_path_to_error v0.1.20
   Compiling tracing-log v0.2.0
   Compiling deranged v0.5.8
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling fs2 v0.4.3
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling sharded-slab v0.1.7
   Compiling thread_local v1.1.9
   Compiling sync_wrapper v0.1.2
   Compiling chrono v0.4.44
   Compiling num-integer v0.1.46
   Compiling etcetera v0.8.0
   Compiling webpki-roots v0.25.4
   Compiling hex v0.4.3
   Compiling signal-hook-registry v1.4.8
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
   Compiling nu-ansi-term v0.50.3
   Compiling unicode-normalization v0.1.25
   Compiling semver v1.0.28
   Compiling rand_core v0.6.4
   Compiling matchit v0.7.3
   Compiling http-body v1.0.1
   Compiling unicode-width v0.2.2
   Compiling ipnet v2.12.0
   Compiling encoding_rs_io v0.1.8
   Compiling unicode-casefold v0.2.0
   Compiling unindent v0.2.4
   Compiling indoc v2.0.7
   Compiling regex-automata v0.4.14
   Compiling ppv-lite86 v0.2.21
   Compiling rustls-pemfile v1.0.4
   Compiling parking_lot v0.12.5
   Compiling pem v3.0.6
   Compiling digest v0.10.7
   Compiling http-body v0.4.6
   Compiling num-bigint v0.4.6
   Compiling toml v0.9.12+spec-1.1.0
   Compiling http-body-util v0.1.3
   Compiling time v0.3.47
   Compiling pest v2.9.4
   Compiling rand_chacha v0.3.1
   Compiling hashbrown v0.14.5
   Compiling grep-searcher v0.1.17
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling tempfile v3.27.0
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling rayon v1.12.0
   Compiling rand v0.8.6
   Compiling hashlink v0.9.1
   Compiling phf_generator v0.11.3
   Compiling pest_meta v2.9.4
   Compiling phf_codegen v0.11.3
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling chrono-tz-build v0.3.0
   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
   Compiling chrono-tz v0.9.0
   Compiling globwalk v0.9.1
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling synstructure v0.13.2
   Compiling serde_derive v1.0.228
   Compiling tokio-macros v2.7.0
   Compiling tracing-attributes v0.1.31
   Compiling zerovec-derive v0.11.3
   Compiling displaydoc v0.2.5
   Compiling futures-macro v0.3.32
   Compiling thiserror-impl v1.0.69
   Compiling thiserror-impl v2.0.18
   Compiling async-trait v0.1.89
   Compiling async-stream-impl v0.3.6
   Compiling arbitrary v1.5.0
   Compiling async-stream v0.3.6
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling pest_derive v2.9.4
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling tracing v0.1.44
   Compiling clap v4.6.7
   Compiling zerofrom v0.1.7
   Compiling simple_asn1 v0.6.4
   Compiling table_formatter v0.6.1
   Compiling tower-http v0.5.2
   Compiling clap-cargo v0.18.3
   Compiling yoke v0.8.2
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling matchers v0.2.0
   Compiling tracing-subscriber v0.3.23
   Compiling json5 v0.4.1
   Compiling dashmap v6.1.0
   Compiling serde_urlencoded v0.7.1
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
   Compiling pyo3-macros v0.22.6
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling icu_collections v2.2.0
   Compiling icu_locale_core v2.2.0
   Compiling axum-core v0.4.5
   Compiling icu_provider v2.2.0
   Compiling tokei v15.0.0
   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling idna_adapter v1.2.2
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling hyper v1.9.0
   Compiling tokio-rustls v0.24.1
   Compiling idna v1.1.0
   Compiling h2 v0.3.27
   Compiling url v2.5.8
   Compiling hyper-util v0.1.20
   Compiling axum v0.7.9
   Compiling hyper v0.14.32
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.43.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_gateway v0.43.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.43.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 15m 45s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-ww2xb65o/sase_core_rs-0.43.2-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/088ba969d471935ce280dd520220153639e97d9d75887eb31e37ccf6a1d206ce/sase_core_rs-0.43.2-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 63ms
Uninstalled 1 package in 2ms
Installed 1 package in 9ms
 - sase-core-rs==0.43.2 (from file:///home/bryan/.sase/cache/sase-core-artifacts/ded739e8de6a73685bfae0978b1c7ff49ded6b506d9d8164ad15071ca991b58b/sase_core_rs-0.43.2-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.43.2 (from file:///home/bryan/.sase/cache/sase-core-artifacts/088ba969d471935ce280dd520220153639e97d9d75887eb31e37ccf6a1d206ce/sase_core_rs-0.43.2-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: no exact cached wheel
[sase-core-wheel-cache] Waiting for the shared build lock for 5049b56b8599 (up to 900s).
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/5049b56b85994f77ad6f69bdd871f56ad026e166fc97897bf69ba538240ba4c3/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/bin/sase-macro-lsp
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
7.88s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.29s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.25s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 19.05s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/d6d17a3c48444b86a3df4142a06ea1d9/manifest.json
run-dir: .pytest_cache/sase-visual/runs/d6d17a3c48444b86a3df4142a06ea1d9
report: .pytest_cache/sase-visual/runs/d6d17a3c48444b86a3df4142a06ea1d9/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/d6d17a3c48444b86a3df4142a06ea1d9/report/summary.md
manifest d6d17a3c48444b86a3df4142a06ea1d9 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 15/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
7.61s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
4.87s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.17s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 18.83s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/068e9c62e03b410c96a737a082c7ff8e/manifest.json
run-dir: .pytest_cache/sase-visual/runs/068e9c62e03b410c96a737a082c7ff8e
report: .pytest_cache/sase-visual/runs/068e9c62e03b410c96a737a082c7ff8e/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/068e9c62e03b410c96a737a082c7ff8e/report/summary.md
manifest 068e9c62e03b410c96a737a082c7ff8e counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 16/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
6.68s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.37s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 18.32s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/6b22280e19a644f68e200f9e4a868d39/manifest.json
run-dir: .pytest_cache/sase-visual/runs/6b22280e19a644f68e200f9e4a868d39
report: .pytest_cache/sase-visual/runs/6b22280e19a644f68e200f9e4a868d39/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/6b22280e19a644f68e200f9e4a868d39/report/summary.md
manifest 6b22280e19a644f68e200f9e4a868d39 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 17/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
8.03s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
4.93s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 18.54s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/ee9462c47afd45958c67b2fb079030c2/manifest.json
run-dir: .pytest_cache/sase-visual/runs/ee9462c47afd45958c67b2fb079030c2
report: .pytest_cache/sase-visual/runs/ee9462c47afd45958c67b2fb079030c2/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/ee9462c47afd45958c67b2fb079030c2/report/summary.md
manifest ee9462c47afd45958c67b2fb079030c2 counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 18/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
7.38s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.28s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 18.50s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/2945d35f4cf942bfb980ed842c400a0f/manifest.json
run-dir: .pytest_cache/sase-visual/runs/2945d35f4cf942bfb980ed842c400a0f
report: .pytest_cache/sase-visual/runs/2945d35f4cf942bfb980ed842c400a0f/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/2945d35f4cf942bfb980ed842c400a0f/report/summary.md
manifest 2945d35f4cf942bfb980ed842c400a0f counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 19/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
6.55s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
4.98s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.16s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 17.96s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/5a2dbbd3cfc0493aaab98ed66193800e/manifest.json
run-dir: .pytest_cache/sase-visual/runs/5a2dbbd3cfc0493aaab98ed66193800e
report: .pytest_cache/sase-visual/runs/5a2dbbd3cfc0493aaab98ed66193800e/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/5a2dbbd3cfc0493aaab98ed66193800e/report/summary.md
manifest 5a2dbbd3cfc0493aaab98ed66193800e counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
serial screenshot proof 20/20
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
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
7.74s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_stranded.py::test_agents_stranded_resolve_modal_png_snapshot
5.29s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.17s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 19.48s ==============================
fix-tui-screenshots: check clean
scope: targeted
counts: created=0 updated=0 unchanged=2 stale=0
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
manifest: .pytest_cache/sase-visual/runs/ecb7404579ec4e8fb62c709174f3845d/manifest.json
run-dir: .pytest_cache/sase-visual/runs/ecb7404579ec4e8fb62c709174f3845d
report: .pytest_cache/sase-visual/runs/ecb7404579ec4e8fb62c709174f3845d/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/ecb7404579ec4e8fb62c709174f3845d/report/summary.md
manifest ecb7404579ec4e8fb62c709174f3845d counts {'created': 0, 'stale': 0, 'unchanged': 2, 'updated': 0} unstable 0 errors 0
succeeded  exit=0  duration=1722170ms

