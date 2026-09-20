# Chat History - ace-run (sase-12z.4--mon-4)

- **TIMESTAMP:** 2026-09-18 17:54:04 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-12z.4--mon-4

## Prompt

sase monitor start --command 'just fix-tui-screenshots --check' --reason 'sase-12z.4 --check after inspecting full inventory e91e4605c16047a49d7bbbb1bacf2731 (643 ACE chrome/procs-default updates, 1 stale prune, pager unchanged)'

## Response

[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/linked/sase-core to origin/master
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [967 items]

........................................................................ [  7%]
........................................................................ [ 14%]
........................................................................ [ 22%]
........................................................................ [ 29%]
........................................................................ [ 37%]
........................................................................ [ 44%]
........................................................................ [ 52%]
........................................................................ [ 59%]
........................................................................ [ 67%]
........................................................................ [ 74%]
........................................................................ [ 81%]
........................................................................ [ 89%]
........................................................................ [ 96%]
...............................                                          [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
33.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
29.51s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
15.32s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
14.52s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
14.16s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
13.98s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
13.40s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot
12.74s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
12.38s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_ordered_highlight_solo_png_snapshot[textual-light-prompt_ordered_highlight_solo_light_120x40-ACE prompt input \u2014 ordered-marker highlighting, light theme]
12.04s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
12.02s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
12.00s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots
11.91s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_scoped_frontmatter_png_snapshot
11.74s call     tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py::test_fuzzy_at_reference_payload_panel_png_snapshot
11.58s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_vim_cursor_normal_png_snapshot
11.41s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_family_bead_and_plan_context_png_snapshot
11.23s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_parked_png_snapshot
11.12s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_readonly_png_snapshot
11.11s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_dirty_png_snapshot
11.11s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_full_menu_png_snapshot[dark]
=========== 967 passed, 1 skipped, 14 warnings in 291.03s (0:04:51) ============
fix-tui-screenshots: check clean
scope: full
counts: created=0 updated=0 unchanged=706 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/agent_neighbor_folded_clan_modal_70x32.png
  tests/ace/tui/visual/snapshots/png/agent_neighbor_modal_descendants_dismissed_60x30.png
  tests/ace/tui/visual/snapshots/png/agent_workspace_tmux_modal_100x28.png
  tests/ace/tui/visual/snapshots/png/agents_artifact_type_icons_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_icons_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_metadata_epic_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_metadata_plan_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_metadata_tale_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_workflow_child_alignment_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_auto_approve_xprompts_metadata_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_capacity_budget_accent_120x40.png
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
  tests/ace/tui/visual/snapshots/png/agents_collapsed_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_collapsed_panel_jump_hints_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_commit_messages_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_epic_phase_roadmap_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_equal_file_layout_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_and_lone_planner_color_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_conversation_level_1_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_conversation_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_conversation_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_gate_output_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_lane_neighbors_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_level_1_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_member_override_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_member_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_pending_digit_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_gate_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_gate_90x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_monitor_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_monitor_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_family_panel_two_digit_roster_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_filter_bar_editing_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_filter_bar_idle_readout_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_empty_no_machine_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_followed_partial_offline_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_keyboard_focus_narrow_82x28.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_loaded_zero_results_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_fleet_unavailable_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_group_clan_collapse_precedence_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_group_lane_collapse_precedence_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_above_context_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_section_expanded_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_section_first_level_160x50.png
  tests/ace/tui/visual/snapshots/png/agents_leader_jump_auto_expanded_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_linked_repo_diff_file_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_list_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_llm_calls_panel_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_llm_calls_panel_full_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_llm_calls_panel_populated_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_metadata_search_committed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_metadata_search_typing_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_degraded_90x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_failed_diagnostics_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_monitor_state_failed_diagnostics_90x40.png
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
  tests/ace/tui/visual/snapshots/png/agents_neighbor_badge_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_neighbor_jump_expanded_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_onboarding_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_onboarding_no_plugins_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_output_variables_multi_agent_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_overflowing_panel_full_height_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_panel_fold_collapse_all_tribes_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_panel_fold_selection_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_panel_fold_sweep_armed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_parallel_family_no_counts_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_partially_streamed_context_lanes_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_pending_plan_status_colors_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_plan_goal_metadata_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_plan_handoff_status_colors_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_proc_shell_detail_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_proc_shells_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_proc_shells_90x30.png
  tests/ace/tui/visual/snapshots/png/agents_python_step_hidden_collapsed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_python_step_parent_family_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_queued_clan_counts_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_renamed_generic_family_root_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_reserved_tribe_wait_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_completed_chain_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_countdown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_e2e_completed_chain_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_e2e_countdown_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_retry_e2e_plan_family_countdown_120x40.png
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
  tests/ace/tui/visual/snapshots/png/agents_running_family_runtime_collapsed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_running_family_runtime_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_selected_clan_collapse_precedence_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_selected_panel_clan_collapse_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_selected_row_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_settled_monitor_lane_badge_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_sole_selected_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_stopped_status_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_task_bead_notes_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_display_config_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_isolation_armed_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_1_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_2_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_3_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_4_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_tribe_panel_selected_expanded_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_unread_highlight_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_view_picker_three_layouts_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_family_child_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_missing_target_row_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_single_bead_labels_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_single_bead_labels_90x32.png
  tests/ace/tui/visual/snapshots/png/agents_waiting_tribe_target_row_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_weighted_runner_capacity_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_weighted_runner_capacity_expanded_80x32.png
  tests/ace/tui/visual/snapshots/png/agents_xprompt_panel_highlighting_120x40.png
  tests/ace/tui/visual/snapshots/png/agents_xprompt_panel_highlighting_light_120x40.png
  tests/ace/tui/visual/snapshots/png/alias_overrides_indicator_multi_120x40.png
  tests/ace/tui/visual/snapshots/png/alias_overrides_indicator_single_120x40.png
  tests/ace/tui/visual/snapshots/png/artifact_links_panel_26_links_120x40.png
  tests/ace/tui/visual/snapshots/png/artifact_links_panel_3_links_120x40.png
  tests/ace/tui/visual/snapshots/png/artifact_links_panel_dangling_row_120x40.png
  tests/ace/tui/visual/snapshots/png/artifact_links_panel_needs_reveal_row_120x40.png
  tests/ace/tui/visual/snapshots/png/artifact_links_panel_staleness_notice_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_agents_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_agents_family_grouped_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_agents_filter_completion_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_agents_filter_parse_error_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_agents_narrow_80x24.png
  tests/ace/tui/visual/snapshots/png/artifacts_agents_populated_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_beads_collapsed_relations_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_beads_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_beads_idle_query_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_beads_populated_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_beads_reopened_detail_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_description_full_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_description_off_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_description_summary_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_description_unconfigured_provider_hint_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_files_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_files_idle_placeholder_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_files_nested_strip_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_files_populated_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_plans_all_projects_populated_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_plans_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_plans_filter_bar_prefilled_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_plans_filter_completion_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_plans_filter_parse_error_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_plans_narrowed_filter_bar_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_plans_populated_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_split_even_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_split_narrow_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_split_narrow_80x24.png
  tests/ace/tui/visual/snapshots/png/artifacts_split_selected_even_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_split_selected_narrow_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_split_selected_narrow_80x24.png
  tests/ace/tui/visual/snapshots/png/artifacts_split_selected_wide_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_split_wide_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_filter_bar_prefilled_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_filter_completion_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_filter_parse_error_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_jump_hints_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_merge_row_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_narrowed_filter_chips_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_origin_legend_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_persistent_filter_80x24.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_sidecar_filter_120x40.png
  tests/ace/tui/visual/snapshots/png/artifacts_stitches_timeline_detail_120x40.png
  tests/ace/tui/visual/snapshots/png/at_reference_completion_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/at_reference_fuzzy_payload_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/at_reference_truncated_payload_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_add_chooser_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_controlled_output_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_description_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_description_collapsed_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_editor_advanced_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_editor_basics_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_overrun_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_overrun_narrow_70x36.png
  tests/ace/tui/visual/snapshots/png/axe_chop_report_absent_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_report_error_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_report_narrow_70x36.png
  tests/ace/tui/visual/snapshots/png/axe_chop_report_rich_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_run_info_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_chop_run_info_panel_running_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_constrained_width_no_wrap_60x30.png
  tests/ace/tui/visual/snapshots/png/axe_description_overflow_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_disabled_chop_row_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_editor_compact_lumberjack_sheet_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_editor_constrained_width_70x36.png
  tests/ace/tui/visual/snapshots/png/axe_editor_diff_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_editor_multiline_yaml_cell_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_editor_single_line_cell_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_editor_validation_failure_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_generated_instance_warning_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_long_label_widened_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_lumberjack_description_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_lumberjack_error_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_lumberjack_tree_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_new_lumberjack_identity_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_script_picker_120x40.png
  tests/ace/tui/visual/snapshots/png/axe_selected_row_120x40.png
  tests/ace/tui/visual/snapshots/png/changespec_initial_120x40.png
  tests/ace/tui/visual/snapshots/png/changespec_selected_row_120x40.png
  tests/ace/tui/visual/snapshots/png/changespecs_onboarding_120x40.png
  tests/ace/tui/visual/snapshots/png/changespecs_onboarding_no_match_120x40.png
  tests/ace/tui/visual/snapshots/png/command_palette_default_120x40.png
  tests/ace/tui/visual/snapshots/png/commit_plan_view_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/commit_view_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_agent_clis_history_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_agent_clis_history_all_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_agent_clis_history_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_agent_clis_marked_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_agent_clis_update_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_comprehensive_update_preview_120x32.png
  tests/ace/tui/visual/snapshots/png/config_center_config_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_config_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_config_long_value_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_config_object_value_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_config_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_config_tab_flags_off_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_edit_enum_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_edit_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_edit_normal_mode_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_edit_object_value_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_edit_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_flags_confirm_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_flags_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_flags_populated_70x32.png
  tests/ace/tui/visual/snapshots/png/config_center_flags_populated_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_flags_populated_light_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_home_100x24.png
  tests/ace/tui/visual/snapshots/png/config_center_home_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_home_resume_procs_100x24.png
  tests/ace/tui/visual/snapshots/png/config_center_home_resume_procs_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_launch_default_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_launch_provider_disabled_70x32.png
  tests/ace/tui/visual/snapshots/png/config_center_logs_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_logs_tab_focused_error_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_logs_tab_toasts_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_community_detail_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_core_update_available_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_dev_update_available_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_install_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_long_description_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_long_update_preview_100x24.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_marked_install_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_not_uv_tool_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_offline_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_uninstall_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_update_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_plugins_verbose_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_procs_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_procs_tab_filtered_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_procs_tab_monitors_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_procs_tab_monitors_90x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_current_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_detail_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_inactive_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_init_plan_all_mixed_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_init_plan_danger_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_init_plan_diffs_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_init_plan_narrow_80x24.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_init_plan_single_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_init_plan_tty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_marked_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_projects_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_repos_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_activity_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_help_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_perf_degraded_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_plans_questions_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_drilldown_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_providers_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_runners_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_xprompts_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_xprompts_focus_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_xprompts_model_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_statistics_xprompts_narrow_90x30.png
  tests/ace/tui/visual/snapshots/png/config_center_updates_all_current_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_updates_digest_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_updates_failed_source_header_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_updates_marks_hidden_by_filter_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_updates_outdated_scope_all_current_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_updates_outdated_scope_cli_only_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_updates_outdated_scope_plugin_only_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_workspaces_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_xprompts_filter_120x40.png
  tests/ace/tui/visual/snapshots/png/config_center_xprompts_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/confirm_dialog_danger_120x40.png
  tests/ace/tui/visual/snapshots/png/confirm_dialog_dismiss_all_120x40.png
  tests/ace/tui/visual/snapshots/png/confirm_dialog_kill_all_escalated_120x40.png
  tests/ace/tui/visual/snapshots/png/confirm_dialog_neutral_120x40.png
  tests/ace/tui/visual/snapshots/png/copy_as_over_artifact_files_modal_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/copy_as_over_preview_panel_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/copy_as_stitches_marked_light_80x30.png
  tests/ace/tui/visual/snapshots/png/copy_as_stitches_selected_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/current_project_indicator_120x40.png
  tests/ace/tui/visual/snapshots/png/custom_gate_actions_120x40.png
  tests/ace/tui/visual/snapshots/png/custom_gate_choices_only_120x40.png
  tests/ace/tui/visual/snapshots/png/custom_gate_draft_banner_120x40.png
  tests/ace/tui/visual/snapshots/png/custom_gate_extras_120x40.png
  tests/ace/tui/visual/snapshots/png/custom_gate_frontmatter_120x40.png
  tests/ace/tui/visual/snapshots/png/custom_gate_inputs_120x45.png
  tests/ace/tui/visual/snapshots/png/custom_gate_no_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/custom_gate_password_warning_120x40.png
  tests/ace/tui/visual/snapshots/png/custom_gate_required_feedback_120x40.png
  tests/ace/tui/visual/snapshots/png/custom_gate_task_triage_120x40.png
  tests/ace/tui/visual/snapshots/png/disabled_provider_launch_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/disabled_provider_launch_panel_swarm_120x40.png
  tests/ace/tui/visual/snapshots/png/footer_leader_overflow_120x40.png
  tests/ace/tui/visual/snapshots/png/footer_leader_overflow_80x30.png
  tests/ace/tui/visual/snapshots/png/frontmatter_input_item_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/frontmatter_panel_cell_edit_120x40.png
  tests/ace/tui/visual/snapshots/png/frontmatter_panel_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/frontmatter_panel_error_120x40.png
  tests/ace/tui/visual/snapshots/png/frontmatter_panel_ghost_row_120x40.png
  tests/ace/tui/visual/snapshots/png/frontmatter_panel_populated_120x40.png
  tests/ace/tui/visual/snapshots/png/frontmatter_panel_raw_diagnostics_120x40.png
  tests/ace/tui/visual/snapshots/png/frontmatter_panel_saved_feedback_120x40.png
  tests/ace/tui/visual/snapshots/png/frontmatter_xprompt_item_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/gate_debug_answered_response_120x40.png
  tests/ace/tui/visual/snapshots/png/gate_debug_pending_overview_120x40.png
  tests/ace/tui/visual/snapshots/png/gate_input_panel_group_120x45.png
  tests/ace/tui/visual/snapshots/png/gate_input_panel_note_120x40.png
  tests/ace/tui/visual/snapshots/png/gate_input_panel_single_120x45.png
  tests/ace/tui/visual/snapshots/png/glossary_preview_card_full_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/glossary_preview_card_full_light_120x40.png
  tests/ace/tui/visual/snapshots/png/glossary_preview_card_minimal_120x40.png
  tests/ace/tui/visual/snapshots/png/header_usage_long_title_80x24.png
  tests/ace/tui/visual/snapshots/png/help_guide_agents_120x40.png
  tests/ace/tui/visual/snapshots/png/help_guide_axe_120x40.png
  tests/ace/tui/visual/snapshots/png/help_guide_changespecs_120x40.png
  tests/ace/tui/visual/snapshots/png/help_keymaps_changespecs_120x40.png
  tests/ace/tui/visual/snapshots/png/help_keymaps_filter_120x40.png
  tests/ace/tui/visual/snapshots/png/history_word_completion_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/input_collection_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/input_collection_modal_error_120x40.png
  tests/ace/tui/visual/snapshots/png/inventory_project_picker_120x40.png
  tests/ace/tui/visual/snapshots/png/jump_action_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/link_rail_agents_single_link_120x40.png
  tests/ace/tui/visual/snapshots/png/link_rail_agents_single_link_60x30.png
  tests/ace/tui/visual/snapshots/png/link_rail_artifacts_three_links_120x40.png
  tests/ace/tui/visual/snapshots/png/link_rail_artifacts_three_links_60x30.png
  tests/ace/tui/visual/snapshots/png/link_rail_axe_twelve_links_120x40.png
  tests/ace/tui/visual/snapshots/png/link_rail_axe_twelve_links_60x30.png
  tests/ace/tui/visual/snapshots/png/link_rail_dangling_row_120x40.png
  tests/ace/tui/visual/snapshots/png/link_reveal_chip_beads_120x40.png
  tests/ace/tui/visual/snapshots/png/link_reveal_chip_beads_60x30.png
  tests/ace/tui/visual/snapshots/png/mini_xprompt_name_edit_existing_120x40.png
  tests/ace/tui/visual/snapshots/png/mini_xprompt_name_fresh_completion_120x40.png
  tests/ace/tui/visual/snapshots/png/mini_xprompt_name_incompatible_swarm_120x40.png
  tests/ace/tui/visual/snapshots/png/mini_xprompt_pane_clean_light_120x40.png
  tests/ace/tui/visual/snapshots/png/mini_xprompt_pane_dirty_120x40.png
  tests/ace/tui/visual/snapshots/png/mini_xprompt_pane_new_120x40.png
  tests/ace/tui/visual/snapshots/png/mini_xprompt_pane_stale_120x40.png
  tests/ace/tui/visual/snapshots/png/mini_xprompt_save_diff_120x40.png
  tests/ace/tui/visual/snapshots/png/mini_xprompt_scoped_frontmatter_120x40.png
  tests/ace/tui/visual/snapshots/png/model_picker_usage_hints_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_alias_effort_picker_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_alias_history_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_alias_history_legacy_only_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_alias_history_populated_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_alias_history_truncated_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_alias_history_usage_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_alias_picker_filtered_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_alias_picker_reordered_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_bucket_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_bucket_drilled_in_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_builtin_effort_picker_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_custom_builtin_warning_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_default_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_duration_picker_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_edit_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_effort_action_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_effort_edit_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_effort_level_edit_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_effort_level_override_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_effort_override_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_effort_provenance_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_empty_custom_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_jump_mixed_bucket_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_jump_top_level_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_long_pool_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_mixed_builtin_bucket_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_overrides_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_pool_effort_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_pool_suspended_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_disabled_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_duration_picker_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_duration_picker_keep_window_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_priority_duration_picker_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_priority_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_priority_modal_narrow_70x32.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_priority_unavailable_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_priority_until_cleared_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_routing_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_routing_modal_narrow_70x32.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_routing_until_cleared_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_provider_soft_disabled_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_runner_limit_action_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_runner_limit_edit_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_runner_limit_override_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_runner_limit_value_edit_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_runner_limit_value_override_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_selector_builder_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_smartest_max_effort_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_tmux_agent_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_until_error_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_until_neutral_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_until_valid_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_worker_drilled_in_120x40.png
  tests/ace/tui/visual/snapshots/png/models_panel_worker_override_drilled_in_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_beads_recent_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_beads_tab_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_beads_typed_gates_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_filed_by_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_gate_answered_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_gate_pending_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_indicator_chips_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_indicator_kind_chips_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_indicator_snoozed_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_plus_one_badge_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_plus_one_pane_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_question_summary_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_report_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_report_pane_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_selected_snooze_status_120x40.png
  tests/ace/tui/visual/snapshots/png/notification_sent_at_120x40.png
  tests/ace/tui/visual/snapshots/png/patch_filter_bar_closed_120x40.png
  tests/ace/tui/visual/snapshots/png/patch_filter_bar_completion_120x40.png
  tests/ace/tui/visual/snapshots/png/placeholder_common_completion_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/placeholder_completion_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/placeholder_highlight_120x40.png
  tests/ace/tui/visual/snapshots/png/placeholder_raw_only_highlight_120x40.png
  tests/ace/tui/visual/snapshots/png/plan_gate_epic_action_120x40.png
  tests/ace/tui/visual/snapshots/png/plan_gate_frontmatter_120x40.png
  tests/ace/tui/visual/snapshots/png/plan_gate_tale_five_controls_120x40.png
  tests/ace/tui/visual/snapshots/png/plan_gate_tale_stacked_90x40.png
  tests/ace/tui/visual/snapshots/png/plan_toast_epic_120x40.png
  tests/ace/tui/visual/snapshots/png/plan_toast_tale_120x40.png
  tests/ace/tui/visual/snapshots/png/post_update_toast_120x40.png
  tests/ace/tui/visual/snapshots/png/post_update_toast_diffstat_120x40.png
  tests/ace/tui/visual/snapshots/png/preview_panel_active_search_120x40.png
  tests/ace/tui/visual/snapshots/png/preview_panel_file_120x40.png
  tests/ace/tui/visual/snapshots/png/preview_panel_properties_band_120x40.png
  tests/ace/tui/visual/snapshots/png/preview_panel_properties_view_120x40.png
  tests/ace/tui/visual/snapshots/png/preview_panel_reference_120x40.png
  tests/ace/tui/visual/snapshots/png/preview_panel_xprompt_120x40.png
  tests/ace/tui/visual/snapshots/png/project_select_modal_default_120x40.png
  tests/ace/tui/visual/snapshots/png/project_select_modal_filtered_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_artifact_ref_highlight_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_bullet_highlight_solo_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_bullet_highlight_solo_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_codeblock_highlight_solo_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_codeblock_highlight_solo_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_codeblock_highlight_stack_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_codeblock_highlight_stack_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_cursor_readout_solo_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_cursor_readout_stack_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_finalizer_completion_mixed_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_finalizer_completion_mixed_70x24.png
  tests/ace/tui/visual/snapshots/png/prompt_fork_target_completion_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_glossary_highlight_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_glossary_highlight_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_glossary_wrapped_highlight_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_history_modal_redesign_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_inputs_long_value_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_inputs_mixed_literal_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_inputs_placeholders_only_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_jinja_invalid_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_jinja_valid_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_misspelling_highlight_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_misspelling_highlight_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_alias_completion_filtered_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_alias_completion_full_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_alias_completion_full_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_alias_completion_narrow_70x24.png
  tests/ace/tui/visual/snapshots/png/prompt_model_alias_completion_stack_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_completion_aliases_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_completion_mixed_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_completion_provider_scoped_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_explicit_completion_advisory_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_explicit_completion_filtered_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_explicit_completion_full_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_explicit_completion_full_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_explicit_completion_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_explicit_completion_scoped_narrow_70x24.png
  tests/ace/tui/visual/snapshots/png/prompt_model_explicit_completion_stack_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_model_explicit_completion_unavailable_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_ordered_highlight_solo_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_ordered_highlight_solo_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_repo_mention_highlight_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_search_count_pill_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_search_count_pill_flexoki_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_search_count_pill_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_search_highlight_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_skill_completion_long_description_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_active_upper_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_compact_inactive_80x30.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_completion_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_g_prefix_hints_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_snippet_dirty_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_snippet_new_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_snippet_parked_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_targeted_clean_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_targeted_dirty_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_targeted_readonly_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_stack_two_panes_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_submit_choice_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_submit_choice_targeted_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_todo_restored_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_todo_restored_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_todo_stack_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_vim_cursor_insert_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_vim_cursor_normal_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_vim_cursor_visual_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_wait_target_completion_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_word_completion_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_xprompt_arg_completion_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_xprompt_arg_completion_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_xprompt_argument_highlight_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_xprompt_argument_highlight_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_xprompt_highlight_solo_light_120x40.png
  tests/ace/tui/visual/snapshots/png/prompt_xprompt_highlight_stack_120x40.png
  tests/ace/tui/visual/snapshots/png/provider_disables_indicator_multiple_120x40.png
  tests/ace/tui/visual/snapshots/png/provider_disables_indicator_single_120x40.png
  tests/ace/tui/visual/snapshots/png/provider_disables_indicator_soft_120x40.png
  tests/ace/tui/visual/snapshots/png/provider_drain_prompt_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/provider_priority_indicator_combined_120x40.png
  tests/ace/tui/visual/snapshots/png/provider_priority_unavailable_indicator_120x40.png
  tests/ace/tui/visual/snapshots/png/recursive_finder_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/refresh_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/refresh_panel_full_history_banner_120x40.png
  tests/ace/tui/visual/snapshots/png/repo_preview_card_120x40.png
  tests/ace/tui/visual/snapshots/png/revert_confirm_modal_bulk_120x40.png
  tests/ace/tui/visual/snapshots/png/revert_confirm_modal_single_120x40.png
  tests/ace/tui/visual/snapshots/png/sase_agent_cleanup_confirmation_120x40.png
  tests/ace/tui/visual/snapshots/png/saved_agent_group_revival_empty_120x40.png
  tests/ace/tui/visual/snapshots/png/saved_agent_group_revival_jump_mode_120x40.png
  tests/ace/tui/visual/snapshots/png/saved_agent_group_revival_load_more_120x40.png
  tests/ace/tui/visual/snapshots/png/saved_agent_group_revival_normal_120x40.png
  tests/ace/tui/visual/snapshots/png/saved_agent_group_revival_preview_rich_120x40.png
  tests/ace/tui/visual/snapshots/png/saved_query_picker_100x32.png
  tests/ace/tui/visual/snapshots/png/snippet_name_collision_120x40.png
  tests/ace/tui/visual/snapshots/png/snippet_save_confirm_diff_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_add_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_add_light_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_delete_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_delete_light_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_diagnostic_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_diagnostic_light_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_empty_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_empty_light_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_populated_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_populated_light_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_relation_dark_120x40.png
  tests/ace/tui/visual/snapshots/png/snippets_panel_relation_light_120x40.png
  tests/ace/tui/visual/snapshots/png/spellcheck_panel_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/spellcheck_panel_modal_full_120x40.png
  tests/ace/tui/visual/snapshots/png/spellcheck_panel_modal_no_suggestions_120x40.png
  tests/ace/tui/visual/snapshots/png/startup_update_toast_120x40.png
  tests/ace/tui/visual/snapshots/png/startup_update_toast_grouped_commits_120x40.png
  tests/ace/tui/visual/snapshots/png/stashed_prompts_bundle_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/stashed_prompts_indicator_badge_120x40.png
  tests/ace/tui/visual/snapshots/png/stashed_prompts_narrow_modal_100x40.png
  tests/ace/tui/visual/snapshots/png/stashed_prompts_restore_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/sudo_request_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/sudo_request_modal_details_120x40.png
  tests/ace/tui/visual/snapshots/png/top_bar_compact_usage_badges_120x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_disable_pill_usage_dark_160x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_disable_pill_usage_light_160x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_attention_80x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_badges_crowded_60x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_claude_three_windows_140x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_collector_failure_140x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_display_states_140x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_groups_real_projection_140x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_groups_weekly_dark_160x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_groups_weekly_light_160x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_no_observation_140x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_palette_dark_240x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_palette_light_240x24.png
  tests/ace/tui/visual/snapshots/png/top_bar_usage_partial_group_overflow_80x24.png
  tests/ace/tui/visual/snapshots/png/update_panel_pending_120x40.png
  tests/ace/tui/visual/snapshots/png/update_panel_unchecked_120x40.png
  tests/ace/tui/visual/snapshots/png/update_pinned_stash_preview_120x40.png
  tests/ace/tui/visual/snapshots/png/updates_indicator_agent_cli_only_120x40.png
  tests/ace/tui/visual/snapshots/png/updates_indicator_core_rebuild_120x40.png
  tests/ace/tui/visual/snapshots/png/updates_indicator_mixed_core_rebuild_120x40.png
  tests/ace/tui/visual/snapshots/png/updates_indicator_mixed_routine_120x40.png
  tests/ace/tui/visual/snapshots/png/updates_indicator_routine_120x40.png
  tests/ace/tui/visual/snapshots/png/vcs_project_completion_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/vcs_ref_completion_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/vcs_ref_completion_panel_no_orgs_120x40.png
  tests/ace/tui/visual/snapshots/png/vcs_ref_completion_panel_placeholder_120x40.png
  tests/ace/tui/visual/snapshots/png/vcs_repo_completion_error_120x40.png
  tests/ace/tui/visual/snapshots/png/vcs_repo_completion_loading_120x40.png
  tests/ace/tui/visual/snapshots/png/vcs_repo_completion_panel_120x40.png
  tests/ace/tui/visual/snapshots/png/wait_modal_100x32.png
  tests/ace/tui/visual/snapshots/png/wait_modal_beads_focused_100x32.png
  tests/ace/tui/visual/snapshots/png/word_definition_modal_120x40.png
  tests/ace/tui/visual/snapshots/png/xprompt_save_collision_armed_diff_120x40.png
  tests/ace/tui/visual/snapshots/png/xprompt_save_create_120x40.png
  tests/ace/tui/visual/snapshots/png/xprompt_save_no_writable_locations_120x40.png
  tests/ace/tui/visual/snapshots/png/xprompt_save_snippet_mode_120x40.png
manifest: .pytest_cache/sase-visual/runs/5e9866cfc36547e19babbe85ce531da4/manifest.json
run-dir: .pytest_cache/sase-visual/runs/5e9866cfc36547e19babbe85ce531da4
report: .pytest_cache/sase-visual/runs/5e9866cfc36547e19babbe85ce531da4/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/5e9866cfc36547e19babbe85ce531da4/report/summary.md

