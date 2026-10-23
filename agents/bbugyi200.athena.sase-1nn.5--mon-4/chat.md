# Chat History - ace-run (sase-1nn.5--mon-4)

- **TIMESTAMP:** 2026-10-23 15:33:12 EDT
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1nn.5--mon-4

## Prompt

sase monitor start --command 'env TZ=UTC just test-visual' --reason 'Run the full TZ=UTC screenshot check for visual-lane'

## Response

sase tool run 993a02657cfef2fefa4b420b38de1a6a
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.42.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-visual              │
└───────────────────────────────────────────────────────┘

---------- Checking TUI screenshot goldens... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, mock-3.16.0, inline-snapshot-0.36.0, asyncio-1.4.0, hypothesis-6.168.5, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [1384 items]

........................................................................ [  5%]
........................................................................ [ 10%]
........................................................................ [ 15%]
........................................................................ [ 20%]
........................................................................ [ 26%]
........................................................................ [ 31%]
........................................................................ [ 36%]
........................................................................ [ 41%]
........................................................................ [ 46%]
........................................................................ [ 52%]
........................................................................ [ 57%]
........................................................................ [ 62%]
........................................................................ [ 67%]
........................................................................ [ 72%]
........................................................................ [ 78%]
........................................................................ [ 83%]
........................................................................ [ 88%]
........................................................................ [ 93%]
........................................................................ [ 98%]
................                                                         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
44.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
38.94s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
23.50s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
22.98s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_cards.py::test_tool_runs_card_png_snapshots
21.42s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
18.17s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_layered_wave_dividers_png_snapshot[80]
17.29s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
17.10s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_parked_png_snapshot
16.99s call     tests/ace/tui/visual/test_ace_png_snapshots_jinja_completion.py::test_jinja_filter_completion_png_snapshot
16.70s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_dirty_png_snapshot
15.73s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_dirty_png_snapshot
15.35s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
15.18s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_search_operator.py::test_prompt_search_operator_delete_preview_png_snapshot
14.61s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_collapsed_two_digit_overflow_png_snapshot
14.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_clan_waves_ladder_png_snapshots
14.41s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
14.29s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_narrowed_png_snapshot
14.26s call     tests/ace/tui/visual/test_ace_png_snapshots_macro_arg_completion.py::test_macro_arg_name_completion_png_snapshot[light]
14.25s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_macro.py::test_mini_macro_pane_dirty_png_snapshot
14.00s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_macro.py::test_mini_macro_pane_new_and_clean_png_snapshots[True-mini_macro_pane_clean_light_120x40-ACE mini-macro pane - clean light]
=========== 1384 passed, 1 skipped, 56 warnings in 459.77s (0:07:39) ===========
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
plugins: cov-7.1.0, mock-3.16.0, inline-snapshot-0.36.0, asyncio-1.4.0, hypothesis-6.168.5, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [3 items]

...                                                                      [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.10s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_session_panel_gate.py::test_agent_session_gate_turns_narrow_png_snapshot
3.65s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
2.87s call     tests/ace/tui/visual/test_ace_png_snapshots_plan_gate.py::test_maxcopy_plan_gate_decisions_png_snapshot
0.18s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_session_panel_gate.py::test_agent_session_gate_turns_narrow_png_snapshot

(5 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 3 passed in 16.32s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
plugins: cov-7.1.0, mock-3.16.0, inline-snapshot-0.36.0, asyncio-1.4.0, hypothesis-6.168.5, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.97s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
3.00s call     tests/ace/tui/visual/test_ace_png_snapshots_plan_gate.py::test_maxcopy_plan_gate_decisions_png_snapshot
0.15s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 13.88s ==============================
fix-tui-screenshots: check drift
scope: full
unstable (passed on recapture):
  tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_session_panel_gate.py::test_agent_session_gate_turns_narrow_png_snapshot after 2 attempt(s)
counts: created=0 updated=2 unchanged=1117 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agents_archive_chooser_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_chooser_marked_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_folded_banners_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_identity_reply_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_list_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_marked_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_missing_content_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_query_bridge_160x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_rebuilding_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_restored_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_restored_toast_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_shelf_empty_inbox_160x40.png
  tests/ace/tui/visual/snapshots/png/agents_archive_shelf_plain_160x40.png
  tests/ace/tui/visual/snapshots/png/agents_artifact_type_icons_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_icons_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_macros_metadata_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_metadata_epic_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_metadata_plan_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_metadata_tale_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_workflow_child_alignment_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_restart_provenance_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_closed_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_bead_created_by_agent_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_bead_note_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_capacity_budget_accent_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_multi_project_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_hints_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_level_3_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_logical_prompt_hints_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_panel_swarm_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_panel_swarm_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_panel_swarm_level_3_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_tree_collapsed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_tree_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_tree_fully_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_tree_fully_expanded_by_status_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_tree_member_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_unread_collapsed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_unread_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_wave_gutter_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_waves_ladder_level_1_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_waves_ladder_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_clan_waves_ladder_level_3_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_collapsed_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_collapsed_panel_jump_hints_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_commit_messages_files_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_commit_messages_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_blocks_arrival_dot_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_blocks_micro_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_blocks_paged_newest_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_blocks_paged_older_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_blocks_split_rails_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_blocks_spread_deck_sticky_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_blocks_spread_landing_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_picker_left_right_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_picker_single_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_deck_picker_split_bottom_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_epic_phase_roadmap_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_filter_bar_editing_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_filter_bar_idle_readout_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_failed_check_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_narrow_tiers_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_overview_unselected_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_picker_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_plugin_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_receipt_deferred_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_receipt_failed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_receipt_running_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_reply_split_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_rows_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_session_blocks_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_final_single_commit_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_followed_partial_offline_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_keyboard_focus_narrow_82x28.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_loaded_zero_results_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_production_sessions_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_remote_tribe_sessions_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_unavailable_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_group_clan_collapse_precedence_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_group_lane_collapse_precedence_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_header_preview_fits_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_header_preview_truncated_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_collapsed_in_flight_mix_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_collapsed_single_section_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_collapsed_two_digit_overflow_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_expanded_two_sections_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_layered_wave_dividers_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_layered_wave_dividers_60x40.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_layered_wave_dividers_80x40.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_llm_calls_layout_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_jump_panel_narrowed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_above_context_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_section_expanded_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_section_first_level_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_linked_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_list_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_llm_calls_panel_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_llm_calls_panel_full_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_llm_calls_panel_populated_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_macro_panel_highlighting_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_macro_panel_highlighting_light_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_macro_panel_tag_highlighting_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_macro_panel_tag_highlighting_light_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_memory_launch_bundle_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_memory_launch_bundle_light_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_memory_launch_bundle_mismatch_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_memory_version_chips_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_memory_version_chips_light_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_metadata_search_committed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_metadata_search_typing_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_degraded_90x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_failed_diagnostics_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_host_completed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_host_completed_90x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_lost_90x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_needs_attention_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_needs_attention_90x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_running_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_running_90x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_timeout_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_timeout_90x40.png
  tests/ace/tui/visual/snapshots/png/agents_named_proc_detail_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_named_procs_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_neighbor_jump_expanded_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_node_rail_80x24.png
  tests/ace/tui/visual/snapshots/png/agents_node_rail_by_project_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_node_rail_by_status_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_node_rail_collapsed_tribes_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_node_rail_jump_hints_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_output_variables_multi_agent_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_panel_fold_collapse_all_tribes_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_panel_fold_sweep_armed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_panel_layout_all_tabs_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_panel_layout_merged_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_panel_layout_modal_three_segment_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_panel_layout_modal_two_segment_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_parallel_session_no_counts_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_partially_streamed_context_lanes_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_pending_plan_status_colors_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_and_plan_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_plan_goal_metadata_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_plan_handoff_status_colors_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_python_step_hidden_collapsed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_python_step_parent_session_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_queued_clan_counts_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_record_archived_lifecycle_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_record_inbox_lifecycle_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_record_links_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_record_unreadable_entry_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_reserved_tribe_wait_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_completed_chain_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_countdown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_e2e_completed_chain_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_e2e_countdown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_e2e_plan_session_countdown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_e2e_running_fallback_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_exhausted_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_running_fallback_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_selected_detail_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_reverted_indicator_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_runner_slot_queue_window_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_runner_slot_waits_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_runner_slot_waits_by_status_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_running_clan_runtime_collapsed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_running_clan_runtime_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_running_session_runtime_collapsed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_running_session_runtime_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_selected_clan_collapse_precedence_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_selected_panel_clan_collapse_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_selected_row_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_and_lone_planner_color_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_conversation_level_1_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_conversation_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_conversation_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_gate_output_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_lane_neighbors_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_level_1_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_member_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_pending_digit_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_gate_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_gate_90x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_turns_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_session_panel_two_digit_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_settled_monitor_lane_badge_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_slow_tool_calls_level_1_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_slow_tool_calls_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_sole_selected_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_stopped_status_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_attention_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_by_machine_on_machine_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_by_machine_on_named_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_feed_unavailable_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_hidden_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_long_name_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_machine_mode_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_named_vs_machine_alias_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_overflow_80x24.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_query_hides_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_stale_host_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tab_strip_standard_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_task_bead_notes_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_clan_summaries_glance_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_clan_summaries_inspect_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_display_config_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_isolation_armed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_1_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_3_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_4_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_prompts_glance_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_prompts_inspect_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_selected_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_epic_follow_blocked_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_epic_follow_following_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_epic_follow_launching_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_epic_follow_multi_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_missing_target_row_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_session_child_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_single_bead_labels_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_tribe_target_row_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_unknown_header_200x40.png
  tests/ace/tui/visual/snapshots/png/agents_weighted_runner_capacity_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_weighted_runner_capacity_expanded_80x32.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/launch_context_bar_agents_120x40.png
  tests/ace/tui/visual/snapshots/png/launch_context_bar_agents_full_160x40.png
  tests/ace/tui/visual/snapshots/png/launch_context_bar_override_120x40.png
  tests/ace/tui/visual/snapshots/png/node_finder_narrow_100x40.png
  tests/ace/tui/visual/snapshots/png/sase_agent_cleanup_confirmation_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_card_failed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_card_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_card_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_card_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_card_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_card_pruned_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_card_session_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_killed_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_known_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_live_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_lost_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_new_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_pass_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_silent_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_stopped_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_header_undetermined_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_picker_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_rows_120x40.png
  tests/ace/tui/visual/snapshots/png/tool_runs_split_120x40.png
manifest: .pytest_cache/sase-visual/runs/99dd30eb2f4142e095d7739f0bf63996/manifest.json
run-dir: .pytest_cache/sase-visual/runs/99dd30eb2f4142e095d7739f0bf63996
report: .pytest_cache/sase-visual/runs/99dd30eb2f4142e095d7739f0bf63996/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/99dd30eb2f4142e095d7739f0bf63996/report/summary.md
update-groups:
  group-1: 1 member(s), tests/ace/tui/visual/snapshots/png/agents_renamed_generic_session_root_120x40.png
  group-2: 1 member(s), tests/ace/tui/visual/snapshots/png/plan_gate_tale_decisions_maxcopy_120x40.png
run: just fix-tui-screenshots
inspect: .pytest_cache/sase-visual/runs/99dd30eb2f4142e095d7739f0bf63996/report/visual-failure-report.html
error: recipe `test-visual` failed on line 634 with exit code 1
failed  exit=1  duration=516507ms

