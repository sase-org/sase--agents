# Chat History - ace-run (019--mon-0)

- **TIMESTAMP:** 2026-09-06 23:25:27 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** 019--mon-0

## Prompt

sase monitor start --command 'SASE_CORE_DIR="$PWD/.venv/published-core" SASE_CORE_WHEEL="$PWD/.venv/pinned-core-wheel/sase_core_rs-0.32.32-cp312-abi3-manylinux_2_28_x86_64.whl" PYTEST_ADDOPTS=-v .venv/bin/python /tmp/sase-ci-check-progress.py' --reason 'Complete full verification of the sase CI fixes; the prior 45-minute run remained active until its timeout'

## Response

n_chop.py::test_action_run_workflow_axe_done_bgcmd_does_not_launch_chop 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_renders_nonempty_applicable_list 
tests/ace/tui/test_agent_completion.py::test_family_completion_candidate_build_does_not_resolve_plan_or_bead_io 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_family_completion_candidate_build_does_not_resolve_plan_or_bead_io 
tests/ace/tui/widgets/test_agent_info_panel.py::test_update_state_full_rebuild_when_stable_state_changes 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_info_panel.py::test_update_state_full_rebuild_when_stable_state_changes 
tests/agents_sync/test_commit_publication.py::test_publication_request_records_the_committing_lane[foo--code-foo] 
tests/ace/tui/test_kill_and_edit_proc_id_rekey.py::test_durable_rekey_makes_resolved_launch_immediately_targetable 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_proc_id_rekey.py::test_durable_rekey_makes_resolved_launch_immediately_targetable 
tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result 
[gw9] [ 95%] PASSED tests/test_bead/test_cli_close_resolution.py::test_conflicting_reclose_is_rejected_without_changing_store 
tests/test_commit_workflow_support.py::test_resolve_head_commit_sha_is_best_effort_on_provider_error 
[gw2] [ 95%] PASSED tests/test_commit_workflow_support.py::test_resolve_head_commit_sha_is_best_effort_on_provider_error 
tests/ace/tui/models/test_changespec_groups_layout.py::test_default_fold_registry_renders_everything_expanded 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_changespec_groups_layout.py::test_default_fold_registry_renders_everything_expanded 
tests/test_commit_workflow_support.py::test_resolve_head_commit_sha_ignores_non_string_results 
tests/ace/tui/models/test_agent_panels.py::test_empty_agents_keep_no_tribe_fallback_panel 
[gw2] [ 95%] PASSED tests/test_commit_workflow_support.py::test_resolve_head_commit_sha_ignores_non_string_results 
[gw0] [ 95%] PASSED tests/ace/tui/models/test_agent_panels.py::test_empty_agents_keep_no_tribe_fallback_panel 
tests/test_command_palette_modal.py::test_modal_focuses_input_on_mount 
tests/ace/tui/test_wait_modal.py::test_modal_prefills_and_returns_explicit_priority 
tests/artifact_file_facade/test_persistence.py::test_persist_default_artifact_files_ignores_explicit_rows_without_source 
[gw4] [ 95%] PASSED tests/agents_sync/test_commit_publication.py::test_publication_request_records_the_committing_lane[foo--code-foo] 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_focuses_input_on_mount 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_persistence.py::test_persist_default_artifact_files_ignores_explicit_rows_without_source 
tests/ace/tui/test_kill_and_edit_proc_id_rekey.py::test_pending_placeholder_kill_survives_durable_proc_id_rekey 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_proc_id_rekey.py::test_pending_placeholder_kill_survives_durable_proc_id_rekey 
tests/ace/tui/test_agent_completion.py::test_build_agent_completion_candidates_humanizes_vcs_badge_and_searches_raw 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_build_agent_completion_candidates_humanizes_vcs_badge_and_searches_raw 
tests/test_bead/test_cli_close_resolution.py::test_close_resolution_round_trips_end_to_end 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_prefills_and_returns_explicit_priority 
tests/ace/tui/models/test_changespec_groups_perf.py::test_by_date_build_parses_each_cs_once 
tests/ace/tui/test_axe_run_chop.py::test_run_selected_chop_outside_axe_tab_is_noop 
tests/test_commit_workflow_support.py::test_resolve_head_commit_sha_ignores_blank_results 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_changespec_groups_perf.py::test_by_date_build_parses_each_cs_once 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_run_selected_chop_outside_axe_tab_is_noop 
[gw2] [ 95%] PASSED tests/test_commit_workflow_support.py::test_resolve_head_commit_sha_ignores_blank_results 
tests/ace/tui/widgets/test_agent_info_panel.py::test_update_state_routes_unchanged_neighbor_count_to_countdown_only 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_info_panel.py::test_update_state_routes_unchanged_neighbor_count_to_countdown_only 
tests/test_command_palette_modal.py::test_modal_renders_key_filter_hint 
tests/artifact_file_facade/test_persistence.py::test_persist_default_artifact_files_captures_when_index_read_fails 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_persistence.py::test_persist_default_artifact_files_captures_when_index_read_fails 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_renders_key_filter_hint 
tests/test_commit_workflow_support.py::test_is_conflict_state_ignores_unconfigured_mock_methods 
[gw2] [ 95%] PASSED tests/test_commit_workflow_support.py::test_is_conflict_state_ignores_unconfigured_mock_methods 
tests/ace/tui/test_wait_modal.py::test_modal_invalid_priority_does_not_dismiss 
tests/ace/tui/models/test_changespec_groups_perf.py::test_by_date_enumerate_parses_each_cs_once 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_changespec_groups_perf.py::test_by_date_enumerate_parses_each_cs_once 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_rewrites_colon_name_directive 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_rewrites_colon_name_directive 
tests/ace/tui/test_agent_completion.py::test_filter_agent_completion_candidates_uses_name_prefix 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_filter_agent_completion_candidates_uses_name_prefix 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_invalid_priority_does_not_dismiss 
tests/test_commit_workflow_support.py::test_is_conflict_state_detects_sync_in_progress 
[gw2] [ 95%] PASSED tests/test_commit_workflow_support.py::test_is_conflict_state_detects_sync_in_progress 
tests/artifact_file_facade/test_persistence.py::test_persist_default_artifact_files_applies_capture_policy_matrix 
tests/test_command_palette_modal.py::test_modal_title_includes_tab_badge 
tests/ace/tui/models/test_changespec_groups_perf.py::test_by_status_build_does_not_parse_timestamps 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_changespec_groups_perf.py::test_by_status_build_does_not_parse_timestamps 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_title_includes_tab_badge 
tests/ace/tui/models/test_agent_panels.py::test_starting_only_tribe_assigned_agents_do_not_create_tribe_panels 
[gw0] [ 95%] PASSED tests/ace/tui/models/test_agent_panels.py::test_starting_only_tribe_assigned_agents_do_not_create_tribe_panels 
tests/ace/tui/test_axe_run_chop.py::test_run_selected_chop_with_lumberjack_row_is_noop 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_run_selected_chop_with_lumberjack_row_is_noop 
[gw9] [ 95%] PASSED tests/test_bead/test_cli_close_resolution.py::test_close_resolution_round_trips_end_to_end 
tests/ace/tui/widgets/test_agent_info_panel.py::test_update_state_full_rebuild_when_neighbor_count_changes 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_info_panel.py::test_update_state_full_rebuild_when_neighbor_count_changes 
tests/ace/tui/test_wait_modal.py::test_modal_marks_cleared_priority_for_update 
tests/test_commit_workflow_support.py::test_is_conflict_state_detects_conflicted_files 
[gw2] [ 95%] PASSED tests/test_commit_workflow_support.py::test_is_conflict_state_detects_conflicted_files 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_rewrites_colon_alias_directive 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_rewrites_colon_alias_directive 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_marks_cleared_priority_for_update 
tests/ace/tui/test_agent_completion.py::test_completion_inserts_bare_local_names_and_searches_raw_alias 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_persistence.py::test_persist_default_artifact_files_applies_capture_policy_matrix 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_completion_inserts_bare_local_names_and_searches_raw_alias 
tests/ace/tui/models/test_changespec_groups_perf.py::test_precompute_cache_is_keyed_by_id_not_value 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_changespec_groups_perf.py::test_precompute_cache_is_keyed_by_id_not_value 
tests/test_command_palette_modal.py::test_modal_filtering_narrows_list 
[gw13] [ 95%] PASSED tests/ace/tui/test_commits_pane_interactions.py::test_commits_pilot_drives_live_filter_bar_detail_copy_and_toggles 
tests/test_bead/test_cli_close_resolution.py::test_force_close_sweeps_unfinished_child_end_to_end 
tests/test_commit_xprompt_append.py::test_append_to_commit_and_propose_found_for_spy_plugin 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_append_to_commit_and_propose_found_for_spy_plugin 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_filtering_narrows_list 
tests/ace/tui/test_wait_modal.py::test_modal_focus_swaps_completion_list_but_time_leaves_it_unchanged 
tests/artifact_file_facade/test_persistence.py::test_persist_default_artifact_files_enforces_store_cap 
tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_schedules_pump_free_task 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_schedules_pump_free_task 
tests/ace/tui/models/test_changespec_groups_perf.py::test_walk_order_uses_supplied_latest_map 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_changespec_groups_perf.py::test_walk_order_uses_supplied_latest_map 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_focus_swaps_completion_list_but_time_leaves_it_unchanged 
tests/ace/tui/widgets/test_agent_info_panel.py::test_update_state_full_rebuild_when_runner_capacity_changes 
tests/test_commit_xprompt_append.py::test_append_to_pr_found_for_spy_plugin 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_append_to_pr_found_for_spy_plugin 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_info_panel.py::test_update_state_full_rebuild_when_runner_capacity_changes 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_rewrites_parenthesized_name_directive 
tests/ace/tui/test_commits_pane_interactions.py::test_commits_refresh_override_drives_action_footer_and_help 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_rewrites_parenthesized_name_directive 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_persistence.py::test_persist_default_artifact_files_enforces_store_cap 
tests/ace/tui/test_agent_completion.py::test_clan_tree_merges_legacy_and_qualified_local_metadata 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_clan_tree_merges_legacy_and_qualified_local_metadata 
tests/test_command_palette_modal.py::test_modal_status_count_switches_to_filtered_form 
tests/ace/tui/models/test_agent_panels.py::test_tribe_assigned_rendered_row_with_starting_row_shows_only_tribe_assigned_panel 
[gw0] [ 95%] PASSED tests/ace/tui/models/test_agent_panels.py::test_tribe_assigned_rendered_row_with_starting_row_shows_only_tribe_assigned_panel 
tests/test_commit_xprompt_append.py::test_append_to_commit_and_propose_found_for_github 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_status_count_switches_to_filtered_form 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_append_to_commit_and_propose_found_for_github 
tests/ace/tui/models/test_diff_badge.py::test_diff_text_has_real_edits_classifies_paths 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_diff_badge.py::test_diff_text_has_real_edits_classifies_paths 
tests/ace/tui/test_wait_modal.py::test_modal_tab_falls_through_to_focus_next_without_highlight 
tests/agents_sync/test_commit_publication.py::test_publication_request_records_the_committing_lane[foo.bar--plan-foo.bar] 
tests/artifact_file_facade/test_reclaim.py::test_clean_pushed_file_reclaims_resolves_and_is_idempotent 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_tab_falls_through_to_focus_next_without_highlight 
tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_success_notifies_and_refreshes 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_success_notifies_and_refreshes 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_rewrites_backtick_name_directive 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_rewrites_backtick_name_directive 
tests/test_commit_xprompt_append.py::test_no_append_when_no_tagged_xprompts 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_no_append_when_no_tagged_xprompts 
tests/ace/tui/widgets/test_agent_info_panel.py::test_render_and_countdown_paths_do_not_read_runner_configuration 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_info_panel.py::test_render_and_countdown_paths_do_not_read_runner_configuration 
tests/test_command_palette_modal.py::test_modal_filtering_resets_highlight_to_top 
tests/ace/tui/test_agent_completion.py::test_build_agent_completion_candidates_derives_ordered_groups 
tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_is_false_for_sdd_only_diff 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_is_false_for_sdd_only_diff 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_build_agent_completion_candidates_derives_ordered_groups 
[gw4] [ 95%] PASSED tests/agents_sync/test_commit_publication.py::test_publication_request_records_the_committing_lane[foo.bar--plan-foo.bar] 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_filtering_resets_highlight_to_top 
tests/test_commit_xprompt_append.py::test_no_append_for_bare_git_append_to_pr 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_no_append_for_bare_git_append_to_pr 
tests/ace/tui/test_wait_modal.py::test_modal_ctrl_j_moves_from_agents_to_beads_input 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_reclaim.py::test_clean_pushed_file_reclaims_resolves_and_is_idempotent 
[gw9] [ 95%] PASSED tests/test_bead/test_cli_close_resolution.py::test_force_close_sweeps_unfinished_child_end_to_end 
tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_is_true_for_mixed_sdd_and_code_diff 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_is_true_for_mixed_sdd_and_code_diff 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_leaves_already_forced_name_directive 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_leaves_already_forced_name_directive 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_ctrl_j_moves_from_agents_to_beads_input 
tests/test_commit_xprompt_append.py::test_commit_method_create_commit_maps_to_append_to_commit_and_propose 
tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_already_running_notifies_warning 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_already_running_notifies_warning 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_commit_method_create_commit_maps_to_append_to_commit_and_propose 
tests/test_command_palette_modal.py::test_modal_empty_state_shown_when_no_match 
tests/ace/tui/models/test_agent_panels.py::test_rendered_no_tribe_row_with_starting_row_shows_no_tribe_panel 
[gw0] [ 95%] PASSED tests/ace/tui/models/test_agent_panels.py::test_rendered_no_tribe_row_with_starting_row_shows_no_tribe_panel 
tests/ace/tui/test_agent_completion.py::test_proc_shell_completion_candidate_uses_exact_proc_id 
tests/ace/tui/widgets/test_agent_info_panel.py::test_update_display_uses_layout_false 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_proc_shell_completion_candidate_uses_exact_proc_id 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_info_panel.py::test_update_display_uses_layout_false 
tests/artifact_file_facade/test_reclaim.py::test_unpushed_content_and_probe_failure_leave_row_untouched 
tests/test_bead/test_cli_dep_list.py::test_dep_parser_supports_bare_list_delegation_and_sorted_options 
[gw9] [ 95%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_parser_supports_bare_list_delegation_and_sorted_options 
tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_is_false_for_sase_plan_only_diff 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_empty_state_shown_when_no_match 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_is_false_for_sase_plan_only_diff 
tests/test_commit_xprompt_append.py::test_commit_method_create_proposal_maps_to_append_to_commit_and_propose 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_commit_method_create_proposal_maps_to_append_to_commit_and_propose 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_reclaim.py::test_unpushed_content_and_probe_failure_leave_row_untouched 
tests/ace/tui/test_wait_modal.py::test_modal_ctrl_j_wraps_from_priority_to_agents_input 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_leaves_template_without_replacement 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_leaves_template_without_replacement 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_ctrl_j_wraps_from_priority_to_agents_input 
tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_is_false_for_rename_only_plan_diff 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_is_false_for_rename_only_plan_diff 
tests/test_commit_xprompt_append.py::test_commit_method_create_pull_request_maps_to_append_to_pr 
tests/test_command_palette_modal.py::test_modal_status_empty_filter_shows_zero_position 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_commit_method_create_pull_request_maps_to_append_to_pr 
tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_compact_shows_both_directions_and_verdicts 
tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_runner_exception_notifies_error_and_refreshes 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_runner_exception_notifies_error_and_refreshes 
tests/ace/tui/test_agent_completion.py::test_proc_shell_is_not_also_offered_as_a_plain_agent_candidate 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_proc_shell_is_not_also_offered_as_a_plain_agent_candidate 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_status_empty_filter_shows_zero_position 
tests/artifact_file_facade/test_reclaim.py::test_history_bound_finds_older_exact_content_only_within_bound 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_update_list_hides_attempt_rows_when_history_present 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_update_list_hides_attempt_rows_when_history_present 
tests/test_commit_xprompt_append.py::test_builtin_commit_workflow_has_environment 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_builtin_commit_workflow_has_environment 
tests/ace/tui/test_wait_modal.py::test_modal_ctrl_k_wraps_from_agents_to_priority_input 
tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_accepts_sase_sdd_variant 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_accepts_sase_sdd_variant 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_replaces_template_with_concrete_name 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_replaces_template_with_concrete_name 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_reclaim.py::test_history_bound_finds_older_exact_content_only_within_bound 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_ctrl_k_wraps_from_agents_to_priority_input 
tests/ace/tui/models/test_agent_panels.py::test_starting_only_tribe_merged_mode_excludes_rows_from_default_panel 
[gw0] [ 95%] PASSED tests/ace/tui/models/test_agent_panels.py::test_starting_only_tribe_merged_mode_excludes_rows_from_default_panel 
tests/test_command_palette_modal.py::test_modal_enter_returns_highlighted_id 
tests/test_commit_xprompt_append.py::test_builtin_propose_workflow_has_environment 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_builtin_propose_workflow_has_environment 
tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_fails_open_for_missing_or_unparsed_diff 
tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_not_found_notifies_error 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_not_found_notifies_error 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_fails_open_for_missing_or_unparsed_diff 
tests/ace/tui/test_agent_completion.py::test_family_completion_candidate_counts_monitor_shell_member 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_family_completion_candidate_counts_monitor_shell_member 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_update_list_no_attempts_keeps_single_agent_row 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_update_list_no_attempts_keeps_single_agent_row 
tests/artifact_file_facade/test_reclaim.py::test_history_walk_is_shared_by_rows_at_the_same_repo_path 
tests/ace/tui/test_wait_modal.py::test_modal_ctrl_k_does_not_delete_focused_input_text 
tests/test_commit_xprompt_append.py::test_builtin_pr_workflow_has_environment 
[gw9] [ 95%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_compact_shows_both_directions_and_verdicts 
[gw2] [ 95%] PASSED tests/test_commit_xprompt_append.py::test_builtin_pr_workflow_has_environment 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_leaves_bare_and_missing_name_directives 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_leaves_bare_and_missing_name_directives 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_reclaim.py::test_history_walk_is_shared_by_rows_at_the_same_repo_path 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_ctrl_k_does_not_delete_focused_input_text 
tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_cache_invalidates_when_file_metadata_changes 
tests/agents_sync/test_commit_publication.py::test_publication_request_records_the_committing_lane[foo.solo-foo.solo] 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_diff_badge.py::test_diff_has_real_edits_cache_invalidates_when_file_metadata_changes 
tests/test_commits_multiline_body.py::TestCommitEntryBody::test_default_body_is_none 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestCommitEntryBody::test_default_body_is_none 
tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_full_adds_provenance 
tests/ace/tui/test_agent_completion.py::test_build_agent_completion_candidates_omits_empty_clan 
tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_ambiguous_error_notifies 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_build_agent_completion_candidates_omits_empty_clan 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_ambiguous_error_notifies 
tests/ace/tui/test_wait_modal.py::test_modal_ctrl_j_from_agent_completion_moves_to_beads_input 
[gw4] [ 95%] PASSED tests/agents_sync/test_commit_publication.py::test_publication_request_records_the_committing_lane[foo.solo-foo.solo] 
tests/artifact_file_facade/test_reclaim.py::test_sidecar_nested_source_maps_to_sidecar_repo 
tests/test_commits_multiline_body.py::TestCommitEntryBody::test_body_with_lines 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestCommitEntryBody::test_body_with_lines 
tests/ace/tui/models/test_agent_panels.py::test_stale_and_missing_start_time_starting_rows_stay_hidden 
[gw0] [ 95%] PASSED tests/ace/tui/models/test_agent_panels.py::test_stale_and_missing_start_time_starting_rows_stay_hidden 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_resolve_row_does_not_return_attempt_numbers_without_child_rows 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_resolve_row_does_not_return_attempt_numbers_without_child_rows 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_ignores_fenced_and_disabled_name_directives 
tests/ace/tui/models/test_done_agent_epic_outcomes.py::test_fs_loader_maps_epic_terminal_outcomes[epic_approved-EPIC APPROVED] 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_done_agent_epic_outcomes.py::test_fs_loader_maps_epic_terminal_outcomes[epic_approved-EPIC APPROVED] 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_force_name_reuse_ignores_fenced_and_disabled_name_directives 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_ctrl_j_from_agent_completion_moves_to_beads_input 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_reclaim.py::test_sidecar_nested_source_maps_to_sidecar_repo 
[gw3] [ 95%] PASSED tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result 
tests/test_commits_multiline_body.py::TestCommitEntryBody::test_body_with_blank_lines 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestCommitEntryBody::test_body_with_blank_lines 
tests/ace/tui/models/test_done_agent_epic_outcomes.py::test_fs_loader_maps_epic_terminal_outcomes[epic_launch_failed-FAILED] 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_done_agent_epic_outcomes.py::test_fs_loader_maps_epic_terminal_outcomes[epic_launch_failed-FAILED] 
tests/ace/tui/test_agent_completion.py::test_status_style_returns_rich_parseable_styles 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion.py::test_status_style_returns_rich_parseable_styles 
tests/artifact_file_facade/test_reclaim.py::test_explicit_consumed_missing_checkout_and_unknown_repo_are_unresolved 
tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_not_found_via_find_notifies 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_not_found_via_find_notifies 
tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_cycles_ranked_projects_and_survives_range_change 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_reclaim.py::test_explicit_consumed_missing_checkout_and_unknown_repo_are_unresolved 
tests/test_commits_multiline_body.py::TestBuildCommitEntryWithBody::test_body_passed_through 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestBuildCommitEntryWithBody::test_body_passed_through 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%i:foo\nDo work-foo-%id:!foo\nDo work] 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%i:foo\nDo work-foo-%id:!foo\nDo work] 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_attempt_option_text_shows_number_and_snippet 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_attempt_option_text_shows_number_and_snippet 
tests/ace/tui/models/test_done_agent_image_files.py::test_done_loader_adds_image_paths_to_extra_files 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_done_agent_image_files.py::test_done_loader_adds_image_paths_to_extra_files 
tests/test_commits_multiline_body.py::TestBuildCommitEntryWithBody::test_none_body 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestBuildCommitEntryWithBody::test_none_body 
tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_aggregates_all_panel_widgets 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_aggregates_all_panel_widgets 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_enter_returns_highlighted_id 
tests/artifact_file_facade/test_reclaim.py::test_missing_checkout_and_unknown_project_fail_safe 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_reclaim.py::test_missing_checkout_and_unknown_project_fail_safe 
tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_passes_chop_timeout_default 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_launch_chop_run_async_passes_chop_timeout_default 
tests/test_commits_multiline_body.py::TestBuildCommitEntryWithBody::test_empty_list_body_treated_as_none 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestBuildCommitEntryWithBody::test_empty_list_body_treated_as_none 
tests/ace/tui/models/test_done_agent_image_files.py::test_snapshot_done_loader_adds_image_paths_to_extra_files 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id:foo\nDo work-foo-%id:!foo\nDo work] 
tests/ace/tui/models/test_agent_panels.py::test_workflow_child_inherits_parent_tribe_without_empty_no_tribe_panel 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_done_agent_image_files.py::test_snapshot_done_loader_adds_image_paths_to_extra_files 
[gw0] [ 95%] PASSED tests/ace/tui/models/test_agent_panels.py::test_workflow_child_inherits_parent_tribe_without_empty_no_tribe_panel 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id:foo\nDo work-foo-%id:!foo\nDo work] 
[gw9] [ 95%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_full_adds_provenance 
tests/test_command_palette_modal.py::test_modal_enter_after_filter_returns_filtered_top 
tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_falls_back_when_no_widgets 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_falls_back_when_no_widgets 
tests/artifact_file_facade/test_retention.py::test_retention_constructs_policy_and_projects_plan 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_attempt_option_id_is_stable 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_attempt_option_id_is_stable 
[gw13] [ 95%] PASSED tests/ace/tui/test_commits_pane_interactions.py::test_commits_refresh_override_drives_action_footer_and_help 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_retention.py::test_retention_constructs_policy_and_projects_plan 
tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_multiline_note 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_multiline_note 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_enter_after_filter_returns_filtered_top 
tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_fs_loader_maps_repeat_stopped_marker_to_stopped 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_fs_loader_maps_repeat_stopped_marker_to_stopped 
tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_json_uses_shared_resolved_reference_shape 
tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_uses_visible_order_fallback 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_uses_visible_order_fallback 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id:@.cld\nDo work-0.cld-%id:!0.cld\nDo work] 
tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_blank_line_marker 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id:@.cld\nDo work-0.cld-%id:!0.cld\nDo work] 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_blank_line_marker 
tests/ace/tui/test_commits_pane_interactions.py::test_commit_fetch_task_uses_visible_project_name_and_matching_file 
tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_chop_selected_idle_shows_run_chop 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_chop_selected_idle_shows_run_chop 
tests/artifact_file_facade/test_retention.py::test_retention_policy_wire_is_built_only_in_bridge 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_retention.py::test_retention_policy_wire_is_built_only_in_bridge 
tests/test_command_palette_modal.py::test_modal_escape_returns_none 
tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_fs_loader_completed_without_repeat_stopped_is_done 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_fs_loader_completed_without_repeat_stopped_is_done 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_attempt_option_text_includes_duration_tail 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_attempt_option_text_includes_duration_tail 
tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_no_body 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_no_body 
tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_escape_returns_none 
tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_adds_collapsed_clan_lanes 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_adds_collapsed_clan_lanes 
tests/artifact_file_facade/test_retention.py::test_retention_names_an_incompatible_binding_field 
tests/ace/tui/models/test_agent_panels.py::test_missing_focused_key_falls_back_to_first_available_panel 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_retention.py::test_retention_names_an_incompatible_binding_field 
[gw0] [ 95%] PASSED tests/ace/tui/models/test_agent_panels.py::test_missing_focused_key_falls_back_to_first_available_panel 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id:!foo\nDo work-foo-%id:!foo\nDo work] 
tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_fs_loader_maps_stopped_outcome_to_stopped 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_fs_loader_maps_stopped_outcome_to_stopped 
[gw6] [ 95%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id:!foo\nDo work-foo-%id:!foo\nDo work] 
tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_body_with_drawers 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_body_with_drawers 
tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_chop_selected_running_shows_running 
[gw1] [ 95%] PASSED tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_chop_selected_running_shows_running 
tests/test_command_palette_modal.py::test_modal_enter_with_no_results_is_noop 
tests/artifact_file_facade/test_storage.py::test_explicit_plan_duplicate_does_not_add_second_plan_row 
[gw4] [ 95%] PASSED tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued 
[gw7] [ 95%] PASSED tests/artifact_file_facade/test_storage.py::test_explicit_plan_duplicate_does_not_add_second_plan_row 
tests/ace/tui/test_wait_modal.py::test_modal_field_navigation_places_cursor_at_end 
tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_multiple_entries_with_body 
[gw2] [ 95%] PASSED tests/test_commits_multiline_body.py::TestParseCommitsLineBody::test_parse_multiple_entries_with_body 
tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_snapshot_loader_maps_repeat_stopped_marker_to_stopped 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_fold_annotation_adds_attempts_count 
[gw8] [ 95%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_fold_annotation_adds_attempts_count 
[gw12] [ 95%] PASSED tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_snapshot_loader_maps_repeat_stopped_marker_to_stopped 
[gw11] [ 95%] PASSED tests/test_command_palette_modal.py::test_modal_enter_with_no_results_is_noop 
[gw10] [ 95%] PASSED tests/ace/tui/test_wait_modal.py::test_modal_field_navigation_places_cursor_at_end 
tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_deduplicates_expanded_clan 
[gw5] [ 95%] PASSED tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_deduplicates_expanded_clan 
tests/test_commits_multiline_body.py::TestRenumberParseBody::test_parse_body_lines 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id:sase-8a.3\n%auto\nDo work-sase-8a.3--plan-%id:!sase-8a.3\n%auto\nDo work] 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRenumberParseBody::test_parse_body_lines 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id:sase-8a.3\n%auto\nDo work-sase-8a.3--plan-%id:!sase-8a.3\n%auto\nDo work] 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_interactions.py::test_commit_fetch_task_uses_visible_project_name_and_matching_file 
tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_no_chop_no_r_binding 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_no_chop_no_r_binding 
tests/test_commits_multiline_body.py::TestRenumberParseBody::test_parse_blank_marker 
tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_snapshot_loader_maps_stopped_outcome_to_stopped 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRenumberParseBody::test_parse_blank_marker 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_done_agent_repeat_stopped.py::test_snapshot_loader_maps_stopped_outcome_to_stopped 
tests/test_command_palette_modal.py::test_modal_down_arrow_moves_highlight 
tests/artifact_file_facade/test_storage.py::test_single_explicit_plan_is_kept_without_metadata_plan 
tests/ace/tui/test_wait_modal_beads.py::test_modal_beads_field_is_editable_and_round_trips_prefill 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_storage.py::test_single_explicit_plan_is_kept_without_metadata_plan 
tests/ace/tui/models/test_agent_panels.py::test_merged_panels_use_one_panel_but_preserve_effective_tribes 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_panels.py::test_merged_panels_use_one_panel_but_preserve_effective_tribes 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_json_uses_shared_resolved_reference_shape 
tests/test_commits_multiline_body.py::TestRenumberParseBody::test_parse_no_body 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRenumberParseBody::test_parse_no_body 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_beads_field_is_editable_and_round_trips_prefill 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id(2, clan=sase-8k, bead=sase-8k.2)\nDo work-sase-8k.2-%id(!2, clan=sase-8k, bead=sase-8k.2)\nDo work] 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_fold_annotation_empty_when_no_attempts_and_no_workflow 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id(2, clan=sase-8k, bead=sase-8k.2)\nDo work-sase-8k.2-%id(!2, clan=sase-8k, bead=sase-8k.2)\nDo work] 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_fold_annotation_empty_when_no_attempts_and_no_workflow 
tests/ace/tui/test_commits_pane_interactions.py::test_commits_cycle_merges_updates_query_and_recollects 
tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_preserves_non_clan_visibility 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_completion_visibility.py::test_visible_agent_completion_agents_preserves_non_clan_visibility 
[gw11] [ 96%] PASSED tests/test_command_palette_modal.py::test_modal_down_arrow_moves_highlight 
tests/ace/tui/models/test_done_agent_reverted.py::test_agent_is_reverted_detects_revert_result_marker 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_done_agent_reverted.py::test_agent_is_reverted_detects_revert_result_marker 
tests/test_commits_multiline_body.py::TestRenumberParseBody::test_parse_body_with_raw_lines 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRenumberParseBody::test_parse_body_with_raw_lines 
tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_direction_filters_sections[out-DEPENDS ON-BLOCKS (] 
tests/test_commits_multiline_body.py::TestRenumberBuildBody::test_build_with_body 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRenumberBuildBody::test_build_with_body 
tests/artifact_file_facade/test_storage.py::test_store_explicit_artifact_creates_index_and_dedupes_display_order 
tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_tracks_description_state 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_tracks_description_state 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_storage.py::test_store_explicit_artifact_creates_index_and_dedupes_display_order 
tests/ace/tui/test_wait_modal_beads.py::test_modal_run_now_cancels_bead_waits 
tests/test_command_palette_modal.py::test_modal_position_updates_after_navigation 
tests/ace/tui/models/test_done_agent_reverted.py::test_fs_done_loader_sets_reverted_from_marker 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_done_agent_reverted.py::test_fs_done_loader_sets_reverted_from_marker 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id(2, clan=sase-8k, bead=sase-8k.2)\nDo work-sase-8k.2--plan-%id(!2, clan=sase-8k, bead=sase-8k.2)\nDo work] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[%id(2, clan=sase-8k, bead=sase-8k.2)\nDo work-sase-8k.2--plan-%id(!2, clan=sase-8k, bead=sase-8k.2)\nDo work] 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_run_now_cancels_bead_waits 
tests/test_commits_multiline_body.py::TestRenumberBuildBody::test_build_with_blank_marker 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRenumberBuildBody::test_build_with_blank_marker 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_fold_annotation_keeps_parallel_family_counts_out_of_structure 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_fold_annotation_keeps_parallel_family_counts_out_of_structure 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_projection_dedupes_workflow_descendants_in_first_seen_sase_agent_order 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_projection_dedupes_workflow_descendants_in_first_seen_sase_agent_order 
[gw11] [ 96%] PASSED tests/test_command_palette_modal.py::test_modal_position_updates_after_navigation 
tests/ace/tui/models/test_done_agent_reverted.py::test_fs_done_loader_defaults_reverted_false_without_marker 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_done_agent_reverted.py::test_fs_done_loader_defaults_reverted_false_without_marker 
tests/artifact_file_facade/test_storage.py::test_read_artifact_file_index_reuses_parse_until_stat_changes 
tests/ace/tui/models/test_agent_panels.py::test_clan_subtree_uses_outer_root_panel_in_split_and_merged_modes 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_panels.py::test_clan_subtree_uses_outer_root_panel_in_split_and_merged_modes 
tests/test_commits_multiline_body.py::TestRenumberBuildBody::test_build_body_before_drawers 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRenumberBuildBody::test_build_body_before_drawers 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_storage.py::test_read_artifact_file_index_reuses_parse_until_stat_changes 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[#gh:gh_sase-org__sase Describe this repo.-068-#gh:gh_sase-org__sase Describe this repo.] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[#gh:gh_sase-org__sase Describe this repo.-068-#gh:gh_sase-org__sase Describe this repo.] 
tests/ace/tui/test_wait_modal_beads.py::test_modal_beads_field_parses_order_preserving_deduplicated_ids 
tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_done_bgcmd_wins_over_chop_label 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_run_chop.py::test_compute_axe_bindings_done_bgcmd_wins_over_chop_label 
tests/test_command_palette_modal.py::test_modal_ctrl_n_ctrl_p_navigate 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_beads_field_parses_order_preserving_deduplicated_ids 
tests/ace/tui/models/test_done_agent_reverted.py::test_snapshot_done_loader_sets_reverted_from_record_artifact_dir 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_done_agent_reverted.py::test_snapshot_done_loader_sets_reverted_from_record_artifact_dir 
tests/test_commits_multiline_body.py::TestRenumberBuildBody::test_build_no_body 
[gw3] [ 96%] PASSED tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_cycles_ranked_projects_and_survives_range_change 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRenumberBuildBody::test_build_no_body 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_highlight_selects_agent_row_when_attempt_number_passed 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_sequential_family_uses_presented_sase_agent_and_exact_running_member 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_sequential_family_uses_presented_sase_agent_and_exact_running_member 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_highlight_selects_agent_row_when_attempt_number_passed 
tests/artifact_file_facade/test_storage.py::test_read_artifact_file_index_returns_defensive_list 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_storage.py::test_read_artifact_file_index_returns_defensive_list 
tests/agents_sync/test_commit_publication_bounded_drain.py::test_after_a_blocked_render_a_later_drain_retries_and_succeeds 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[Do work-None-Do work] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_contract[Do work-None-Do work] 
[gw11] [ 96%] PASSED tests/test_command_palette_modal.py::test_modal_ctrl_n_ctrl_p_navigate 
tests/ace/tui/test_wait_modal_beads.py::test_modal_clearing_beads_keeps_agents_wait 
tests/ace/tui/models/test_fold_scale.py::test_effective_fold_level_clamps_to_kind_scale[FoldLevel.COLLAPSED-scale0-FoldLevel.EXPANDED] 
tests/test_commits_multiline_body.py::TestRoundTrip::test_round_trip_with_body 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_effective_fold_level_clamps_to_kind_scale[FoldLevel.COLLAPSED-scale0-FoldLevel.EXPANDED] 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_direction_filters_sections[out-DEPENDS ON-BLOCKS (] 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRoundTrip::test_round_trip_with_body 
tests/ace/tui/test_statistics_pane_filters.py::test_empty_project_filter_clears_to_all_projects_in_either_direction[p-sase-SASE] 
tests/ace/tui/test_axe_selection_identity.py::test_rebuild_preserves_selected_bgcmd_slot_when_lumberjack_inserted 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_rebuild_preserves_selected_bgcmd_slot_when_lumberjack_inserted 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_clearing_beads_keeps_agents_wait 
tests/artifact_file_facade/test_storage.py::test_artifact_file_index_write_invalidates_cache_when_stat_is_unchanged 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_interactions.py::test_commits_cycle_merges_updates_query_and_recollects 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_storage.py::test_artifact_file_index_write_invalidates_cache_when_stat_is_unchanged 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_completed_family_members_never_leak_into_dismiss_entries 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_completed_family_members_never_leak_into_dismiss_entries 
tests/test_command_palette_modal.py::test_modal_typing_q_does_not_cancel 
tests/test_commits_multiline_body.py::TestRoundTrip::test_round_trip_blank_markers 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestRoundTrip::test_round_trip_blank_markers 
tests/ace/tui/models/test_fold_scale.py::test_effective_fold_level_clamps_to_kind_scale[FoldLevel.EXHAUSTIVE-scale1-FoldLevel.FULLY_EXPANDED] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_effective_fold_level_clamps_to_kind_scale[FoldLevel.EXHAUSTIVE-scale1-FoldLevel.FULLY_EXPANDED] 
tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_direction_filters_sections[in-BLOCKS (-DEPENDS ON] 
[gw4] [ 96%] PASSED tests/agents_sync/test_commit_publication_bounded_drain.py::test_after_a_blocked_render_a_later_drain_retries_and_succeeds 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_update_highlight_falls_back_to_agent_row_for_stale_attempt_pin 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_family_root_keeps_clan 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_update_highlight_falls_back_to_agent_row_for_stale_attempt_pin 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_family_root_keeps_clan 
[gw11] [ 96%] PASSED tests/test_command_palette_modal.py::test_modal_typing_q_does_not_cancel 
tests/ace/tui/test_wait_modal_beads.py::test_modal_clearing_every_field_returns_run_now 
tests/ace/tui/test_commits_pane_rendering.py::test_commits_renderer_builds_compact_single_line_rows 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commits_renderer_builds_compact_single_line_rows 
tests/artifact_file_facade/test_storage.py::test_store_explicit_artifact_file_preserves_jsonl_wire_format 
tests/test_commits_multiline_body.py::TestFindCommitsSectionWithBody::test_body_lines_included_in_section 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestFindCommitsSectionWithBody::test_body_lines_included_in_section 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_storage.py::test_store_explicit_artifact_file_preserves_jsonl_wire_format 
tests/ace/tui/models/test_fold_scale.py::test_effective_fold_level_clamps_to_kind_scale[FoldLevel.EXHAUSTIVE-scale2-FoldLevel.FULLY_EXPANDED] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_effective_fold_level_clamps_to_kind_scale[FoldLevel.EXHAUSTIVE-scale2-FoldLevel.FULLY_EXPANDED] 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_rename_on_attach_family_root_uses_bare_family_sase_agent 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_rename_on_attach_family_root_uses_bare_family_sase_agent 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_clearing_every_field_returns_run_now 
tests/ace/tui/test_axe_selection_identity.py::test_saved_axe_tab_selection_restores_by_bgcmd_slot_key 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_saved_axe_tab_selection_restores_by_bgcmd_slot_key 
tests/ace/tui/models/test_agent_panels.py::test_new_clan_tribe_keeps_entire_subtree_in_one_panel 
tests/test_command_palette_wiring.py::test_colon_opens_command_palette_modal 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_panels.py::test_new_clan_tribe_keeps_entire_subtree_in_one_panel 
tests/test_commits_multiline_body.py::TestTruncateNote::test_no_truncation_needed 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestTruncateNote::test_no_truncation_needed 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_epic_root_without_flag_still_keeps_clan 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_epic_root_without_flag_still_keeps_clan 
tests/ace/tui/models/test_fold_scale.py::test_effective_fold_level_clamps_to_kind_scale[FoldLevel.EXHAUSTIVE-scale3-FoldLevel.EXHAUSTIVE] 
tests/ace/tui/test_commits_pane_rendering.py::test_commits_info_legend_only_lists_repositories_with_displayed_rows 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_effective_fold_level_clamps_to_kind_scale[FoldLevel.EXHAUSTIVE-scale3-FoldLevel.EXHAUSTIVE] 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commits_info_legend_only_lists_repositories_with_displayed_rows 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_highlight_selects_agent_row_when_attempt_number_is_none 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_highlight_selects_agent_row_when_attempt_number_is_none 
tests/artifact_file_facade/test_storage.py::test_explicit_artifact_association_survives_removed_and_restored_run_dir 
tests/ace/tui/test_wait_modal_beads.py::test_modal_bead_completion_filters_by_id_and_title_then_tab_inserts 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_plan_workflow_steps_resolve_to_family_sase_agent 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_plan_workflow_steps_resolve_to_family_sase_agent 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_storage.py::test_explicit_artifact_association_survives_removed_and_restored_run_dir 
tests/test_commits_multiline_body.py::TestTruncateNote::test_exact_fit 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestTruncateNote::test_exact_fit 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_bead_completion_filters_by_id_and_title_then_tab_inserts 
tests/ace/tui/test_axe_selection_identity.py::test_rebuild_preserves_selected_lumberjack_name_when_lumberjack_inserted 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_rebuild_preserves_selected_lumberjack_name_when_lumberjack_inserted 
tests/ace/tui/models/test_fold_scale.py::test_family_scale_cycles_and_positions_relative_to_two_levels 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_family_scale_cycles_and_positions_relative_to_two_levels 
tests/ace/tui/test_commits_pane_rendering.py::test_commits_info_only_renders_active_cap_when_supplied 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commits_info_only_renders_active_cap_when_supplied 
tests/test_commits_multiline_body.py::TestTruncateNote::test_truncated 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestTruncateNote::test_truncated 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_clan_descendants_resolve_to_direct_member_sase_agents_not_clan 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_clan_descendants_resolve_to_direct_member_sase_agents_not_clan 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_plain_family_root_keeps_prompt 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_plain_family_root_keeps_prompt 
tests/artifact_file_facade/test_storage.py::test_store_default_artifact_file_writes_index_row_with_source_path 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_storage.py::test_store_default_artifact_file_writes_index_row_with_source_path 
tests/ace/tui/widgets/test_agent_list_attempts.py::test_update_list_skips_attempt_rows_for_workflow_children 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_attempts.py::test_update_list_skips_attempt_rows_for_workflow_children 
tests/ace/tui/models/test_fold_scale.py::test_tribe_scale_cycles_all_four_levels_in_both_directions 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_tribe_scale_cycles_all_four_levels_in_both_directions 
tests/test_commits_multiline_body.py::TestTruncateNote::test_zero_available 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestTruncateNote::test_zero_available 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_is_one_based_styled_and_precedes_repository 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_is_one_based_styled_and_precedes_repository 
tests/ace/tui/test_wait_modal_beads.py::test_modal_risky_wait_guard_requires_second_enter 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_missing_parent_uses_concrete_legacy_row_as_defensive_fallback 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_missing_parent_uses_concrete_legacy_row_as_defensive_fallback 
tests/ace/tui/test_axe_selection_identity.py::test_rebuild_falls_back_when_selected_item_disappears 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_rebuild_falls_back_when_selected_item_disappears 
tests/test_commits_multiline_body.py::TestTruncateNote::test_one_available 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestTruncateNote::test_one_available 
tests/artifact_file_facade/test_storage.py::test_store_default_artifact_file_returns_none_for_missing_source 
tests/ace/tui/models/test_agent_panels.py::test_nested_monitor_inherits_clan_anchor_panel 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_storage.py::test_store_default_artifact_file_returns_none_for_missing_source 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_panels.py::test_nested_monitor_inherits_clan_anchor_panel 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_prompt_without_identity 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_prompt_without_identity 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale0-FoldLevel.COLLAPSED-FoldLevel.FULLY_EXPANDED] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale0-FoldLevel.COLLAPSED-FoldLevel.FULLY_EXPANDED] 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_risky_wait_guard_requires_second_enter 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[pre-load] 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[pre-load] 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_direction_filters_sections[in-BLOCKS (-DEPENDS ON] 
tests/test_commits_multiline_body.py::TestBodyFolding::test_body_hidden_when_collapsed 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestBodyFolding::test_body_hidden_when_collapsed 
[gw3] [ 96%] PASSED tests/ace/tui/test_statistics_pane_filters.py::test_empty_project_filter_clears_to_all_projects_in_either_direction[p-sase-SASE] 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_counts_family_sase_agent_and_unique_concrete_agents 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_counts_family_sase_agent_and_unique_concrete_agents 
[gw11] [ 96%] PASSED tests/test_command_palette_wiring.py::test_colon_opens_command_palette_modal 
tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_format_banner_option_renders_all_mark_indicator 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_format_banner_option_renders_all_mark_indicator 
tests/artifact_file_facade/test_synthesis.py::test_synthesize_default_artifact_files_from_done_and_agent_meta 
tests/test_commits_multiline_body.py::TestBodyFolding::test_body_shown_when_expanded 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_synthesize_default_artifact_files_from_done_and_agent_meta 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestBodyFolding::test_body_shown_when_expanded 
tests/agents_sync/test_commit_publication_queue.py::test_committed_publication_records_a_retryable_request_when_git_fails 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale1-FoldLevel.EXPANDED-FoldLevel.FULLY_EXPANDED] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale1-FoldLevel.EXPANDED-FoldLevel.FULLY_EXPANDED] 
tests/ace/tui/test_wait_modal_beads.py::test_modal_editing_beads_disarms_risky_wait_guard 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[empty] 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[empty] 
tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_explicit_status_filters_endpoints 
tests/ace/tui/test_axe_selection_identity.py::test_off_tab_rebuild_does_not_mutate_current_idx 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_off_tab_rebuild_does_not_mutate_current_idx 
tests/ace/tui/test_statistics_pane_filters.py::test_empty_project_filter_clears_to_all_projects_in_either_direction[P-core-Core] 
tests/test_commits_multiline_body.py::TestBodyFolding::test_body_shown_when_fully_expanded 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_refuses_self_attaching_family 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestBodyFolding::test_body_shown_when_fully_expanded 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_refuses_self_attaching_family 
[gw4] [ 96%] PASSED tests/agents_sync/test_commit_publication_queue.py::test_committed_publication_records_a_retryable_request_when_git_fails 
tests/test_command_palette_wiring.py::test_semicolon_opens_command_palette_modal 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_editing_beads_disarms_risky_wait_guard 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_counts_workflow_with_hidden_steps_as_one_sase_agent 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_counts_workflow_with_hidden_steps_as_one_sase_agent 
tests/artifact_file_facade/test_synthesis.py::test_artifact_association_from_dir_parses_sharded_agent_dir 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_artifact_association_from_dir_parses_sharded_agent_dir 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale2-FoldLevel.FULLY_EXPANDED-FoldLevel.EXPANDED] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale2-FoldLevel.FULLY_EXPANDED-FoldLevel.EXPANDED] 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[no-selection] 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[no-selection] 
tests/test_commits_multiline_body.py::TestBodyFolding::test_no_body_no_indicator 
[gw2] [ 96%] PASSED tests/test_commits_multiline_body.py::TestBodyFolding::test_no_body_no_indicator 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_restarts_exact_family_member[%id:sase-8u.4.2\n%auto\nDo work-kwargs0-%id(!code, family=sase-8u.4.2)\n%auto\nDo work] 
tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_format_banner_option_renders_partial_mark_indicator 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_format_banner_option_renders_partial_mark_indicator 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_restarts_exact_family_member[%id:sase-8u.4.2\n%auto\nDo work-kwargs0-%id(!code, family=sase-8u.4.2)\n%auto\nDo work] 
tests/ace/tui/test_wait_modal_beads.py::test_modal_unavailable_bead_store_reports_neutral_and_never_arms_guard 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_omits_agent_detail_for_standalone_sase_agents 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_omits_agent_detail_for_standalone_sase_agents 
tests/artifact_file_facade/test_synthesis.py::test_committed_sdd_plan_is_single_default_plan_artifact 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale3-FoldLevel.EXHAUSTIVE-FoldLevel.EXPANDED] 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_committed_sdd_plan_is_single_default_plan_artifact 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale3-FoldLevel.EXHAUSTIVE-FoldLevel.EXPANDED] 
tests/test_bead/test_cli_id_shorthand.py::test_update_accepts_multiple_shorthand_ids_in_one_batch 
tests/ace/tui/test_axe_selection_identity.py::test_chop_item_identity_key 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_chop_item_identity_key 
tests/ace/tui/models/test_agent_panels.py::test_panel_focus_next_skips_multiple_panels_and_wraps 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_panels.py::test_panel_focus_next_skips_multiple_panels_and_wraps 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[provider-cap] 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_unavailable_bead_store_reports_neutral_and_never_arms_guard 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[provider-cap] 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_restarts_exact_family_member[Do work-kwargs1-%id(!code, family=sase-8u.4.2, bead=sase-8u.4.2)\nDo work] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_restarts_exact_family_member[Do work-kwargs1-%id(!code, family=sase-8u.4.2, bead=sase-8u.4.2)\nDo work] 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale4-FoldLevel.COLLAPSED-FoldLevel.FULLY_EXPANDED] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale4-FoldLevel.COLLAPSED-FoldLevel.FULLY_EXPANDED] 
tests/artifact_file_facade/test_synthesis.py::test_plan_committed_requires_a_literal_boolean 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_plan_committed_requires_a_literal_boolean 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_subject_lines_use_singular_sase_agent_and_agent_units 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_subject_lines_use_singular_sase_agent_and_agent_units 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[aggregate-cap] 
tests/ace/tui/test_wait_modal_beads.py::test_modal_own_bead_excluded_from_candidates_and_errors_when_typed 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_truthful_states[aggregate-cap] 
tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_banner_render_key_varies_by_mark_state 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_banner_render_key_varies_by_mark_state 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_own_bead_excluded_from_candidates_and_errors_when_typed 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_restarts_exact_family_member[%id(worker, clan=research, bead=kept)\nDo work-kwargs2-%id(!reviewer, family=research.worker, bead=kept)\nDo work] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_restarts_exact_family_member[%id(worker, clan=research, bead=kept)\nDo work-kwargs2-%id(!reviewer, family=research.worker, bead=kept)\nDo work] 
tests/ace/tui/test_axe_selection_identity.py::test_switch_to_axe_view_moves_highlight_to_matching_row 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_switch_to_axe_view_moves_highlight_to_matching_row 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale5-FoldLevel.EXPANDED-FoldLevel.FULLY_EXPANDED] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale5-FoldLevel.EXPANDED-FoldLevel.FULLY_EXPANDED] 
tests/artifact_file_facade/test_synthesis.py::test_agent_meta_chat_path_is_used_when_done_response_is_missing 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_agent_meta_chat_path_is_used_when_done_response_is_missing 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_handles_referenced_large_timeline 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_position_badge_handles_referenced_large_timeline 
tests/ace/tui/test_wait_modal_beads.py::test_modal_enter_on_focused_bead_completion_list_accepts_highlighted 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_restarts_exact_family_member[%clan(research, tribe=review)\n%id:research.worker\nDo work-kwargs3-%id(!commit, family=research.worker)\nDo work] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_restarts_exact_family_member[%clan(research, tribe=review)\n%id:research.worker\nDo work-kwargs3-%id(!commit, family=research.worker)\nDo work] 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_deduplicates_repeated_concrete_identity 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_deduplicates_repeated_concrete_identity 
tests/ace/tui/models/test_agent_panels.py::test_panel_focus_prev_skips_multiple_panels_and_wraps 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_panels.py::test_panel_focus_prev_skips_multiple_panels_and_wraps 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_id_shorthand.py::test_update_accepts_multiple_shorthand_ids_in_one_batch 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale6-FoldLevel.FULLY_EXPANDED-FoldLevel.COLLAPSED] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale6-FoldLevel.FULLY_EXPANDED-FoldLevel.COLLAPSED] 
[gw11] [ 96%] PASSED tests/test_command_palette_wiring.py::test_semicolon_opens_command_palette_modal 
[gw10] [ 96%] PASSED tests/ace/tui/test_wait_modal_beads.py::test_modal_enter_on_focused_bead_completion_list_accepts_highlighted 
tests/artifact_file_facade/test_synthesis.py::test_generated_markdown_pdf_artifact_keeps_pdf_path_and_uses_source_metadata 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_explicit_status_filters_endpoints 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_generated_markdown_pdf_artifact_keeps_pdf_path_and_uses_source_metadata 
tests/ace/tui/test_commits_pane_rendering.py::test_empty_commits_info_has_one_separator_before_presence_legend 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_empty_commits_info_has_one_separator_before_presence_legend 
tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_update_list_marks_collapsed_banner_all 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_update_list_marks_collapsed_banner_all 
tests/test_bead/test_cli_id_shorthand.py::test_dependency_and_reference_commands_accept_shorthand 
tests/ace/tui/test_axe_selection_identity.py::test_pending_write_selection_expands_parent_and_selects_target 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_pending_write_selection_expands_parent_and_selects_target 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_bare_id[foo] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_bare_id[foo] 
tests/test_command_palette_wiring.py::test_palette_escape_dismisses_without_side_effects 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale7-FoldLevel.EXHAUSTIVE-FoldLevel.COLLAPSED] 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_empty_summary_emits_no_subject_lines 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale7-FoldLevel.EXHAUSTIVE-FoldLevel.COLLAPSED] 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_empty_summary_emits_no_subject_lines 
tests/artifact_file_facade/test_synthesis.py::test_prompt_absolute_image_path_is_default_image_artifact 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_prompt_absolute_image_path_is_default_image_artifact 
tests/ace/tui/test_xprompt_browser_filter.py::test_xprompts_open_browse_first_with_hidden_filter 
tests/test_bead/test_cli_dep_list.py::test_dep_list_store_wide_compact_groups_and_prints_census 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_preserves_full_metadata_for_every_presence[local_only-\u2191 unpushed] 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_preserves_full_metadata_for_every_presence[local_only-\u2191 unpushed] 
tests/agents_sync/test_commit_publication_queue.py::test_failed_targeted_publish_cleans_uncommitted_payload 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_bare_id[None] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_bare_id[None] 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale8-FoldLevel.COLLAPSED-FoldLevel.EXHAUSTIVE] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale8-FoldLevel.COLLAPSED-FoldLevel.EXHAUSTIVE] 
tests/artifact_file_facade/test_synthesis.py::test_prompt_referenced_gif_is_default_image_artifact 
tests/ace/tui/test_axe_selection_identity.py::test_pending_write_selection_is_dropped_after_newer_navigation 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_prompt_referenced_gif_is_default_image_artifact 
tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_update_list_marks_collapsed_banner_partial 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_pending_write_selection_is_dropped_after_newer_navigation 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_banner_marks.py::test_update_list_marks_collapsed_banner_partial 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_preserves_full_metadata_for_every_presence[remote_only-\u2193 GitHub-only] 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_preserves_full_metadata_for_every_presence[remote_only-\u2193 GitHub-only] 
[gw4] [ 96%] PASSED tests/agents_sync/test_commit_publication_queue.py::test_failed_targeted_publish_cleans_uncommitted_payload 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_headline_sase_agent_count_equals_roster_length 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_summary_headline_sase_agent_count_equals_roster_length 
tests/ace/tui/models/test_agent_panels.py::test_panel_focus_step_can_start_from_skipped_panel 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_panels.py::test_panel_focus_step_can_start_from_skipped_panel 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_06y_unnamed_prompt[06y] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_06y_unnamed_prompt[06y] 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale9-FoldLevel.EXPANDED-FoldLevel.EXHAUSTIVE] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale9-FoldLevel.EXPANDED-FoldLevel.EXHAUSTIVE] 
tests/artifact_file_facade/test_synthesis.py::test_prompt_workspace_relative_image_path_uses_workspace_dir 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_prompt_workspace_relative_image_path_uses_workspace_dir 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_preserves_full_metadata_for_every_presence[synced-\u25cf synced] 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_preserves_full_metadata_for_every_presence[synced-\u25cf synced] 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_id_shorthand.py::test_dependency_and_reference_commands_accept_shorthand 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_06y_unnamed_prompt[bbugyi200.athena.06y] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_06y_unnamed_prompt[bbugyi200.athena.06y] 
tests/ace/tui/test_axe_selection_identity.py::test_pending_write_selection_is_dropped_off_tab 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_selection_identity.py::test_pending_write_selection_is_dropped_off_tab 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::test_missing_cache_entries_back_off_longer_than_confirmed_hits 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::test_missing_cache_entries_back_off_longer_than_confirmed_hits 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale10-FoldLevel.FULLY_EXPANDED-FoldLevel.EXHAUSTIVE] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale10-FoldLevel.FULLY_EXPANDED-FoldLevel.EXHAUSTIVE] 
tests/ace/tui/test_agent_confirmation_sase_agents.py::test_bulk_subject_can_show_same_family_sase_agent_in_kill_and_dismiss_sections 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_confirmation_sase_agents.py::test_bulk_subject_can_show_same_family_sase_agent_in_kill_and_dismiss_sections 
tests/artifact_file_facade/test_synthesis.py::test_prompt_workspace_relative_video_path_is_default_file_artifact 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_prompt_workspace_relative_video_path_is_default_file_artifact 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_preserves_full_metadata_for_every_presence[unknown-\xb7 unknown] 
tests/test_bead/test_cli_id_shorthand.py::test_work_task_dry_run_uses_canonical_id_for_shorthand 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_preserves_full_metadata_for_every_presence[unknown-\xb7 unknown] 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_store_wide_compact_groups_and_prints_census 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_06y_unnamed_prompt[None] 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_06y_unnamed_prompt[None] 
tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale11-FoldLevel.EXHAUSTIVE-FoldLevel.COLLAPSED] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_toggle_fold_scale_extreme_uses_effective_active_scale_level[scale11-FoldLevel.EXHAUSTIVE-FoldLevel.COLLAPSED] 
tests/ace/tui/test_agent_content_search_cache.py::test_haystack_includes_prompt_and_reply 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_haystack_includes_prompt_and_reply 
tests/ace/tui/models/test_agent_panels.py::test_panel_focus_step_returns_false_when_every_other_panel_is_skipped 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_panels.py::test_panel_focus_step_returns_false_when_every_other_panel_is_skipped 
tests/artifact_file_facade/test_synthesis.py::test_committed_sdd_plan_reference_resolves_to_filesystem_path 
[gw10] [ 96%] PASSED tests/ace/tui/test_xprompt_browser_filter.py::test_xprompts_open_browse_first_with_hidden_filter 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_marks_merge_parents_and_first_parent_diff_label 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_marks_merge_parents_and_first_parent_diff_label 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_committed_sdd_plan_reference_resolves_to_filesystem_path 
tests/ace/tui/test_axe_status_read_cache.py::test_unchanged_run_records_are_not_reparsed 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_status_read_cache.py::test_unchanged_run_records_are_not_reparsed 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_id_shorthand.py::test_work_task_dry_run_uses_canonical_id_for_shorthand 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_modern_phase_row_renders_badge_without_store_confirmation 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_modern_phase_row_renders_badge_without_store_confirmation 
tests/test_bead/test_cli_dep_list.py::test_dep_list_store_wide_full_and_json_render 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_fenced_only_id 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_keeps_fenced_only_id 
tests/ace/tui/models/test_fold_scale.py::test_empty_fold_scale_is_rejected 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_empty_fold_scale_is_rejected 
tests/test_bead/test_cli_id_shorthand.py::test_pages_url_resolves_shorthand_before_building_url 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_omits_empty_author 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_omits_empty_author 
tests/artifact_file_facade/test_synthesis.py::test_absolute_sdd_plan_path_passes_through_unchanged 
tests/ace/tui/test_agent_content_search_cache.py::test_no_artifacts_dir_returns_empty_haystack 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_no_artifacts_dir_returns_empty_haystack 
tests/ace/tui/test_xprompt_browser_filter.py::test_slash_reveals_filter_without_changing_selection 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_absolute_sdd_plan_path_passes_through_unchanged 
tests/ace/tui/models/test_fold_scale.py::test_direct_positions_resolve_exactly_within_each_scale[scale0-expected0] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_direct_positions_resolve_exactly_within_each_scale[scale0-expected0] 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_tolerates_unparseable_prompt_without_id 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_tolerates_unparseable_prompt_without_id 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_view_spec_preserves_owner_context_and_full_tagged_message 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_view_spec_preserves_owner_context_and_full_tagged_message 
tests/artifact_file_facade/test_synthesis.py::test_sdd_plan_reference_miss_yields_a_real_candidate_location 
tests/ace/tui/test_axe_status_read_cache.py::test_run_json_mtime_change_invalidates_cache 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_sdd_plan_reference_miss_yields_a_real_candidate_location 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_status_read_cache.py::test_run_json_mtime_change_invalidates_cache 
tests/ace/tui/test_agent_content_search_cache.py::test_cache_reuses_entry_when_mtime_unchanged 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_cache_reuses_entry_when_mtime_unchanged 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_confirmed_phase_agent_row_renders_bead_badge 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_confirmed_phase_agent_row_renders_bead_badge 
tests/ace/tui/models/test_fold_scale.py::test_direct_positions_resolve_exactly_within_each_scale[scale1-expected1] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_direct_positions_resolve_exactly_within_each_scale[scale1-expected1] 
tests/agents_sync/test_commit_publication_queue.py::test_large_backlog_builds_one_inventory_and_publishes_each_hood_once 
tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_reopens_named_unparseable_prompt 
[gw6] [ 96%] PASSED tests/ace/tui/test_kill_and_edit_prompt_name.py::test_prepare_kill_and_edit_prompt_reopens_named_unparseable_prompt 
tests/ace/tui/models/test_agent_panels.py::test_panel_focus_default_step_and_single_panel_behavior_are_unchanged 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_panels.py::test_panel_focus_default_step_and_single_panel_behavior_are_unchanged 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_view_spec_carries_merge_parent_ids 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_view_spec_carries_merge_parent_ids 
tests/artifact_file_facade/test_synthesis.py::test_sdd_plan_reference_without_workspace_dir_passes_through_unchanged 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_id_shorthand.py::test_pages_url_resolves_shorthand_before_building_url 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_sdd_plan_reference_without_workspace_dir_passes_through_unchanged 
[gw4] [ 96%] PASSED tests/agents_sync/test_commit_publication_queue.py::test_large_backlog_builds_one_inventory_and_publishes_each_hood_once 
tests/ace/tui/test_agent_content_search_cache.py::test_cache_refreshes_when_mtime_changes 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_cache_refreshes_when_mtime_changes 
[gw3] [ 96%] PASSED tests/ace/tui/test_statistics_pane_filters.py::test_empty_project_filter_clears_to_all_projects_in_either_direction[P-core-Core] 
tests/ace/tui/models/test_fold_scale.py::test_direct_positions_resolve_exactly_within_each_scale[scale2-expected2] 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_direct_positions_resolve_exactly_within_each_scale[scale2-expected2] 
tests/test_bead/test_cli_list.py::test_handle_bead_list_json_outputs_envelope 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_store_wide_full_and_json_render 
tests/ace/tui/test_axe_status_read_cache.py::test_log_tail_rereads_only_when_size_grows 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_status_read_cache.py::test_log_tail_rereads_only_when_size_grows 
tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_bounds_byte_heavy_diff_and_explains_truncation 
tests/artifact_file_facade/test_synthesis.py::test_home_plan_is_skipped_when_matching_workspace_plan_exists 
tests/ace/tui/test_config_center_state.py::test_failed_replace_preserves_destination_and_cleans_temporary 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_synthesis.py::test_home_plan_is_skipped_when_matching_workspace_plan_exists 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commit_detail_bounds_byte_heavy_diff_and_explains_truncation 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_state.py::test_failed_replace_preserves_destination_and_cleans_temporary 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_confirmed_land_agent_row_renders_epic_bead_badge 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_confirmed_land_agent_row_renders_epic_bead_badge 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list.py::test_handle_bead_list_json_outputs_envelope 
tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_cycle_is_inert_without_choices_and_handles_stale_selection 
[gw3] [ 96%] PASSED tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_cycle_is_inert_without_choices_and_handles_stale_selection 
tests/ace/tui/models/test_fold_scale.py::test_direct_positions_reject_zero_negative_and_out_of_range 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_direct_positions_reject_zero_negative_and_out_of_range 
tests/ace/tui/test_agent_content_search_cache.py::test_missing_file_is_tolerated 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_missing_file_is_tolerated 
tests/test_bead/test_cli_list.py::test_handle_bead_list_json_always_emits_size 
tests/test_bead/test_cli_dep_list.py::test_dep_list_store_wide_status_default_filters_closed_sources 
[gw11] [ 96%] PASSED tests/test_command_palette_wiring.py::test_palette_escape_dismisses_without_side_effects 
tests/artifact_file_facade/test_trash.py::test_batch_trash_uses_one_lock_and_preserves_unparsed_lines 
tests/ace/tui/test_commits_pane_rendering.py::test_commits_timeline_mounted_rows_stay_one_line_with_jump_hints 
tests/ace/tui/test_config_center_state.py::test_save_rejects_non_catalog_current_tab 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_state.py::test_save_rejects_non_catalog_current_tab 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_trash.py::test_batch_trash_uses_one_lock_and_preserves_unparsed_lines 
tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths 
tests/ace/tui/test_axe_worker_status_completion.py::test_restart_completion_clears_transient_state_before_repoll 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_worker_status_completion.py::test_restart_completion_clears_transient_state_before_repoll 
tests/ace/tui/models/test_fold_scale.py::test_family_direct_level_one_is_expanded_not_global_collapsed 
tests/ace/tui/models/test_agent_phase_bead_summary.py::test_phase_display_keeps_relative_reference_for_external_sdd_target 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_family_direct_level_one_is_expanded_not_global_collapsed 
[gw10] [ 96%] PASSED tests/ace/tui/test_xprompt_browser_filter.py::test_slash_reveals_filter_without_changing_selection 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_phase_bead_summary.py::test_phase_display_keeps_relative_reference_for_external_sdd_target 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_confirmed_exact_land_agent_row_renders_epic_bead_badge 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_confirmed_exact_land_agent_row_renders_epic_bead_badge 
tests/ace/tui/test_agent_content_search_cache.py::test_size_cap_limits_cached_content 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_size_cap_limits_cached_content 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list.py::test_handle_bead_list_json_always_emits_size 
tests/test_command_palette_wiring.py::test_palette_executes_refresh_via_action 
tests/ace/tui/test_config_center_state.py::test_save_drops_alternate_matching_current 
tests/artifact_file_facade/test_trash.py::test_byte_free_row_round_trips_with_identical_fields_and_id 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_state.py::test_save_drops_alternate_matching_current 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_trash.py::test_byte_free_row_round_trips_with_identical_fields_and_id 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_store_wide_status_default_filters_closed_sources 
tests/ace/tui/models/test_fold_scale.py::test_summary_selection_resolves_kind_specific_scale 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_summary_selection_resolves_kind_specific_scale 
tests/test_bead/test_cli_list.py::test_handle_bead_list_includes_snoozed_by_default 
tests/ace/tui/test_xprompt_browser_filter.py::test_live_filter_updates_rows_preview_bookmark_and_jump_state 
tests/ace/tui/test_axe_worker_status_completion.py::test_running_restart_completion_does_not_schedule_repolls 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_worker_status_completion.py::test_running_restart_completion_does_not_schedule_repolls 
tests/ace/tui/test_config_center_tabs.py::test_catalog_is_the_single_numbered_alphabetical_source 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_catalog_is_the_single_numbered_alphabetical_source 
tests/artifact_file_facade/test_trash.py::test_purge_respects_cutoff_and_all 
tests/ace/tui/models/test_fold_scale.py::test_lane_fold_scale_uses_family_or_shared_agent_scale 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_fold_scale.py::test_lane_fold_scale_uses_family_or_shared_agent_scale 
tests/test_bead/test_cli_dep_list.py::test_dep_list_limit_caps_store_wide_root_beads 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_confirmed_dismissed_phase_agent_row_renders_bead_badge 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_confirmed_dismissed_phase_agent_row_renders_bead_badge 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_trash.py::test_purge_respects_cutoff_and_all 
tests/ace/tui/test_config_center_tabs.py::test_config_tab_description_follows_rollout_flag 
[gw13] [ 96%] PASSED tests/ace/tui/test_commits_pane_rendering.py::test_commits_timeline_mounted_rows_stay_one_line_with_jump_hints 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_config_tab_description_follows_rollout_flag 
tests/agents_sync/test_commit_publication_queue.py::test_mixed_queue_publishes_good_items_and_quarantines_only_bad_item 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list.py::test_handle_bead_list_includes_snoozed_by_default 
tests/ace/tui/models/test_agent_phase_bead_summary.py::test_modern_phase_normalizes_epic_title_once 
tests/ace/tui/models/test_gate_rows.py::test_settling_gate_meta_projects_start_label_and_bucket 
tests/ace/tui/test_axe_worker_status_completion.py::test_stop_completion_clears_transient_state_without_repolls 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_worker_status_completion.py::test_stop_completion_clears_transient_state_without_repolls 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_gate_rows.py::test_settling_gate_meta_projects_start_label_and_bucket 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_phase_bead_summary.py::test_modern_phase_normalizes_epic_title_once 
tests/artifact_file_facade/test_trash.py::test_core_failure_leaves_prior_rows_trashed_and_remaining_rows_live 
tests/test_bead/test_cli_list.py::test_handle_bead_list_json_empty_store_is_valid_envelope 
tests/ace/tui/test_config_center_tabs.py::test_numbered_tab_strip_plain_text_and_click_ranges_without_selection 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_numbered_tab_strip_plain_text_and_click_ranges_without_selection 
tests/ace/tui/test_common_placeholders_cache.py::test_loader_seeds_once_then_loads_on_the_first_warm 
[gw13] [ 96%] PASSED tests/ace/tui/test_common_placeholders_cache.py::test_loader_seeds_once_then_loads_on_the_first_warm 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_trash.py::test_core_failure_leaves_prior_rows_trashed_and_remaining_rows_live 
tests/ace/tui/models/test_gate_rows.py::test_gate_starter_keeps_reference_without_gate_row_semantics 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_gate_rows.py::test_gate_starter_keeps_reference_without_gate_row_semantics 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_expired_confirmed_bead_row_keeps_badge_and_revalidates 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_expired_confirmed_bead_row_keeps_badge_and_revalidates 
tests/ace/tui/test_config_center_tabs.py::test_tab_strip_can_uppercase_only_the_active_canonical_label 
tests/ace/tui/test_axe_worker_status_completion.py::test_failed_restart_completion_clears_transient_state 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_worker_status_completion.py::test_failed_restart_completion_clears_transient_state 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_tab_strip_can_uppercase_only_the_active_canonical_label 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list.py::test_handle_bead_list_json_empty_store_is_valid_envelope 
tests/ace/tui/test_common_placeholders_cache.py::test_loader_skips_the_seed_and_the_read_for_an_unchanged_token 
[gw13] [ 96%] PASSED tests/ace/tui/test_common_placeholders_cache.py::test_loader_skips_the_seed_and_the_read_for_an_unchanged_token 
tests/artifact_file_facade/test_vcs.py::test_materialize_artifact_file_uses_verified_content_cache 
tests/test_bead/test_cli_list.py::test_handle_bead_list_json_reports_implicit_closed_without_notice 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_vcs.py::test_materialize_artifact_file_uses_verified_content_cache 
tests/ace/tui/models/test_gate_rows.py::test_filesystem_gate_meta_projects_detail_fields 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_gate_rows.py::test_filesystem_gate_meta_projects_detail_fields 
tests/ace/tui/test_config_center_tabs.py::test_micro_tab_tier_is_opt_in_and_uses_numbered_micro_labels 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_micro_tab_tier_is_opt_in_and_uses_numbered_micro_labels 
tests/ace/tui/test_common_placeholders_cache.py::test_loader_applies_the_configured_limit_to_the_warm_index 
[gw13] [ 96%] PASSED tests/ace/tui/test_common_placeholders_cache.py::test_loader_applies_the_configured_limit_to_the_warm_index 
tests/ace/tui/models/test_agent_phase_bead_summary.py::test_modern_phase_normalizes_folded_phase_title 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_phase_bead_summary.py::test_modern_phase_normalizes_folded_phase_title 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_cold_bead_candidate_row_omits_bead_badge 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_cold_bead_candidate_row_omits_bead_badge 
tests/ace/tui/test_axe_worker_status_completion.py::test_config_restart_failure_keeps_saved_write_truthful 
[gw1] [ 96%] PASSED tests/ace/tui/test_axe_worker_status_completion.py::test_config_restart_failure_keeps_saved_write_truthful 
tests/ace/tui/models/test_gate_rows.py::test_terminal_gate_done_projects_stop_label_and_followup_fields 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_gate_rows.py::test_terminal_gate_done_projects_stop_label_and_followup_fields 
tests/artifact_file_facade/test_vcs.py::test_store_default_reference_writes_no_artifact_bytes 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_vcs.py::test_store_default_reference_writes_no_artifact_bytes 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_limit_caps_store_wide_root_beads 
tests/ace/tui/test_config_center_tabs.py::test_title_has_no_leading_icon_and_underline_matches 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_title_has_no_leading_icon_and_underline_matches 
[gw4] [ 96%] PASSED tests/agents_sync/test_commit_publication_queue.py::test_mixed_queue_publishes_good_items_and_quarantines_only_bad_item 
tests/ace/tui/test_common_placeholders_cache.py::test_forget_prunes_index_publishes_and_forces_disk_reload 
[gw13] [ 96%] PASSED tests/ace/tui/test_common_placeholders_cache.py::test_forget_prunes_index_publishes_and_forces_disk_reload 
tests/ace/tui/models/test_gate_rows.py::test_filesystem_done_gate_row_projects_custom_stop_status 
[gw3] [ 96%] PASSED tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_gate_rows.py::test_filesystem_done_gate_row_projects_custom_stop_status 
[gw11] [ 96%] PASSED tests/test_command_palette_wiring.py::test_palette_executes_refresh_via_action 
tests/artifact_file_facade/test_vcs.py::test_vcs_ids_and_dedupe_keys_are_stable_and_revision_specific 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_vcs.py::test_vcs_ids_and_dedupe_keys_are_stable_and_revision_specific 
tests/test_bead/test_cli_dep_list.py::test_dep_list_unknown_id_exits_one 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list.py::test_handle_bead_list_json_reports_implicit_closed_without_notice 
tests/ace/tui/test_config_center_tabs.py::test_resume_tab_validation_accepts_only_catalog_ids 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_resume_tab_validation_accepts_only_catalog_ids 
tests/ace/tui/test_bead_close_modal.py::test_close_requires_reason_and_previews_descendants 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_missing_bead_candidate_row_omits_bead_badge 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_missing_bead_candidate_row_omits_bead_badge 
tests/ace/tui/test_statistics_pane_filters.py::test_custom_range_accepts_valid_input_and_rejects_invalid_input 
tests/test_bead/test_cli_list.py::test_handle_bead_list_json_limit_preserves_total 
tests/ace/tui/test_comprehensive_update_preview.py::test_update_scope_legs 
tests/ace/tui/models/test_gate_rows.py::test_answered_handoff_gate_members_bucket_running 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_gate_rows.py::test_answered_handoff_gate_members_bucket_running 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_update_scope_legs 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_close_modal.py::test_close_requires_reason_and_previews_descendants 
tests/artifact_file_facade/test_vcs.py::test_dedupe_tolerates_byte_free_row_with_incomplete_provenance 
[gw7] [ 96%] PASSED tests/artifact_file_facade/test_vcs.py::test_dedupe_tolerates_byte_free_row_with_incomplete_provenance 
tests/ace/tui/test_config_center_tabs.py::test_home_hint_explains_no_history_and_uses_catalog_resume_style 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_home_hint_explains_no_history_and_uses_catalog_resume_style 
tests/ace/tui/models/test_agent_phase_bead_summary.py::test_blank_phase_title_degrades_to_unavailable 
tests/test_command_palette_wiring.py::test_palette_omits_inapplicable_axe_only_command_on_cls_tab 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_phase_bead_summary.py::test_blank_phase_title_degrades_to_unavailable 
tests/ace/tui/test_agent_content_search_cache.py::test_prune_drops_entries_for_missing_agents 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_prune_drops_entries_for_missing_agents 
tests/ace/tui/models/test_gate_rows.py::test_non_handoff_settled_gate_members_keep_gate_state_bucket 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_gate_rows.py::test_non_handoff_settled_gate_members_keep_gate_state_bucket 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_unknown_id_exits_one 
tests/ace/tui/test_comprehensive_update_preview.py::test_collect_update_preview_inputs_skips_unneeded_legs 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_collect_update_preview_inputs_skips_unneeded_legs 
tests/artifact_links/test_agent_bead_projection.py::test_emits_one_row_per_bead_field 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_emits_one_row_per_bead_field 
tests/ace/tui/test_config_center_tabs.py::test_tab_cycle_bindings_are_modal_priority 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_tab_cycle_bindings_are_modal_priority 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_deleted_bead_candidate_row_drops_badge_after_reresolve 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_deleted_bead_candidate_row_drops_badge_after_reresolve 
tests/ace/tui/test_agent_content_search_cache.py::test_haystack_includes_attempt_replies 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_haystack_includes_attempt_replies 
tests/ace/tui/test_bead_close_modal.py::test_force_selects_non_done_resolution_and_returns_close_contract 
tests/ace/tui/models/test_gate_rows.py::test_done_marker_answered_tale_approved_buckets_running 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_gate_rows.py::test_done_marker_answered_tale_approved_buckets_running 
tests/test_bead/test_cli_dep_list.py::test_dep_list_color_modes_override_non_tty 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_close_modal.py::test_force_selects_non_done_resolution_and_returns_close_contract 
tests/ace/tui/test_comprehensive_update_preview.py::test_collect_update_preview_inputs_captures_provider_errors 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_collect_update_preview_inputs_captures_provider_errors 
tests/ace/tui/test_config_center_tabs.py::test_generic_modal_is_static_home_with_no_concrete_panes 
tests/artifact_links/test_agent_bead_projection.py::test_three_bead_fields_stay_distinguishable_by_description 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_three_bead_fields_stay_distinguishable_by_description 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list.py::test_handle_bead_list_json_limit_preserves_total 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_generic_modal_is_static_home_with_no_concrete_panes 
tests/ace/tui/models/test_gate_rows.py::test_filesystem_done_gate_row_tale_approved_buckets_running 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_gate_rows.py::test_filesystem_done_gate_row_tale_approved_buckets_running 
tests/test_bead/test_cli_list.py::test_handle_bead_list_full_reuses_show_rendering 
tests/ace/tui/test_agent_content_search_cache.py::test_haystack_includes_chat_path_fallback 
tests/ace/tui/test_comprehensive_update_preview.py::test_build_preview_everything_plans_selected_legs 
tests/ace/tui/models/test_agent_phase_bead_summary.py::test_selected_phase_title_never_leaks_peer_phase 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_ordinary_agent_row_omits_bead_badge 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_ordinary_agent_row_omits_bead_badge 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_build_preview_everything_plans_selected_legs 
tests/ace/tui/test_config_center_tabs.py::test_importing_lightweight_modal_does_not_import_concrete_panes 
tests/artifact_links/test_agent_bead_projection.py::test_skips_agent_with_no_bead_fields 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_phase_bead_summary.py::test_selected_phase_title_never_leaks_peer_phase 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_haystack_includes_chat_path_fallback 
tests/ace/tui/test_bead_create_modal.py::test_create_modal_requires_and_returns_an_explicit_size 
tests/ace/tui/models/test_group_fold.py::test_agent_owner_exposes_neutral_per_panel_registry 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_group_fold.py::test_agent_owner_exposes_neutral_per_panel_registry 
[gw10] [ 96%] PASSED tests/ace/tui/test_xprompt_browser_filter.py::test_live_filter_updates_rows_preview_bookmark_and_jump_state 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_create_modal.py::test_create_modal_requires_and_returns_an_explicit_size 
tests/ace/tui/test_comprehensive_update_preview.py::test_build_preview_sase_scope_omits_other_legs 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_build_preview_sase_scope_omits_other_legs 
tests/agents_sync/test_commit_publication_queue.py::test_no_publishable_runs_retries_once_then_retires 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_skips_agent_with_no_bead_fields 
tests/ace/tui/test_agent_content_search_cache.py::test_build_index_includes_all_agent_content_sources 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_build_index_includes_all_agent_content_sources 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_dotted_ordinary_agent_row_omits_bead_badge 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_dotted_ordinary_agent_row_omits_bead_badge 
tests/ace/tui/test_xprompt_browser_filter.py::test_enter_and_escape_keep_query_and_restore_list_focus 
tests/ace/tui/test_comprehensive_update_preview.py::test_build_preview_providers_scope_omits_other_legs 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_build_preview_providers_scope_omits_other_legs 
tests/ace/tui/test_agent_content_search_cache.py::test_index_serves_haystacks_without_file_cache_reads 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_index_serves_haystacks_without_file_cache_reads 
tests/artifact_links/test_agent_bead_projection.py::test_skips_a_blank_bead_field 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_skips_a_blank_bead_field 
[gw4] [ 96%] PASSED tests/agents_sync/test_commit_publication_queue.py::test_no_publishable_runs_retries_once_then_retires 
tests/ace/tui/models/test_group_fold.py::test_default_registry_has_no_collapsed_groups 
tests/ace/tui/test_bead_snooze_modal.py::test_presets_resolve_to_future_wake_times 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_presets_resolve_to_future_wake_times 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list.py::test_handle_bead_list_full_reuses_show_rendering 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_group_fold.py::test_default_registry_has_no_collapsed_groups 
[gw11] [ 96%] PASSED tests/test_command_palette_wiring.py::test_palette_omits_inapplicable_axe_only_command_on_cls_tab 
tests/ace/tui/models/test_agent_phase_bead_summary.py::test_phase_bead_normalizes_missing_legacy_size_to_small 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_phase_bead_summary.py::test_phase_bead_normalizes_missing_legacy_size_to_small 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_color_modes_override_non_tty 
tests/test_bead/test_cli_list.py::test_handle_bead_list_explicit_compact_matches_default 
tests/ace/tui/test_comprehensive_update_preview.py::test_cached_current_status_still_runs_sase_planner_for_editables 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_cached_current_status_still_runs_sase_planner_for_editables 
tests/ace/tui/test_agent_content_search_cache.py::test_cache_fork_populate_and_merge 
tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_bead_badge_flows_from_fold_annotation_to_agent_name 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_cache_fork_populate_and_merge 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bead_badges.py::TestAgentListBeadBadge::test_bead_badge_flows_from_fold_annotation_to_agent_name 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list.py::test_handle_bead_list_explicit_compact_matches_default 
tests/artifact_links/test_agent_bead_projection.py::test_no_agents_root_is_a_no_op 
tests/test_command_palette_wiring.py::test_palette_context_uses_current_tab_badge 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_no_agents_root_is_a_no_op 
[gw3] [ 96%] PASSED tests/ace/tui/test_statistics_pane_filters.py::test_custom_range_accepts_valid_input_and_rejects_invalid_input 
tests/ace/tui/models/test_group_fold.py::test_collapse_returns_true_only_on_first_change 
[gw6] [ 96%] PASSED tests/ace/tui/test_config_center_tabs.py::test_importing_lightweight_modal_does_not_import_concrete_panes 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_group_fold.py::test_collapse_returns_true_only_on_first_change 
tests/ace/tui/test_bead_snooze_modal.py::test_day_presets_span_their_advertised_range[3-lower0-upper0] 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_day_presets_span_their_advertised_range[3-lower0-upper0] 
tests/test_bead/test_cli_dep_list.py::test_dep_list_json_is_never_colored 
tests/test_bead/test_cli_list_compact.py::test_handle_bead_list_compact_summary_counts_printed_limited_rows 
tests/ace/tui/test_comprehensive_update_preview.py::test_fresh_current_sase_plan_reports_current_noop 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_fresh_current_sase_plan_reports_current_noop 
tests/ace/tui/test_agent_content_search_cache.py::test_substring_match_semantics 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_content_search_cache.py::test_substring_match_semantics 
tests/ace/tui/test_statistics_pane_interactions.py::test_xprompt_focus_picker_all_clear_key_and_cancel 
tests/artifact_links/test_agent_bead_projection.py::test_no_agents_directory_under_the_root_is_a_no_op 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_no_agents_directory_under_the_root_is_a_no_op 
tests/ace/tui/widgets/test_agent_list_bindings.py::test_mark_prefix_renders_when_marked 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bindings.py::test_mark_prefix_renders_when_marked 
tests/ace/tui/models/test_group_fold.py::test_expand_undoes_collapse_and_is_idempotent 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_group_fold.py::test_expand_undoes_collapse_and_is_idempotent 
tests/ace/tui/test_comprehensive_update_preview.py::test_non_currency_sase_noop_keeps_blocking_reason 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_non_currency_sase_noop_keeps_blocking_reason 
tests/ace/tui/test_agent_context_members.py::test_promoted_root_context_label_uses_suffix_token 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_context_members.py::test_promoted_root_context_label_uses_suffix_token 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list_compact.py::test_handle_bead_list_compact_summary_counts_printed_limited_rows 
tests/ace/tui/models/test_agent_phase_bead_summary.py::test_unreadable_modern_phase_keeps_only_identity_and_known_path 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_phase_bead_summary.py::test_unreadable_modern_phase_keeps_only_identity_and_known_path 
tests/ace/tui/test_bead_snooze_modal.py::test_day_presets_span_their_advertised_range[4-lower1-upper1] 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_day_presets_span_their_advertised_range[4-lower1-upper1] 
tests/artifact_links/test_agent_bead_projection.py::test_unparseable_meta_json_contributes_no_row 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_unparseable_meta_json_contributes_no_row 
tests/test_bead/test_cli_list_compact.py::test_handle_bead_list_implicit_closed_summary_hint_respects_explicit_limit 
tests/ace/tui/models/test_group_fold.py::test_clear_unknown_drops_stale_keys 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_group_fold.py::test_clear_unknown_drops_stale_keys 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_json_is_never_colored 
tests/ace/tui/test_comprehensive_update_preview.py::test_cached_current_managed_only_preview_keeps_current_fallback 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_cached_current_managed_only_preview_keeps_current_fallback 
tests/ace/tui/test_agent_context_members.py::test_historical_q_suffix_context_label_uses_suffix_token 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_context_members.py::test_historical_q_suffix_context_label_uses_suffix_token 
tests/ace/tui/widgets/test_agent_list_bindings.py::test_mark_prefix_absent_when_unmarked 
tests/artifact_links/test_agent_bead_projection.py::test_warm_run_is_idempotent_when_nothing_changed 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bindings.py::test_mark_prefix_absent_when_unmarked 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_warm_run_is_idempotent_when_nothing_changed 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list_compact.py::test_handle_bead_list_implicit_closed_summary_hint_respects_explicit_limit 
tests/ace/tui/models/test_group_fold.py::test_version_increments_only_on_real_mutation 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_group_fold.py::test_version_increments_only_on_real_mutation 
tests/test_bead/test_cli_dep_list.py::test_dep_list_empty_messages_are_successful 
tests/ace/tui/test_bead_snooze_modal.py::test_tomorrow_morning_preset_wakes_at_nine_the_next_day 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_tomorrow_morning_preset_wakes_at_nine_the_next_day 
tests/ace/tui/test_comprehensive_update_preview.py::test_missing_or_failed_cache_does_not_claim_sase_current 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_missing_or_failed_cache_does_not_claim_sase_current 
tests/test_bead/test_cli_list_compact.py::test_list_compact_renders_type_glyph_only_per_type 
tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_is_empty_when_all_counts_are_zero 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_is_empty_when_all_counts_are_zero 
[gw10] [ 96%] PASSED tests/ace/tui/test_xprompt_browser_filter.py::test_enter_and_escape_keep_query_and_restore_list_focus 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_empty_messages_are_successful 
tests/artifact_links/test_agent_bead_projection.py::test_stale_agent_disappears_after_it_is_removed_from_disk 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_stale_agent_disappears_after_it_is_removed_from_disk 
tests/ace/tui/models/test_imported_family_tree.py::test_imported_family_renders_grouped_without_code_orphan_roots 
tests/agents_sync/test_commit_publication_queue.py::test_repeated_format_publication_failure_retires_and_doctor_says_drop 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_imported_family_tree.py::test_imported_family_renders_grouped_without_code_orphan_roots 
tests/ace/tui/test_comprehensive_update_preview.py::test_not_uv_tool_install_blocks_sase_leg 
tests/ace/tui/models/test_agent_phase_bead_summary.py::test_phase_bead_cache_refreshes_description_and_title_after_plan_edit 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_not_uv_tool_install_blocks_sase_leg 
[gw4] [ 96%] PASSED tests/agents_sync/test_commit_publication_queue.py::test_repeated_format_publication_failure_retires_and_doctor_says_drop 
[gw11] [ 96%] PASSED tests/test_command_palette_wiring.py::test_palette_context_uses_current_tab_badge 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_renders_type_glyph_only_per_type 
tests/ace/tui/widgets/test_agent_list_bindings.py::test_tribe_badge_omitted_for_tribe_assigned_agent_row 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bindings.py::test_tribe_badge_omitted_for_tribe_assigned_agent_row 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_phase_bead_summary.py::test_phase_bead_cache_refreshes_description_and_title_after_plan_edit 
tests/ace/tui/test_xprompt_browser_filter.py::test_cached_reactivation_restores_open_filter_or_list 
tests/test_bead/test_cli_dep_list.py::test_dep_list_rows_carry_the_bead_created_cell_separate_from_edge_provenance 
tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_renders_one_status_and_multi_digit_count 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_renders_one_status_and_multi_digit_count 
tests/ace/tui/models/test_imported_family_tree.py::test_reviving_imported_family_restores_root_and_members 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_imported_family_tree.py::test_reviving_imported_family_restores_root_and_members 
tests/artifact_links/test_agent_bead_projection.py::test_only_the_changed_agent_is_reparsed 
tests/ace/tui/test_bead_snooze_modal.py::test__next_morning_always_skips_to_the_following_day 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test__next_morning_always_skips_to_the_following_day 
tests/test_bead/test_cli_list_compact.py::test_list_compact_type_cells_share_equal_cell_width 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_bead_projection.py::test_only_the_changed_agent_is_reparsed 
tests/ace/tui/test_config_center_tabs.py::test_home_tab_directions_and_digits_mount_only_requested_panes 
tests/test_command_palette_wiring.py::test_palette_filter_input_swallows_typing_no_action_dispatched 
tests/ace/tui/test_comprehensive_update_preview.py::test_comprehensive_confirm_copy[everything-Update everything-snapshot-gated SASE and provider] 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_comprehensive_confirm_copy[everything-Update everything-snapshot-gated SASE and provider] 
tests/ace/tui/models/test_imported_family_tree.py::test_imported_source_owner_loads_from_meta_and_bundle 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_imported_family_tree.py::test_imported_source_owner_loads_from_meta_and_bundle 
tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_uses_canonical_order_and_status_styles 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_uses_canonical_order_and_status_styles 
tests/artifact_links/test_agent_cites_plan.py::test_emits_a_row_per_published_agent_and_skips_the_unpublished_one 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_cites_plan.py::test_emits_a_row_per_published_agent_and_skips_the_unpublished_one 
tests/ace/tui/widgets/test_agent_list_bindings.py::test_plain_agent_without_tribe_omits_at_annotation 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bindings.py::test_plain_agent_without_tribe_omits_at_annotation 
tests/ace/tui/test_comprehensive_update_preview.py::test_comprehensive_confirm_copy[sase-Update SASE, core & plugins-Confirm the SASE, core, and plugin work below.] 
tests/ace/tui/test_bead_snooze_modal.py::test_cancel_choice_exists_only_in_resnooze_mode 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_cancel_choice_exists_only_in_resnooze_mode 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_comprehensive_confirm_copy[sase-Update SASE, core & plugins-Confirm the SASE, core, and plugin work below.] 
tests/ace/tui/models/test_imported_family_tree.py::test_synthetic_imported_family_parent_is_not_persisted 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_imported_family_tree.py::test_synthetic_imported_family_parent_is_not_persisted 
tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_can_override_chrome_and_letter_styles 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_can_override_chrome_and_letter_styles 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_type_cells_share_equal_cell_width 
tests/artifact_links/test_agent_cites_plan.py::test_skips_when_no_agent_resolves_as_published 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_cites_plan.py::test_skips_when_no_agent_resolves_as_published 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_selects_standalone_xprompt_procs_and_dedupes 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_selects_standalone_xprompt_procs_and_dedupes 
tests/test_bead/test_cli_list_compact.py::test_list_compact_renders_size_tokens_for_every_stored_size 
tests/ace/tui/test_comprehensive_update_preview.py::test_comprehensive_confirm_copy[providers-Update providers-Confirm the exact provider update commands below] 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_comprehensive_confirm_copy[providers-Update providers-Confirm the exact provider update commands below] 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_list.py::test_dep_list_rows_carry_the_bead_created_cell_separate_from_edge_provenance 
tests/ace/tui/models/test_loader_executor_shutdown.py::test_shutdown_loader_executor_cancels_pending_and_resets 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_loader_executor_shutdown.py::test_shutdown_loader_executor_cancels_pending_and_resets 
tests/ace/tui/widgets/test_agent_list_bindings.py::test_agent_list_merged_bindings_exclude_enter 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bindings.py::test_agent_list_merged_bindings_exclude_enter 
tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_suppresses_zero_metrics 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_suppresses_zero_metrics 
tests/artifact_links/test_agent_cites_plan.py::test_skips_when_there_is_no_agents_sidecar_clone 
tests/ace/tui/test_bead_snooze_modal.py::test_title_names_the_wake_time_a_resnooze_replaces 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_cites_plan.py::test_skips_when_there_is_no_agents_sidecar_clone 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_title_names_the_wake_time_a_resnooze_replaces 
tests/ace/tui/test_comprehensive_update_preview.py::test_scoped_noop_messages_name_the_scope 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_scoped_noop_messages_name_the_scope 
tests/test_bead/test_cli_dep_rm.py::test_dep_rm_removes_edge_reports_readiness_and_records_history 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_renders_size_tokens_for_every_stored_size 
tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_uses_canonical_bright_pink_queue_style 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_count_chip.py::test_agent_count_chip_uses_canonical_bright_pink_queue_style 
tests/artifact_links/test_agent_cites_plan.py::test_skips_a_plan_with_no_prompt_section 
tests/ace/tui/models/test_loader_executor_shutdown.py::test_shutdown_loader_executor_is_noop_without_pool 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_cites_plan.py::test_skips_a_plan_with_no_prompt_section 
[gw12] [ 96%] PASSED tests/ace/tui/models/test_loader_executor_shutdown.py::test_shutdown_loader_executor_is_noop_without_pool 
tests/test_bead/test_cli_list_compact.py::test_list_compact_collapses_size_column_when_no_rows_are_sized 
tests/ace/tui/widgets/test_agent_list_bindings.py::test_enter_passthrough_reaches_app_binding 
tests/ace/tui/test_comprehensive_update_preview.py::test_confirm_modal_includes_only_selected_sections 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_confirm_modal_includes_only_selected_sections 
tests/ace/tui/test_bead_snooze_modal.py::test_custom_field_accepts_the_shared_duration_and_reason 
tests/agents_sync/test_commit_publication_target_resolution.py::test_resolves_known_repository_kinds 
[gw8] [ 96%] PASSED tests/ace/tui/widgets/test_agent_list_bindings.py::test_enter_passthrough_reaches_app_binding 
[gw4] [ 96%] PASSED tests/agents_sync/test_commit_publication_target_resolution.py::test_resolves_known_repository_kinds 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_skips_dismissed_proc_ids 
[gw0] [ 96%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_skips_dismissed_proc_ids 
tests/agents_sync/test_publication.py::test_publication_links_commits_for_github_primary_remote 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_selects_adjacent_whole_panel[1-2-2] 
[gw5] [ 96%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_selects_adjacent_whole_panel[1-2-2] 
tests/artifact_links/test_agent_cites_plan.py::test_skips_when_the_archived_prompt_is_missing 
[gw7] [ 96%] PASSED tests/artifact_links/test_agent_cites_plan.py::test_skips_when_the_archived_prompt_is_missing 
[gw2] [ 96%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_collapses_size_column_when_no_rows_are_sized 
[gw1] [ 96%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_custom_field_accepts_the_shared_duration_and_reason 
[gw9] [ 96%] PASSED tests/test_bead/test_cli_dep_rm.py::test_dep_rm_removes_edge_reports_readiness_and_records_history 
tests/ace/tui/test_comprehensive_update_preview.py::test_noop_without_admin_center_points_at_updates_tab 
[gw13] [ 96%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_noop_without_admin_center_points_at_updates_tab 
tests/test_bead/test_cli_list_compact.py::test_list_compact_pads_unsized_rows_when_any_row_is_sized 
tests/artifact_links/test_agent_cites_plan.py::test_skips_a_non_plan_ref 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_selects_adjacent_whole_panel[-1-0-0] 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_selects_adjacent_whole_panel[-1-0-0] 
[gw7] [ 97%] PASSED tests/artifact_links/test_agent_cites_plan.py::test_skips_a_non_plan_ref 
tests/test_bead/test_cli_dep_rm.py::test_dep_rm_reports_the_remaining_active_blocker 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_diff_path_renders_pencil 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_diff_path_renders_pencil 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_pads_unsized_rows_when_any_row_is_sized 
[gw10] [ 97%] PASSED tests/ace/tui/test_xprompt_browser_filter.py::test_cached_reactivation_restores_open_filter_or_list 
tests/ace/tui/test_comprehensive_update_preview.py::test_scoped_current_noop_names_sase 
[gw13] [ 97%] PASSED tests/ace/tui/test_comprehensive_update_preview.py::test_scoped_current_noop_names_sase 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication.py::test_publication_links_commits_for_github_primary_remote 
tests/ace/tui/test_bead_snooze_modal.py::test_reason_field_rides_along_with_a_preset 
tests/test_bead/test_cli_list_compact.py::test_list_formats_render_sizes_coherently 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_panel_escape_wraps[None-0--1-beta] 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_panel_escape_wraps[None-0--1-beta] 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_center_tabs.py::test_home_tab_directions_and_digits_mount_only_requested_panes 
tests/artifact_links/test_chop_agent_projection.py::test_resolves_a_for_each_expanded_chop_agent 
[gw7] [ 97%] PASSED tests/artifact_links/test_chop_agent_projection.py::test_resolves_a_for_each_expanded_chop_agent 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_reason_field_rides_along_with_a_preset 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_rm.py::test_dep_rm_reports_the_remaining_active_blocker 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[pending-STARTING-Starting] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[pending-STARTING-Starting] 
tests/ace/tui/test_xprompt_browser_filter.py::test_no_match_filter_clears_preview_and_stays_safe 
tests/ace/tui/test_config_center_alternate_tab.py::test_alternate_opener_ping_pongs_between_exactly_two_sections 
tests/agents_sync/test_publication.py::test_two_owner_manifests_coexist_and_indexes_converge 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_formats_render_sizes_coherently 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_panel_escape_wraps[beta-2-1-None] 
tests/ace/tui/test_config_center_tabs.py::test_tab_click_mounts_target_and_reentry_reuses_state 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_classified_real_diff_renders_pencil 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_classified_real_diff_renders_pencil 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_panel_escape_wraps[beta-2-1-None] 
tests/test_bead/test_cli_dep_rm.py::test_dep_rm_errors_are_nonzero_and_leave_the_batch_untouched 
tests/artifact_links/test_chop_agent_projection.py::test_a_disabled_chop_still_resolves 
[gw7] [ 97%] PASSED tests/artifact_links/test_chop_agent_projection.py::test_a_disabled_chop_still_resolves 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_center_tabs.py::test_tab_click_mounts_target_and_reentry_reuses_state 
tests/test_bead/test_cli_list_compact.py::test_list_compact_color_modes_override_non_tty 
tests/ace/tui/test_bead_snooze_modal.py::test_escape_leaves_the_reason_field_without_cancelling 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_escape_can_select_collapsed_neighbor 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_escape_can_select_collapsed_neighbor 
tests/artifact_links/test_chop_agent_projection.py::test_an_agent_name_with_no_chop_segment_is_skipped 
[gw7] [ 97%] PASSED tests/artifact_links/test_chop_agent_projection.py::test_an_agent_name_with_no_chop_segment_is_skipped 
tests/ace/tui/test_config_center_tabs.py::test_landing_row_click_mounts_exact_target_and_focuses_it 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_rm.py::test_dep_rm_errors_are_nonzero_and_leave_the_batch_untouched 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_color_modes_override_non_tty 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_escape_leaves_the_reason_field_without_cancelling 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_classified_bookkeeping_diff_omits_pencil 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_classified_bookkeeping_diff_omits_pencil 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_center_tabs.py::test_landing_row_click_mounts_exact_target_and_focuses_it 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[running-RUNNING-Running] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[running-RUNNING-Running] 
tests/test_bead/test_cli_list_compact.py::test_list_compact_renders_flag_key_and_due_cells 
tests/agents_sync/test_commit_publication_target_resolution.py::test_sync_targets_use_primary_slug_or_name 
[gw4] [ 97%] PASSED tests/agents_sync/test_commit_publication_target_resolution.py::test_sync_targets_use_primary_slug_or_name 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_collapsed_grouping_banner_escapes_without_arming_agent 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_collapsed_grouping_banner_escapes_without_arming_agent 
[gw11] [ 97%] PASSED tests/test_command_palette_wiring.py::test_palette_filter_input_swallows_typing_no_action_dispatched 
tests/artifact_links/test_chop_agent_projection.py::test_a_chop_segment_that_does_not_resolve_is_skipped 
tests/test_bead/test_cli_dep_rm.py::test_dep_rm_auto_commit_message 
[gw7] [ 97%] PASSED tests/artifact_links/test_chop_agent_projection.py::test_a_chop_segment_that_does_not_resolve_is_skipped 
tests/ace/tui/test_config_center_tabs.py::test_landing_is_keyboard_transparent_and_digits_work_immediately 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication.py::test_two_owner_manifests_coexist_and_indexes_converge 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_center_tabs.py::test_landing_is_keyboard_transparent_and_digits_work_immediately 
tests/test_command_palette_wiring.py::test_action_open_command_palette_uses_real_catalog 
tests/ace/tui/test_bead_snooze_modal.py::test_unparsable_custom_duration_keeps_the_modal_open 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_multi_row_panel_keeps_intra_panel_navigation 
[gw11] [ 97%] PASSED tests/test_command_palette_wiring.py::test_action_open_command_palette_uses_real_catalog 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_without_diff_path_omits_pencil 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_multi_row_panel_keeps_intra_panel_navigation 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_without_diff_path_omits_pencil 
tests/artifact_links/test_chop_agent_projection.py::test_no_agents_root_is_a_no_op 
[gw7] [ 97%] PASSED tests/artifact_links/test_chop_agent_projection.py::test_no_agents_root_is_a_no_op 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_unparsable_custom_duration_keeps_the_modal_open 
tests/agents_sync/test_publication.py::test_publication_skips_undecodable_foreign_manifest_but_keeps_local_strict 
tests/ace/tui/test_config_center_tabs.py::test_landing_compact_class_tracks_viewport_size 
tests/test_command_palette_wiring.py::test_action_open_command_palette_dispatches_selection 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_renders_flag_key_and_due_cells 
[gw11] [ 97%] PASSED tests/test_command_palette_wiring.py::test_action_open_command_palette_dispatches_selection 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_in_only_panel_remains_row_focused 
tests/artifact_links/test_chop_agent_projection.py::test_warm_run_reuses_cache_when_nothing_changed 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_in_only_panel_remains_row_focused 
[gw7] [ 97%] PASSED tests/artifact_links/test_chop_agent_projection.py::test_warm_run_reuses_cache_when_nothing_changed 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[settling-SETTLING-Running] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[settling-SETTLING-Running] 
[gw13] [ 97%] PASSED tests/ace/tui/test_config_center_alternate_tab.py::test_alternate_opener_ping_pongs_between_exactly_two_sections 
tests/test_bead/test_cli_list_compact.py::test_list_compact_renders_typed_flag_task_cells 
[gw3] [ 97%] PASSED tests/ace/tui/test_statistics_pane_interactions.py::test_xprompt_focus_picker_all_clear_key_and_cancel 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_live_hint_renders_pencil_without_diff_path 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_live_hint_renders_pencil_without_diff_path 
tests/test_command_palette_wiring.py::test_action_open_command_palette_noop_on_cancel 
[gw11] [ 97%] PASSED tests/test_command_palette_wiring.py::test_action_open_command_palette_noop_on_cancel 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_in_merged_layout_remains_row_focused 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_lone_row_in_merged_layout_remains_row_focused 
tests/artifact_links/test_chop_agent_projection.py::test_a_new_agent_directory_is_picked_up_on_the_next_run 
tests/ace/tui/test_bead_snooze_modal.py::test_snooze_action_refuses_beads_the_store_would_reject[issue0-Only task beads can be snoozed] 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_snooze_action_refuses_beads_the_store_would_reject[issue0-Only task beads can be snoozed] 
tests/ace/tui/test_config_center_alternate_tab.py::test_single_section_visited_leaves_opener_inert 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_existing_whole_panel_focus_hops_exactly_once 
tests/test_command_palette_wiring.py::test_action_open_command_palette_unknown_id_is_silent 
tests/ace/tui/test_statistics_pane_interactions.py::test_focused_xprompt_body_renders_every_group_and_not_found 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_existing_whole_panel_focus_hops_exactly_once 
[gw11] [ 97%] PASSED tests/test_command_palette_wiring.py::test_action_open_command_palette_unknown_id_is_silent 
[gw3] [ 97%] PASSED tests/ace/tui/test_statistics_pane_interactions.py::test_focused_xprompt_body_renders_every_group_and_not_found 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_false_live_hint_omits_pencil 
[gw7] [ 97%] PASSED tests/artifact_links/test_chop_agent_projection.py::test_a_new_agent_directory_is_picked_up_on_the_next_run 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_false_live_hint_omits_pencil 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[success-DONE-Done] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[success-DONE-Done] 
tests/ace/tui/test_bead_snooze_modal.py::test_snooze_action_refuses_beads_the_store_would_reject[issue1-Only open, ready, and already snoozed task beads can be snoozed] 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_snooze_action_refuses_beads_the_store_would_reject[issue1-Only open, ready, and already snoozed task beads can be snoozed] 
tests/agents_sync/test_commit_publication_target_resolution.py::test_resolves_numbered_sidecar_clone 
tests/test_command_palette_wiring.py::test_extract_command_context_smoke_against_real_app 
[gw4] [ 97%] PASSED tests/agents_sync/test_commit_publication_target_resolution.py::test_resolves_numbered_sidecar_clone 
tests/ace/tui/test_statistics_pane_interactions.py::test_pending_perf_load_cannot_restore_stale_rail 
[gw11] [ 97%] PASSED tests/test_command_palette_wiring.py::test_extract_command_context_smoke_against_real_app 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_artifact_file_viewer_guard_blocks_dead_end_escape_once 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_artifact_file_viewer_guard_blocks_dead_end_escape_once 
tests/artifact_links/test_entry.py::test_aggregates_candidates_from_every_rule 
[gw7] [ 97%] PASSED tests/artifact_links/test_entry.py::test_aggregates_candidates_from_every_rule 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_renders_typed_flag_task_cells 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_rm.py::test_dep_rm_auto_commit_message 
tests/test_bead/test_cli_list_compact.py::test_list_compact_no_color_env_suppresses_escapes 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_linked_file_change_hint_renders_pencil 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_linked_file_change_hint_renders_pencil 
tests/test_comments.py::test_get_comments_file_path 
[gw11] [ 97%] PASSED tests/test_comments.py::test_get_comments_file_path 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_zero_stop_panel_surfaces_artifact_file_viewer_guard 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_zero_stop_panel_surfaces_artifact_file_viewer_guard 
tests/artifact_links/test_entry.py::test_a_document_no_rule_recognizes_contributes_nothing 
[gw7] [ 97%] PASSED tests/artifact_links/test_entry.py::test_a_document_no_rule_recognizes_contributes_nothing 
tests/test_bead/test_cli_dep_rm.py::test_dep_rm_parser_accepts_multiple_targets 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_rm.py::test_dep_rm_parser_accepts_multiple_targets 
tests/ace/tui/test_bead_snooze_modal.py::test_snooze_action_refuses_beads_the_store_would_reject[issue2-Only open, ready, and already snoozed task beads can be snoozed] 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_snooze_action_refuses_beads_the_store_would_reject[issue2-Only open, ready, and already snoozed task beads can be snoozed] 
tests/test_comments.py::test_is_comments_suffix_stale_fresh 
[gw11] [ 97%] PASSED tests/test_comments.py::test_is_comments_suffix_stale_fresh 
tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_zero_stop_panel_selects_adjacent_whole_panel 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_dead_end_panel_navigation.py::test_zero_stop_panel_selects_adjacent_whole_panel 
tests/artifact_links/test_entry.py::test_empty_input_yields_no_candidates 
[gw7] [ 97%] PASSED tests/artifact_links/test_entry.py::test_empty_input_yields_no_candidates 
tests/test_bead/test_cli_dep_rm.py::test_mirror_rebuild_and_fallback_export_do_not_resurrect_removed_edge 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_false_linked_file_change_hint_omits_pencil 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_row_with_false_linked_file_change_hint_omits_pencil 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[error-FAILED-Failed] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[error-FAILED-Failed] 
tests/test_comments.py::test_is_comments_suffix_stale_non_timestamp 
[gw11] [ 97%] PASSED tests/test_comments.py::test_is_comments_suffix_stale_non_timestamp 
tests/ace/tui/test_bead_snooze_modal.py::test_snooze_action_opens_the_picker_for_a_snoozable_task 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_snooze_action_opens_the_picker_for_a_snoozable_task 
tests/artifact_links/test_link_suggest.py::test_suggest_reports_read_log_and_overlapping_read_evidence 
[gw7] [ 97%] PASSED tests/artifact_links/test_link_suggest.py::test_suggest_reports_read_log_and_overlapping_read_evidence 
tests/ace/tui/test_agent_detail_two_phase.py::test_debounced_refresh_runs_immediate_phase_only 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_detail_two_phase.py::test_debounced_refresh_runs_immediate_phase_only 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_center_tabs.py::test_landing_compact_class_tracks_viewport_size 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_no_color_env_suppresses_escapes 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication.py::test_publication_skips_undecodable_foreign_manifest_but_keeps_local_strict 
tests/test_comments.py::test_comment_needs_crs_no_suffix 
[gw11] [ 97%] PASSED tests/test_comments.py::test_comment_needs_crs_no_suffix 
[gw10] [ 97%] PASSED tests/ace/tui/test_xprompt_browser_filter.py::test_no_match_filter_clears_preview_and_stays_safe 
tests/artifact_links/test_link_suggest.py::test_suggest_excludes_existing_related_rows 
[gw7] [ 97%] PASSED tests/artifact_links/test_link_suggest.py::test_suggest_excludes_existing_related_rows 
tests/ace/tui/test_agent_detail_two_phase.py::test_debounced_clan_refresh_defers_multisection_summary 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_detail_two_phase.py::test_debounced_clan_refresh_defers_multisection_summary 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_linked_change_overrides_bookkeeping_primary_diff 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_linked_change_overrides_bookkeeping_primary_diff 
tests/test_bead/test_cli_list_compact.py::test_list_compact_default_auto_is_colorless_under_pytest_capture 
tests/ace/tui/test_config_edit_modal_chezmoi_widget.py::test_chezmoi_write_applies_home_target_not_source 
tests/agents_sync/test_publication.py::test_plan_hoods_refuses_to_republish_from_an_empty_manifest 
tests/ace/tui/test_bead_snooze_modal.py::test_snooze_submission_settles_the_triage_gate_and_commits_a_snooze 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_snooze_submission_settles_the_triage_gate_and_commits_a_snooze 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_rm.py::test_mirror_rebuild_and_fallback_export_do_not_resurrect_removed_edge 
tests/test_comments.py::test_default_zombie_timeout_is_two_hours 
[gw11] [ 97%] PASSED tests/test_comments.py::test_default_zombie_timeout_is_two_hours 
tests/ace/tui/test_xprompt_browser_filter.py::test_empty_catalog_filter_and_list_escape_are_safe 
tests/artifact_links/test_link_suggest.py::test_suggest_reports_filename_lineage_without_writing_the_store 
[gw7] [ 97%] PASSED tests/artifact_links/test_link_suggest.py::test_suggest_reports_filename_lineage_without_writing_the_store 
tests/agents_sync/test_commit_publication_target_resolution.py::test_prefers_primary_on_path_tie 
[gw4] [ 97%] PASSED tests/agents_sync/test_commit_publication_target_resolution.py::test_prefers_primary_on_path_tie 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_default_auto_is_colorless_under_pytest_capture 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[killed-STOPPED-Done] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_maps_proc_statuses[killed-STOPPED-Done] 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_parser_defaults_and_sorted_public_options 
tests/test_comments.py::test_comment_entry_parsing 
[gw11] [ 97%] PASSED tests/test_comments.py::test_comment_entry_parsing 
tests/ace/tui/test_agent_detail_two_phase.py::test_jk_burst_only_full_updates_final_selection 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_detail_two_phase.py::test_jk_burst_only_full_updates_final_selection 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_active_live_hint_wins_over_persisted_classification 
tests/test_bead/test_cli_list_compact.py::test_list_compact_preserves_parent_suffix_and_separator 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_active_live_hint_wins_over_persisted_classification 
tests/artifact_links/test_link_suggest.py::test_handle_link_suggest_json_prints_stable_payload 
[gw7] [ 97%] PASSED tests/artifact_links/test_link_suggest.py::test_handle_link_suggest_json_prints_stable_payload 
[gw3] [ 97%] PASSED tests/ace/tui/test_statistics_pane_interactions.py::test_pending_perf_load_cannot_restore_stale_rail 
tests/ace/tui/test_bead_snooze_modal.py::test_cancel_choice_routes_to_the_wake_mutation 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_cancel_choice_routes_to_the_wake_mutation 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_parser_defaults_and_sorted_public_options 
tests/test_comments.py::test_comment_entry_no_suffix 
[gw11] [ 97%] PASSED tests/test_comments.py::test_comment_entry_no_suffix 
tests/ace/tui/test_statistics_pane_interactions.py::test_failed_perf_load_keeps_the_active_view_rail 
tests/ace/tui/test_agent_detail_two_phase.py::test_collapsed_panel_tribe_uses_cheap_then_debounced_document 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_detail_two_phase.py::test_collapsed_panel_tribe_uses_cheap_then_debounced_document 
tests/artifact_links/test_plan_implements.py::test_implements_a_bead_named_in_frontmatter 
[gw7] [ 97%] PASSED tests/artifact_links/test_plan_implements.py::test_implements_a_bead_named_in_frontmatter 
tests/test_comments.py::test_is_comments_suffix_stale_none 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_renders_linear_chain_and_longest_chain 
[gw11] [ 97%] PASSED tests/test_comments.py::test_is_comments_suffix_stale_none 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_pencil_renders_in_suffix_not_display_name_flow 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_pencil_renders_in_suffix_not_display_name_flow 
tests/ace/tui/test_bead_snooze_modal.py::test_waking_a_bead_commits_a_snooze_cancel_and_leaves_gates_alone 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_waking_a_bead_commits_a_snooze_cancel_and_leaves_gates_alone 
tests/artifact_links/test_plan_implements.py::test_skips_a_plan_with_no_bead_field 
[gw7] [ 97%] PASSED tests/artifact_links/test_plan_implements.py::test_skips_a_plan_with_no_bead_field 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_resolves_explicit_label_provenance 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_projection_resolves_explicit_label_provenance 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_preserves_parent_suffix_and_separator 
tests/ace/tui/test_agent_detail_two_phase.py::test_selected_tribe_navigation_defers_even_the_cheap_document 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_detail_two_phase.py::test_selected_tribe_navigation_defers_even_the_cheap_document 
tests/test_comments.py::test_patch_with_multiple_comments 
[gw11] [ 97%] PASSED tests/test_comments.py::test_patch_with_multiple_comments 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication.py::test_plan_hoods_refuses_to_republish_from_an_empty_manifest 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_renders_linear_chain_and_longest_chain 
tests/test_bead/test_cli_list_compact.py::test_list_compact_created_cell_carries_the_shared_glyph_and_accent 
tests/artifact_links/test_plan_implements.py::test_skips_a_bead_id_that_does_not_resolve 
[gw7] [ 97%] PASSED tests/artifact_links/test_plan_implements.py::test_skips_a_bead_id_that_does_not_resolve 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_running_pencil_immediately_follows_runtime_marker 
tests/test_comments.py::test_comments_entry_with_suffix_parsing 
[gw11] [ 97%] PASSED tests/test_comments.py::test_comments_entry_with_suffix_parsing 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_running_pencil_immediately_follows_runtime_marker 
tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue0-snooze] 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue0-snooze] 
tests/agents_sync/test_publication.py::test_plan_hoods_diagnoses_but_still_publishes_when_manifest_omits_a_hood 
tests/ace/tui/test_agent_detail_two_phase.py::test_debounced_document_waits_for_navigation_gate_to_quiesce 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_detail_two_phase.py::test_debounced_document_waits_for_navigation_gate_to_quiesce 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_marks_diamond_repeat_instead_of_cycle 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_compact.py::test_list_compact_created_cell_carries_the_shared_glyph_and_accent 
[gw10] [ 97%] PASSED tests/ace/tui/test_xprompt_browser_filter.py::test_empty_catalog_filter_and_list_escape_are_safe 
tests/artifact_links/test_plan_implements.py::test_skips_a_blank_bead_field 
[gw7] [ 97%] PASSED tests/artifact_links/test_plan_implements.py::test_skips_a_blank_bead_field 
[gw13] [ 97%] PASSED tests/ace/tui/test_config_center_alternate_tab.py::test_single_section_visited_leaves_opener_inert 
tests/test_comments_handler.py::test_check_comment_zombies_no_comments 
[gw11] [ 97%] PASSED tests/test_comments_handler.py::test_check_comment_zombies_no_comments 
tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_since_keeps_current_beads 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_compacts_preview[  echo   hello  \\\n  echo world\n-\u276f echo hello\u2026] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_compacts_preview[  echo   hello  \\\n  echo world\n-\u276f echo hello\u2026] 
tests/ace/tui/test_xprompt_browser_jump.py::test_apostrophe_enters_jump_mode_with_hints_skipping_headers 
tests/artifact_links/test_plan_implements.py::test_skips_proposing_agent_bead_without_plan_bead_id 
[gw7] [ 97%] PASSED tests/artifact_links/test_plan_implements.py::test_skips_proposing_agent_bead_without_plan_bead_id 
tests/agents_sync/test_commit_publication_target_resolution.py::test_unregistered_repository_without_name_fallback_is_skipped 
[gw4] [ 97%] PASSED tests/agents_sync/test_commit_publication_target_resolution.py::test_unregistered_repository_without_name_fallback_is_skipped 
tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_finished_pencil_immediately_follows_finish_timestamp 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_file_change_pencil.py::TestAgentListFileChangePencil::test_finished_pencil_immediately_follows_finish_timestamp 
tests/ace/tui/test_config_center_alternate_tab.py::test_seeded_alternate_survives_close_and_reopen 
tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue1-snooze] 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue1-snooze] 
tests/test_comments_handler.py::test_check_comment_zombies_multiple_mixed 
[gw11] [ 97%] PASSED tests/test_comments_handler.py::test_check_comment_zombies_multiple_mixed 
tests/ace/tui/test_agent_detail_two_phase.py::test_generation_token_increments_per_phase 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_detail_two_phase.py::test_generation_token_increments_per_phase 
tests/artifact_links/test_plan_implements.py::test_skips_invalid_frontmatter 
[gw7] [ 97%] PASSED tests/artifact_links/test_plan_implements.py::test_skips_invalid_frontmatter 
tests/test_comments_operations.py::test_format_comments_field_empty 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_format_comments_field_empty 
tests/ace/tui/widgets/test_agent_list_grouping.py::test_main_panel_emits_project_and_patch_banners 
tests/ace/tui/test_agent_detail_two_phase.py::test_hint_render_advances_generation_and_rejects_prior_render_context 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_grouping.py::test_main_panel_emits_project_and_patch_banners 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_detail_two_phase.py::test_hint_render_advances_generation_and_rejects_prior_render_context 
tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue2-re-snooze] 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue2-re-snooze] 
[gw3] [ 97%] PASSED tests/ace/tui/test_statistics_pane_interactions.py::test_failed_perf_load_keeps_the_active_view_rail 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_since_keeps_current_beads 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_compacts_preview[\n\nprintf ready\n-\u276f printf ready] 
tests/test_comments_operations.py::test_format_comments_field_plain 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_compacts_preview[\n\nprintf ready\n-\u276f printf ready] 
tests/artifact_links/test_plan_implements.py::test_skips_a_non_plan_ref 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_format_comments_field_plain 
[gw7] [ 97%] PASSED tests/artifact_links/test_plan_implements.py::test_skips_a_non_plan_ref 
tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_until_excludes_current_beads 
tests/ace/tui/test_statistics_pane_interactions.py::test_refresh_and_hidden_tab_keep_the_active_view_rail 
tests/test_comments_operations.py::test_format_comments_field_error_suffix_by_type 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_format_comments_field_error_suffix_by_type 
tests/artifact_links/test_projection_entry.py::test_a_store_with_no_repo_inventory_and_no_agents_root_projects_nothing 
[gw7] [ 97%] PASSED tests/artifact_links/test_projection_entry.py::test_a_store_with_no_repo_inventory_and_no_agents_root_projects_nothing 
tests/ace/tui/test_agent_display_defer_detail.py::test_refresh_list_with_defer_detail_schedules_timer 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_defer_detail.py::test_refresh_list_with_defer_detail_schedules_timer 
tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue3-None] 
tests/ace/tui/widgets/test_agent_list_grouping.py::test_two_agents_with_distinct_projects_get_two_project_banners 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue3-None] 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_grouping.py::test_two_agents_with_distinct_projects_get_two_project_banners 
[gw10] [ 97%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_apostrophe_enters_jump_mode_with_hints_skipping_headers 
tests/test_comments_operations.py::test_format_comments_field_error_suffix_auto_detect 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_format_comments_field_error_suffix_auto_detect 
tests/artifact_links/test_projection_entry.py::test_every_row_is_materialized_with_the_projected_shape 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_marks_diamond_repeat_instead_of_cycle 
[gw7] [ 97%] PASSED tests/artifact_links/test_projection_entry.py::test_every_row_is_materialized_with_the_projected_shape 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_until_excludes_current_beads 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_edit_modal_chezmoi_widget.py::test_chezmoi_write_applies_home_target_not_source 
tests/ace/tui/test_agent_display_defer_detail.py::test_refresh_list_without_defer_updates_detail_immediately 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_defer_detail.py::test_refresh_list_without_defer_updates_detail_immediately 
tests/ace/tui/test_xprompt_browser_jump.py::test_jump_hint_selects_item_and_updates_preview 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_compacts_preview[-None] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_compacts_preview[-None] 
tests/test_comments_operations.py::test_format_comments_field_running_agent_by_type 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_format_comments_field_running_agent_by_type 
tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue4-None] 
[gw1] [ 97%] PASSED tests/ace/tui/test_bead_snooze_modal.py::test_footer_offers_snooze_only_where_the_action_would_work[issue4-None] 
tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_status_all_includes_closed_beads 
tests/ace/tui/widgets/test_agent_list_grouping.py::test_singleton_name_root_emits_no_deepest_banner_in_main_panel 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_grouping.py::test_singleton_name_root_emits_no_deepest_banner_in_main_panel 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_cycle_terminates_and_prints_warning 
tests/ace/tui/test_config_edit_modal_editors_widget.py::test_edit_string_writes_to_target 
tests/artifact_links/test_read_candidates.py::test_aggregates_reads_by_agent_and_ref 
[gw7] [ 97%] PASSED tests/artifact_links/test_read_candidates.py::test_aggregates_reads_by_agent_and_ref 
tests/ace/tui/test_agent_display_defer_detail.py::test_leader_footer_refresh_preserves_plan_notification_binding 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_defer_detail.py::test_leader_footer_refresh_preserves_plan_notification_binding 
tests/test_comments_operations.py::test_format_comments_field_running_agent_auto_detect 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_format_comments_field_running_agent_auto_detect 
tests/agents_sync/test_commit_publication_target_resolution.py::test_project_without_agents_target_is_skipped 
[gw4] [ 97%] PASSED tests/agents_sync/test_commit_publication_target_resolution.py::test_project_without_agents_target_is_skipped 
[gw13] [ 97%] PASSED tests/ace/tui/test_config_center_alternate_tab.py::test_seeded_alternate_survives_close_and_reopen 
tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_clamps_below_min 
[gw1] [ 97%] PASSED tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_clamps_below_min 
tests/test_comments_operations.py::test_format_comments_field_killed_agent 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_format_comments_field_killed_agent 
tests/ace/tui/test_agent_display_defer_detail.py::test_leader_footer_refresh_clears_non_notification_binding 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_defer_detail.py::test_leader_footer_refresh_clears_non_notification_binding 
tests/artifact_links/test_read_candidates.py::test_scoped_to_every_read_not_just_plan_or_research 
[gw7] [ 97%] PASSED tests/artifact_links/test_read_candidates.py::test_scoped_to_every_read_not_just_plan_or_research 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication.py::test_plan_hoods_diagnoses_but_still_publishes_when_manifest_omits_a_hood 
tests/ace/tui/test_config_center_alternate_tab.py::test_custom_opener_drives_alternate_jump_and_is_shown_in_footer 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_compacts_preview[   \n\t-None] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_compacts_preview[   \n\t-None] 
tests/test_comments_operations.py::test_format_comments_field_plain_suffix 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_format_comments_field_plain_suffix 
tests/artifact_links/test_read_candidates.py::test_empty_input_yields_no_candidates 
[gw7] [ 97%] PASSED tests/artifact_links/test_read_candidates.py::test_empty_input_yields_no_candidates 
tests/ace/tui/test_agent_display_defer_detail.py::test_leader_footer_refresh_keeps_unread_and_stopped_flags 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_defer_detail.py::test_leader_footer_refresh_keeps_unread_and_stopped_flags 
tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_clamps_above_max 
[gw1] [ 97%] PASSED tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_clamps_above_max 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_status_all_includes_closed_beads 
tests/agents_sync/test_publication.py::test_plan_hoods_manifest_guard_is_inert_on_a_clean_repository 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_cycle_terminates_and_prints_warning 
tests/test_comments_operations.py::test_format_comments_field_multiple 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_format_comments_field_multiple 
tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_json_total_counts_only_created_window 
tests/artifact_links/test_research_lineage.py::test_derives_from_both_siblings_when_present 
tests/ace/tui/test_agent_display_defer_detail.py::test_footer_refresh_uses_navigation_and_collapse_resolver_capabilities 
[gw7] [ 97%] PASSED tests/artifact_links/test_research_lineage.py::test_derives_from_both_siblings_when_present 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_defer_detail.py::test_footer_refresh_uses_navigation_and_collapse_resolver_capabilities 
tests/test_comments_operations.py::test_apply_comments_insert_new 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_apply_comments_insert_new 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_levels_marks_truncated_remainder 
tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_fits_natural_width 
[gw1] [ 97%] PASSED tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_fits_natural_width 
tests/artifact_links/test_research_lineage.py::test_derives_from_only_the_sibling_that_exists 
[gw7] [ 97%] PASSED tests/artifact_links/test_research_lineage.py::test_derives_from_only_the_sibling_that_exists 
tests/ace/tui/test_agent_display_defer_detail.py::test_footer_refresh_uses_panel_fold_sweep_probe_during_whole_panel_focus 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_defer_detail.py::test_footer_refresh_uses_panel_fold_sweep_probe_during_whole_panel_focus 
tests/test_comments_operations.py::test_apply_comments_replace_existing 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_apply_comments_replace_existing 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_truncates_to_cell_budget 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_command_title_truncates_to_cell_budget 
tests/artifact_links/test_research_lineage.py::test_skips_lead_with_no_siblings_on_disk 
[gw7] [ 97%] PASSED tests/artifact_links/test_research_lineage.py::test_skips_lead_with_no_siblings_on_disk 
tests/ace/tui/widgets/test_agent_list_grouping.py::test_named_agents_share_name_root_banner 
[gw8] [ 97%] PASSED tests/ace/tui/widgets/test_agent_list_grouping.py::test_named_agents_share_name_root_banner 
tests/test_comments_operations.py::test_apply_comments_remove 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_apply_comments_remove 
tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_clamps_to_terminal_when_dashboard_would_be_starved 
[gw1] [ 97%] PASSED tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_clamps_to_terminal_when_dashboard_would_be_starved 
tests/ace/tui/test_agent_display_diff.py::test_workflow_cosmetic_same_position_changes_do_not_touch_tree 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_workflow_cosmetic_same_position_changes_do_not_touch_tree 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_edit_string_writes_to_target 
tests/agents_sync/test_committed_plan_header.py::test_committed_plan_header_refresh_is_idempotent 
[gw4] [ 97%] PASSED tests/agents_sync/test_committed_plan_header.py::test_committed_plan_header_refresh_is_idempotent 
[gw13] [ 97%] PASSED tests/ace/tui/test_config_center_alternate_tab.py::test_custom_opener_drives_alternate_jump_and_is_shown_in_footer 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_json_total_counts_only_created_window 
tests/artifact_links/test_research_lineage.py::test_skips_a_swarm_source_document_even_with_a_sibling_present 
[gw7] [ 97%] PASSED tests/artifact_links/test_research_lineage.py::test_skips_a_swarm_source_document_even_with_a_sibling_present 
tests/test_comments_operations.py::test_apply_comments_wrong_patch 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_apply_comments_wrong_patch 
tests/ace/tui/test_agent_display_diff.py::test_workflow_same_position_structural_change_touches_tree 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_workflow_same_position_structural_change_touches_tree 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_levels_marks_truncated_remainder 
tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_created_bound_lifts_newest_closed_default 
tests/ace/tui/test_config_edit_modal_editors_widget.py::test_edit_back_from_preview_returns_to_edit 
tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_keeps_min_on_tiny_terminal 
[gw1] [ 97%] PASSED tests/ace/tui/test_bgcmd_left_panel_width.py::test_width_event_keeps_min_on_tiny_terminal 
tests/ace/tui/test_statistics_view_number_select.py::test_range_input_keeps_prefix_digit_as_text 
tests/artifact_links/test_research_lineage.py::test_skips_a_non_research_ref 
[gw7] [ 97%] PASSED tests/artifact_links/test_research_lineage.py::test_skips_a_non_research_ref 
tests/test_comments_operations.py::test_apply_comments_end_of_file 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_apply_comments_end_of_file 
tests/ace/tui/test_config_center_alternate_tab.py::test_literal_opener_with_alternate_available_still_types_and_stays_put 
tests/ace/tui/test_agent_display_diff.py::test_added_removed_and_moved_workflow_rows_touch_tree 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_added_removed_and_moved_workflow_rows_touch_tree 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_direction_in_inverts_walk 
tests/artifact_links/test_stitch_rules_projection.py::test_emits_both_bead_and_agent_rows_from_one_commit 
tests/test_comments_operations.py::test_apply_comments_multiple_patches 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_apply_comments_multiple_patches 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_row_renders_explicit_identity_status_and_language 
[gw10] [ 97%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_jump_hint_selects_item_and_updates_preview 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_row_renders_explicit_identity_status_and_language 
[gw7] [ 97%] PASSED tests/artifact_links/test_stitch_rules_projection.py::test_emits_both_bead_and_agent_rows_from_one_commit 
tests/ace/tui/test_bulk_marked_patch_launch.py::test_marked_patch_submit_fans_out_one_launch_per_patch 
[gw1] [ 97%] PASSED tests/ace/tui/test_bulk_marked_patch_launch.py::test_marked_patch_submit_fans_out_one_launch_per_patch 
tests/ace/tui/test_agent_display_diff.py::test_workflow_cosmetic_row_change_patches_without_tree_fallback 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_workflow_cosmetic_row_change_patches_without_tree_fallback 
[gw3] [ 97%] PASSED tests/ace/tui/test_statistics_pane_interactions.py::test_refresh_and_hidden_tab_keep_the_active_view_rail 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication.py::test_plan_hoods_manifest_guard_is_inert_on_a_clean_repository 
tests/test_comments_operations.py::test_mark_agents_killed_basic 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_mark_agents_killed_basic 
tests/ace/tui/test_xprompt_browser_jump.py::test_apostrophe_in_jump_mode_returns_to_previous_item 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_created_bound_lifts_newest_closed_default 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_direction_in_inverts_walk 
tests/artifact_links/test_stitch_rules_projection.py::test_legacy_agent_spelling_is_also_recognized 
tests/ace/tui/test_statistics_pane_interactions.py::test_description_rail_cannot_steal_focus_or_bindings 
[gw7] [ 97%] PASSED tests/artifact_links/test_stitch_rules_projection.py::test_legacy_agent_spelling_is_also_recognized 
tests/ace/tui/test_agent_display_diff.py::test_workflow_structural_row_change_falls_back_to_full_rebuild 
tests/agents_sync/test_publication_outbox.py::test_outbox_is_idempotent_updates_digest_and_acknowledges 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_workflow_structural_row_change_falls_back_to_full_rebuild 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_outbox_is_idempotent_updates_digest_and_acknowledges 
tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_rejects_since_later_than_until 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_filters.py::test_handle_bead_list_rejects_since_later_than_until 
tests/test_comments_operations.py::test_mark_agents_killed_no_match 
tests/ace/tui/test_bulk_marked_patch_launch.py::test_marked_patch_submit_reports_partial_failure 
[gw1] [ 97%] PASSED tests/ace/tui/test_bulk_marked_patch_launch.py::test_marked_patch_submit_reports_partial_failure 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_mark_agents_killed_no_match 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_direction_both_renders_two_trees 
tests/test_bead/test_cli_list_parser.py::test_list_parser_sets_filters_and_limit 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_sets_filters_and_limit 
tests/ace/tui/test_agent_display_diff.py::test_same_position_row_change_patches_without_panel_rebuild 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_same_position_row_change_patches_without_panel_rebuild 
tests/artifact_links/test_stitch_rules_projection.py::test_a_commit_with_no_trailers_contributes_nothing 
tests/agents_sync/test_publication_outbox.py::test_repeated_item_failure_is_quarantined_and_manually_clearable 
[gw7] [ 97%] PASSED tests/artifact_links/test_stitch_rules_projection.py::test_a_commit_with_no_trailers_contributes_nothing 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_repeated_item_failure_is_quarantined_and_manually_clearable 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_edit_back_from_preview_returns_to_edit 
tests/test_comments_operations.py::test_mark_agents_killed_empty 
[gw11] [ 97%] PASSED tests/test_comments_operations.py::test_mark_agents_killed_empty 
tests/agents_sync/test_committed_plan_header.py::test_committed_plan_header_refresh_swallows_failures 
tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_color_choices 
[gw4] [ 97%] PASSED tests/agents_sync/test_committed_plan_header.py::test_committed_plan_header_refresh_swallows_failures 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_color_choices 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_row_renders_derived_command_title 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_row_renders_derived_command_title 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_direction_both_renders_two_trees 
tests/ace/tui/test_bulk_marked_patch_launch.py::test_marked_patch_submit_counts_rejected_durable_proc 
[gw1] [ 97%] PASSED tests/ace/tui/test_bulk_marked_patch_launch.py::test_marked_patch_submit_counts_rejected_durable_proc 
tests/ace/tui/test_agent_display_diff.py::test_row_patch_refreshes_family_lane_panel_title_without_rebuild 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_row_patch_refreshes_family_lane_panel_title_without_rebuild 
[gw13] [ 97%] PASSED tests/ace/tui/test_config_center_alternate_tab.py::test_literal_opener_with_alternate_available_still_types_and_stays_put 
tests/artifact_links/test_stitch_rules_projection.py::test_no_primary_repo_is_a_no_op 
[gw7] [ 97%] PASSED tests/artifact_links/test_stitch_rules_projection.py::test_no_primary_repo_is_a_no_op 
tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_format_aliases[--format] 
tests/test_commit_bead_hooks.py::TestHandleBeads::test_missing_sase_cli_is_non_fatal_and_message_is_unchanged 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_format_aliases[--format] 
tests/ace/tui/test_config_edit_modal_editors_widget.py::test_preview_scroll_keys_move_preview_region 
[gw11] [ 97%] PASSED tests/test_commit_bead_hooks.py::TestHandleBeads::test_missing_sase_cli_is_non_fatal_and_message_is_unchanged 
tests/agents_sync/test_publication_outbox.py::test_repeated_terminal_failure_retires_without_quarantining 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_repeated_terminal_failure_retires_without_quarantining 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_renders_unresolved_target 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_renders_unresolved_target 
tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_format_aliases[-f] 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_format_aliases[-f] 
tests/ace/tui/test_agent_display_diff.py::test_collapsed_last_panel_order_still_allows_incremental_row_patch 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_collapsed_last_panel_order_still_allows_incremental_row_patch 
tests/artifact_links/test_stitch_rules_projection.py::test_idempotent_across_two_warm_runs 
tests/test_commit_bead_hooks.py::TestHandleBeads::test_in_progress_assigned_bead_is_armed_without_a_pre_commit_reminder 
tests/ace/tui/test_config_center_alternate_tab.py::test_failed_alternate_jump_leaves_history_unchanged_and_is_retryable 
[gw11] [ 97%] PASSED tests/test_commit_bead_hooks.py::TestHandleBeads::test_in_progress_assigned_bead_is_armed_without_a_pre_commit_reminder 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_debounced_refresh_50_idx_changes_zero_update_list 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_debounced_refresh_50_idx_changes_zero_update_list 
[gw7] [ 97%] PASSED tests/artifact_links/test_stitch_rules_projection.py::test_idempotent_across_two_warm_runs 
tests/agents_sync/test_publication_outbox.py::test_retry_quarantined_keeps_terminal_retired 
tests/test_bead/test_cli_list_parser.py::test_list_parser_defaults_to_compact_for_explicit_and_bare_list 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_store_wide_forest_selects_top_level_roots 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_defaults_to_compact_for_explicit_and_bare_list 
[gw10] [ 97%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_apostrophe_in_jump_mode_returns_to_previous_item 
tests/ace/tui/test_agent_display_diff.py::test_single_panel_addition_rebuilds_only_affected_panel 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_single_panel_addition_rebuilds_only_affected_panel 
tests/test_commit_bead_hooks.py::TestHandleBeads::test_autoclose_closes_in_progress_assigned_bead_in_primary_repo[task] 
[gw11] [ 97%] PASSED tests/test_commit_bead_hooks.py::TestHandleBeads::test_autoclose_closes_in_progress_assigned_bead_in_primary_repo[task] 
tests/test_bead/test_cli_list_parser.py::test_list_parser_rejects_unknown_format 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_render_key_tracks_derived_title_inputs 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_retry_quarantined_keeps_terminal_retired 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_render_key_tracks_derived_title_inputs 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_rejects_unknown_format 
tests/artifact_links/test_stitch_rules_projection.py::test_incremental_walk_adds_only_the_new_commit 
tests/ace/tui/test_xprompt_browser_jump.py::test_apostrophe_without_history_jumps_to_first_item 
tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_short_limit_and_zero 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_short_limit_and_zero 
tests/test_commit_bead_hooks.py::TestHandleBeads::test_autoclose_closes_in_progress_assigned_bead_in_primary_repo[phase] 
tests/ace/tui/test_agent_display_diff.py::test_single_panel_removal_removes_then_rebuilds_affected_panel 
[gw11] [ 97%] PASSED tests/test_commit_bead_hooks.py::TestHandleBeads::test_autoclose_closes_in_progress_assigned_bead_in_primary_repo[phase] 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_debounced_refresh_does_not_call_clear_options 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_debounced_refresh_does_not_call_clear_options 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_single_panel_removal_removes_then_rebuilds_affected_panel 
tests/agents_sync/test_publication_outbox.py::test_diagnostics_separate_retryable_quarantine_from_retired_requests 
tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_created_date_filters_and_status_all 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_accepts_created_date_filters_and_status_all 
[gw7] [ 97%] PASSED tests/artifact_links/test_stitch_rules_projection.py::test_incremental_walk_adds_only_the_new_commit 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_diagnostics_separate_retryable_quarantine_from_retired_requests 
tests/test_bead/test_cli_list_parser.py::test_list_parser_rejects_malformed_created_date 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_rejects_malformed_created_date 
tests/test_commit_bead_hooks.py::TestHandleBeads::test_autoclose_closes_in_progress_assigned_bead_in_primary_repo[plan] 
[gw11] [ 97%] PASSED tests/test_commit_bead_hooks.py::TestHandleBeads::test_autoclose_closes_in_progress_assigned_bead_in_primary_repo[plan] 
tests/ace/tui/test_agent_display_diff.py::test_tribe_move_between_existing_panels_rebuilds_source_and_target 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_tribe_move_between_existing_panels_rebuilds_source_and_target 
tests/test_bead/test_cli_list_parser.py::test_list_parser_rejects_negative_limit 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_list_parser.py::test_list_parser_rejects_negative_limit 
tests/artifact_links/test_stitch_rules_projection.py::test_unreachable_cached_sha_falls_back_to_a_full_walk 
[gw3] [ 97%] PASSED tests/ace/tui/test_statistics_pane_interactions.py::test_description_rail_cannot_steal_focus_or_bindings 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_store_wide_forest_selects_top_level_roots 
tests/agents_sync/test_publication_outbox.py::test_schema_v1_backlog_is_read_and_upgraded_without_data_loss 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_schema_v1_backlog_is_read_and_upgraded_without_data_loss 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_counts_stay_out_of_agent_lanes 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_counts_stay_out_of_agent_lanes 
tests/test_commit_bead_hooks.py::TestHandleBeads::test_assigned_bead_statuses_other_than_in_progress_are_not_auto_closed[open] 
tests/test_bead/test_cli_memory_asset.py::test_generated_bead_memory_examples_parse_against_cli_contract 
[gw11] [ 97%] PASSED tests/test_commit_bead_hooks.py::TestHandleBeads::test_assigned_bead_statuses_other_than_in_progress_are_not_auto_closed[open] 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_memory_asset.py::test_generated_bead_memory_examples_parse_against_cli_contract 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_detail_only_refresh_skips_update_list 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_detail_only_refresh_skips_update_list 
tests/ace/tui/test_agent_display_diff.py::test_merged_panel_tribe_label_change_rebuilds_panel 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_merged_panel_tribe_label_change_rebuilds_panel 
tests/agents_sync/test_deferred_prompt_archive.py::test_full_sync_publishes_the_prompt_archive_a_busy_lock_deferred 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_preview_scroll_keys_move_preview_region 
tests/test_bead/test_cli_mutation_push.py::test_deferred_push_routes_split_beads_to_beads_sidecar 
[gw7] [ 97%] PASSED tests/artifact_links/test_stitch_rules_projection.py::test_unreachable_cached_sha_falls_back_to_a_full_walk 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_mutation_push.py::test_deferred_push_routes_split_beads_to_beads_sidecar 
tests/agents_sync/test_publication_outbox.py::test_schema_v2_backlog_loads_without_terminal_state_and_upgrades 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_json_node_shape_and_full_provenance 
tests/ace/tui/test_statistics_pane_interactions.py::test_resize_switches_statistics_caption_without_reloading 
tests/test_commit_bead_hooks.py::TestHandleBeads::test_assigned_bead_statuses_other_than_in_progress_are_not_auto_closed[ready] 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_schema_v2_backlog_loads_without_terminal_state_and_upgrades 
[gw11] [ 97%] PASSED tests/test_commit_bead_hooks.py::TestHandleBeads::test_assigned_bead_statuses_other_than_in_progress_are_not_auto_closed[ready] 
tests/test_bead/test_cli_mutation_push.py::test_deferred_push_keeps_separate_repo_target 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_mutation_push.py::test_deferred_push_keeps_separate_repo_target 
tests/ace/tui/test_agent_display_diff.py::test_panel_collection_change_falls_back_to_full_rebuild 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_panel_collection_change_falls_back_to_full_rebuild 
tests/ace/tui/test_config_edit_modal_editors_widget.py::test_bool_toggle_and_write 
tests/artifact_links/test_stitch_rules_projection.py::test_a_git_log_failure_degrades_to_the_cached_rows 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_full_refresh_still_calls_update_list 
tests/test_bead/test_cli_mutation_push.py::test_deferred_push_still_skips_in_tree_store 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_full_refresh_still_calls_update_list 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_mutation_push.py::test_deferred_push_still_skips_in_tree_store 
[gw7] [ 97%] PASSED tests/artifact_links/test_stitch_rules_projection.py::test_a_git_log_failure_degrades_to_the_cached_rows 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_json_node_shape_and_full_provenance 
[gw4] [ 97%] PASSED tests/agents_sync/test_deferred_prompt_archive.py::test_full_sync_publishes_the_prompt_archive_a_busy_lock_deferred 
tests/test_commit_bead_hooks.py::TestHandleBeads::test_assigned_bead_statuses_other_than_in_progress_are_not_auto_closed[claimed] 
[gw11] [ 97%] PASSED tests/test_commit_bead_hooks.py::TestHandleBeads::test_assigned_bead_statuses_other_than_in_progress_are_not_auto_closed[claimed] 
tests/agents_sync/test_publication_outbox.py::test_lock_free_snapshot_reads_schema_v1_without_writing 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_lock_free_snapshot_reads_schema_v1_without_writing 
[gw10] [ 97%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_apostrophe_without_history_jumps_to_first_item 
tests/test_bead/test_cli_mutation_push.py::test_bead_store_mutation_no_push_still_commits 
tests/ace/tui/test_agent_display_diff.py::test_same_list_falls_back_when_previous_rows_were_not_rendered 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_same_list_falls_back_when_previous_rows_were_not_rendered 
[gw8] [ 97%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_range_input_keeps_prefix_digit_as_text 
tests/artifact_providers/test_builtin_entry_agent.py::test_properties_come_from_meta_and_state_json 
[gw7] [ 97%] PASSED tests/artifact_providers/test_builtin_entry_agent.py::test_properties_come_from_meta_and_state_json 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_groups_under_its_selected_project 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_groups_under_its_selected_project 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_output_is_byte_identical_across_runs 
tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[attempts-True] 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[attempts-True] 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_mutation_push.py::test_bead_store_mutation_no_push_still_commits 
tests/test_commit_bead_hooks.py::TestHandleBeads::test_assigned_bead_statuses_other_than_in_progress_are_not_auto_closed[snoozed] 
[gw11] [ 97%] PASSED tests/test_commit_bead_hooks.py::TestHandleBeads::test_assigned_bead_statuses_other_than_in_progress_are_not_auto_closed[snoozed] 
tests/ace/tui/test_xprompt_browser_jump.py::test_escape_cancels_jump_mode_without_closing_modal 
tests/ace/tui/test_agent_display_diff.py::test_standard_clan_status_bucket_change_rebuilds_instead_of_patching 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_standard_clan_status_bucket_change_rebuilds_instead_of_patching 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_full_refresh_tolerates_unmounted_patch_filter_bar 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_full_refresh_tolerates_unmounted_patch_filter_bar 
tests/test_bead/test_cli_mutation_push.py::test_bead_store_mutation_routes_explicit_cwd_to_commit_and_push 
tests/artifact_providers/test_builtin_entry_agent.py::test_missing_meta_and_state_drop_properties_without_failing 
[gw7] [ 97%] PASSED tests/artifact_providers/test_builtin_entry_agent.py::test_missing_meta_and_state_drop_properties_without_failing 
tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[attempts-3] 
tests/ace/tui/test_changespec_jk_navigation.py::test_patch_debounced_refresh_uses_guarded_highlight_api 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[attempts-3] 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespec_jk_navigation.py::test_patch_debounced_refresh_uses_guarded_highlight_api 
tests/ace/tui/test_agent_display_diff.py::test_standard_clan_badge_only_change_patches_in_place 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_standard_clan_badge_only_change_patches_in_place 
tests/artifact_providers/test_builtin_entry_agent.py::test_malformed_meta_json_drops_properties_without_failing 
[gw7] [ 97%] PASSED tests/artifact_providers/test_builtin_entry_agent.py::test_malformed_meta_json_drops_properties_without_failing 
tests/ace/tui/test_statistics_view_number_select.py::test_jump_key_then_digit_selects_view 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_mark_toggle_calls_patch_patch_row_once_no_clear_options 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_mark_toggle_calls_patch_patch_row_once_no_clear_options 
tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_kill_dispatches_native_proc_operation 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_proc_shells.py::test_proc_shell_kill_dispatches_native_proc_operation 
tests/ace/tui/test_changespec_query_corpus_routing.py::test_initial_load_builds_corpus_and_reuses_it_per_query 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespec_query_corpus_routing.py::test_initial_load_builds_corpus_and_reuses_it_per_query 
tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[attempts--1] 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[attempts--1] 
tests/ace/tui/test_agent_display_diff.py::test_by_status_badge_only_change_patches_in_place 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_by_status_badge_only_change_patches_in_place 
tests/artifact_providers/test_builtin_entry_agent.py::test_prompt_expansion_uses_centralized_agent_wording 
[gw7] [ 97%] PASSED tests/artifact_providers/test_builtin_entry_agent.py::test_prompt_expansion_uses_centralized_agent_wording 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_mutation_push.py::test_bead_store_mutation_routes_explicit_cwd_to_commit_and_push 
tests/ace/tui/test_changespec_query_corpus_routing.py::test_reload_replaces_corpus_for_new_list_identity 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespec_query_corpus_routing.py::test_reload_replaces_corpus_for_new_list_identity 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_output_is_byte_identical_across_runs 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_refresh_display_off_tab_does_not_touch_shared_footer 
tests/test_bead/test_cli_mutation_push.py::test_handle_bead_close_no_push_commits_without_push 
tests/ace/tui/test_agent_display_diff.py::test_by_status_status_bucket_move_refuses_row_patch 
tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[quarantined-1] 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_refresh_display_off_tab_does_not_touch_shared_footer 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_by_status_status_bucket_move_refuses_row_patch 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[quarantined-1] 
tests/ace/tui/test_changespec_query_corpus_routing.py::test_repeated_query_hits_evaluation_cache 
tests/agents_sync/test_deferred_prompt_archive.py::test_full_sync_keeps_the_request_queued_when_the_archive_cannot_be_rebuilt 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespec_query_corpus_routing.py::test_repeated_query_hits_evaluation_cache 
tests/artifact_providers/test_builtin_entry_agent.py::test_local_and_global_agent_names_expand_to_canonical_identity 
[gw7] [ 97%] PASSED tests/artifact_providers/test_builtin_entry_agent.py::test_local_and_global_agent_names_expand_to_canonical_identity 
tests/test_bead/test_cli_dep_tree.py::test_dep_tree_rows_end_with_the_bead_created_cell_after_graph_markers 
[gw13] [ 97%] PASSED tests/ace/tui/test_config_center_alternate_tab.py::test_failed_alternate_jump_leaves_history_unchanged_and_is_retryable 
[gw3] [ 97%] PASSED tests/ace/tui/test_statistics_pane_interactions.py::test_resize_switches_statistics_caption_without_reloading 
tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[quarantined-false] 
tests/ace/tui/test_agent_display_diff.py::test_by_status_launch_anchor_change_refuses_row_patch 
tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_is_terminal 
tests/ace/tui/test_changespec_query_corpus_routing.py::test_async_reload_prepares_corpus_inside_worker 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_is_terminal 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespec_query_corpus_routing.py::test_async_reload_prepares_corpus_inside_worker 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_by_status_launch_anchor_change_refuses_row_patch 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_typed_snapshot_rejects_malformed_consumed_fields[quarantined-false] 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_refresh_display_off_tab_empty_list_does_not_touch_footer 
tests/artifact_providers/test_builtin_entry_agent.py::test_unresolvable_agent_has_no_entry 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_refresh_display_off_tab_empty_list_does_not_touch_footer 
[gw7] [ 97%] PASSED tests/artifact_providers/test_builtin_entry_agent.py::test_unresolvable_agent_has_no_entry 
[gw10] [ 97%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_escape_cancels_jump_mode_without_closing_modal 
tests/ace/tui/test_config_center_alternate_tab.py::test_footer_hidden_on_home_and_reflects_alternate_once_a_tab_is_active 
tests/ace/tui/test_changespec_query_corpus_routing.py::test_hide_counts_are_preserved_on_corpus_route 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespec_query_corpus_routing.py::test_hide_counts_are_preserved_on_corpus_route 
tests/agents_sync/test_publication_outbox.py::test_schema_v2_snapshot_requires_quarantine_state 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_mutation_push.py::test_handle_bead_close_no_push_commits_without_push 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_schema_v2_snapshot_requires_quarantine_state 
[gw4] [ 97%] PASSED tests/agents_sync/test_deferred_prompt_archive.py::test_full_sync_keeps_the_request_queued_when_the_archive_cannot_be_rebuilt 
tests/ace/tui/test_agent_display_diff.py::test_stale_widget_grouping_mode_falls_back_to_full_rebuild 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_display_diff.py::test_stale_widget_grouping_mode_falls_back_to_full_rebuild 
tests/ace/tui/test_xprompt_browser_jump.py::test_apostrophe_with_typed_filter_is_ordinary_text 
tests/artifact_providers/test_builtin_entry_bead.py::test_full_id_defers_to_rust_resolver 
[gw7] [ 97%] PASSED tests/artifact_providers/test_builtin_entry_bead.py::test_full_id_defers_to_rust_resolver 
tests/test_bead/test_cli_mutation_push.py::test_handle_bead_close_legacy_namespace_still_pushes 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_detail_only_refresh_off_tab_does_not_touch_shared_footer 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_detail_only_refresh_off_tab_does_not_touch_shared_footer 
tests/ace/tui/test_changespec_query_corpus_routing.py::test_forced_stale_handle_fails_before_returning_results 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespec_query_corpus_routing.py::test_forced_stale_handle_fails_before_returning_results 
tests/agents_sync/test_publication_outbox.py::test_schema_v3_agent_request_loads_with_same_logical_key 
tests/ace/tui/test_agent_durable_producers.py::test_directive_argv_payload_and_key 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_schema_v3_agent_request_loads_with_same_logical_key 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_durable_producers.py::test_directive_argv_payload_and_key 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[pre_prompt] 
tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_groups_as_done_not_failed 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[pre_prompt] 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_groups_as_done_not_failed 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_dep_tree.py::test_dep_tree_rows_end_with_the_bead_created_cell_after_graph_markers 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_requires_loaded_filtered_empty 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_requires_loaded_filtered_empty 
tests/ace/tui/test_changespec_detail_only_refresh.py::test_mark_toggle_falls_back_to_full_refresh_on_patch_failure 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_detail_only_refresh.py::test_mark_toggle_falls_back_to_full_refresh_on_patch_failure 
tests/agents_sync/test_publication_outbox.py::test_schema_v4_drops_non_agent_requests_with_a_visible_diagnostic 
tests/ace/tui/test_agent_durable_producers.py::test_tribe_uses_shared_store_key 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_durable_producers.py::test_tribe_uses_shared_store_key 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_schema_v4_drops_non_agent_requests_with_a_visible_diagnostic 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_bool_toggle_and_write 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_mutation_push.py::test_handle_bead_close_legacy_namespace_still_pushes 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[parallel] 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[parallel] 
tests/test_bead/test_cli_detail_index.py::test_issue_detail_index_resolves_relationships_and_parent_plan 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_hides_before_first_load 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_hides_before_first_load 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_detail_index.py::test_issue_detail_index_resolves_relationships_and_parent_plan 
tests/test_bead/test_cli_mutation_push.py::test_handle_bead_update_multi_id_commits_once_and_pushes_once 
tests/agents_sync/test_publication_outbox.py::test_two_workers_enqueue_without_lost_or_duplicate_requests 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[embedded] 
tests/ace/tui/test_config_edit_modal_editors_widget.py::test_enum_navigation_digits_and_space 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[embedded] 
tests/ace/tui/test_agent_durable_producers.py::test_independent_artifacts_dirs_do_not_collide 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_durable_producers.py::test_independent_artifacts_dirs_do_not_collide 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_ignores_saved_queries 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_ignores_saved_queries 
tests/ace/tui/test_changespec_graph_index.py::test_index_builds_children_status_and_terminal_counts 
tests/test_bead/test_cli_detail_index.py::test_resolve_issue_detail_consumes_single_read_snapshot 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_outbox.py::test_two_workers_enqueue_without_lost_or_duplicate_requests 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_graph_index.py::test_index_builds_children_status_and_terminal_counts 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_detail_index.py::test_resolve_issue_detail_consumes_single_read_snapshot 
tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_is_dismissable 
[gw13] [ 97%] PASSED tests/ace/tui/test_config_center_alternate_tab.py::test_footer_hidden_on_home_and_reflects_alternate_once_a_tab_is_active 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_is_dismissable 
tests/ace/tui/test_statistics_pane_loading.py::test_statistics_loads_only_after_its_tab_becomes_active 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[compatibility] 
tests/ace/tui/test_agent_durable_producers.py::test_launch_and_cleanup_argv 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_durable_producers.py::test_launch_and_cleanup_argv 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[compatibility] 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_hides_when_filtered_specs_exist 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_hides_when_filtered_specs_exist 
tests/agents_sync/test_publication_repair.py::test_repair_resigns_drifted_payload_and_publication_recovers 
tests/test_bead/test_cli_doctor.py::test_doctor_parser_accepts_fix_aliases_and_documents_help 
tests/agents_sync/test_git_sync.py::test_default_sync_lock_timeout_waits_briefly 
[gw4] [ 97%] PASSED tests/agents_sync/test_git_sync.py::test_default_sync_lock_timeout_waits_briefly 
tests/ace/tui/test_config_center_alternate_tab.py::test_footer_click_navigates_to_the_alternate_section 
[gw8] [ 97%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_jump_key_then_digit_selects_view 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_doctor.py::test_doctor_parser_accepts_fix_aliases_and_documents_help 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_uses_filtered_patches 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_predicate_uses_filtered_patches 
tests/ace/tui/test_agent_durable_producers.py::test_stale_callback_skips_rollback 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_durable_producers.py::test_stale_callback_skips_rollback 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_keeps_duplicate_owner_rejection 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_keeps_duplicate_owner_rejection 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_mutation_push.py::test_handle_bead_update_multi_id_commits_once_and_pushes_once 
tests/ace/tui/test_changespec_graph_index.py::test_index_groups_siblings_by_base_name 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_graph_index.py::test_index_groups_siblings_by_base_name 
tests/test_bead/test_cli_doctor.py::test_doctor_parser_accepts_projection_repair_and_yes_aliases 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_visible_after_empty_startup 
tests/test_bead/test_cli_mutation_push.py::test_close_parser_accepts_no_push_short_and_long_options 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_repair.py::test_repair_resigns_drifted_payload_and_publication_recovers 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_family_member_then_top_level_family_selects_tribe 
tests/ace/tui/test_agent_durable_producers.py::test_revert_execute_carries_preview_in_request 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_durable_producers.py::test_revert_execute_carries_preview_in_request 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_family_member_then_top_level_family_selects_tribe 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_mutation_push.py::test_close_parser_accepts_no_push_short_and_long_options 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_doctor.py::test_doctor_parser_accepts_projection_repair_and_yes_aliases 
tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_is_not_resumable 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_is_not_resumable 
tests/test_bead/test_cli_note.py::test_note_parser_contract 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_note.py::test_note_parser_contract 
tests/ace/tui/test_statistics_view_number_select.py::test_jump_key_non_digit_cancels_prefix_and_continues_to_modal[q] 
tests/agents_sync/test_publication_repair.py::test_repair_is_idempotent_on_healthy_sidecar 
tests/ace/tui/test_agent_fold_persistence.py::test_load_race_installs_baseline_then_replays_newer_user_intent 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_load_race_installs_baseline_then_replays_newer_user_intent 
tests/ace/tui/test_changespec_graph_index.py::test_update_relationships_from_index_avoids_per_row_rebuilds 
tests/test_bead/test_cli_doctor.py::test_doctor_parser_accepts_fix_issue_prefix_alias_and_documents_help 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_graph_index.py::test_update_relationships_from_index_avoids_per_row_rebuilds 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_doctor.py::test_doctor_parser_accepts_fix_issue_prefix_alias_and_documents_help 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[agent] 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[agent] 
tests/test_bead/test_cli_note.py::test_note_parser_accepts_edit_and_remove_flags 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_note.py::test_note_parser_accepts_edit_and_remove_flags 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_repair.py::test_repair_is_idempotent_on_healthy_sidecar 
tests/ace/tui/test_agent_fold_persistence.py::test_collapse_then_expand_journal_persists_group_result 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_collapse_then_expand_journal_persists_group_result 
tests/test_bead/test_cli_doctor.py::test_doctor_warns_about_leaked_key_prefix 
tests/test_bead/test_cli_note.py::test_note_parser_rejects_edit_and_remove_together 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_note.py::test_note_parser_rejects_edit_and_remove_together 
[gw6] [ 97%] PASSED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_enum_navigation_digits_and_space 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[bash] 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[bash] 
tests/agents_sync/test_publication_repair.py::test_repair_after_applying_a_fix_is_a_noop 
tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_is_not_revertable 
[gw0] [ 97%] PASSED tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_is_not_revertable 
tests/ace/tui/test_changespec_grouped_navigation.py::test_navigation_stops_skip_expanded_banners 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_navigation_stops_skip_expanded_banners 
tests/test_bead/test_cli_note.py::test_note_appends_to_empty_notes_with_explicit_author 
tests/ace/tui/test_agent_fold_persistence.py::test_panel_expansion_helper_wins_when_persisted_load_is_still_in_flight 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_panel_expansion_helper_wins_when_persisted_load_is_still_in_flight 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_doctor.py::test_doctor_warns_about_leaked_key_prefix 
tests/ace/tui/test_config_edit_modal_editors_widget.py::test_bool_digit_picks_visible_option 
[gw11] [ 97%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_visible_after_empty_startup 
[gw12] [ 97%] PASSED tests/agents_sync/test_publication_repair.py::test_repair_after_applying_a_fix_is_a_noop 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[python] 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[python] 
[gw2] [ 97%] PASSED tests/test_bead/test_cli_note.py::test_note_appends_to_empty_notes_with_explicit_author 
tests/test_bead/test_cli_doctor.py::test_doctor_omits_prefix_warning_for_correctly_prefixed_store 
tests/ace/tui/test_agent_fold_persistence.py::test_panel_intent_recorded_before_late_load_survives_install 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_panel_intent_recorded_before_late_load_survives_install 
[gw13] [ 97%] PASSED tests/ace/tui/test_config_center_alternate_tab.py::test_footer_click_navigates_to_the_alternate_section 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_mounts_single_quickstart_panel 
tests/agents_sync/test_publication_repair.py::test_repair_never_touches_a_foreign_owners_snapshot 
tests/ace/tui/test_changespec_grouped_navigation.py::test_navigation_stops_include_collapsed_banner 
[gw1] [ 97%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_navigation_stops_include_collapsed_banner 
tests/test_bead/test_cli_note.py::test_note_appends_to_existing_notes_and_history_shows_revisions 
tests/agents_sync/test_git_sync.py::test_full_sync_reuses_one_name_registry_load_session_for_publication 
[gw4] [ 97%] PASSED tests/agents_sync/test_git_sync.py::test_full_sync_reuses_one_name_registry_load_session_for_publication 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[pre_prompt] 
[gw3] [ 97%] PASSED tests/ace/tui/test_statistics_pane_loading.py::test_statistics_loads_only_after_its_tab_becomes_active 
[gw7] [ 97%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[pre_prompt] 
[gw9] [ 97%] PASSED tests/test_bead/test_cli_doctor.py::test_doctor_omits_prefix_warning_for_correctly_prefixed_store 
tests/ace/tui/test_agent_fold_persistence.py::test_partial_projection_preserves_panel_intent_and_prunes_stale_groups 
[gw5] [ 97%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_partial_projection_preserves_panel_intent_and_prunes_stale_groups 
tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_visual_identity_constants 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_status_stopped.py::test_stopped_visual_identity_constants 
[gw10] [ 98%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_apostrophe_with_typed_filter_is_ordinary_text 
tests/ace/tui/test_config_center_alternate_tab.py::test_persisted_file_contains_both_lines_in_order 
[gw12] [ 98%] PASSED tests/agents_sync/test_publication_repair.py::test_repair_never_touches_a_foreign_owners_snapshot 
tests/test_bead/test_cli_doctor.py::test_fix_issue_prefix_rewrites_config_and_preserves_existing_ids 
[gw8] [ 98%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_jump_key_non_digit_cancels_prefix_and_continues_to_modal[q] 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_appends_to_existing_notes_and_history_shows_revisions 
tests/ace/tui/test_statistics_pane_loading.py::test_stale_project_filter_result_is_discarded_and_rescheduled 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_loading.py::test_stale_project_filter_result_is_discarded_and_rescheduled 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[parallel] 
tests/ace/tui/test_changespec_grouped_navigation.py::test_navigate_steps_through_collapsed_banner_then_cl 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[parallel] 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_navigate_steps_through_collapsed_banner_then_cl 
tests/ace/tui/test_agent_fold_persistence.py::test_legacy_panel_state_is_ignored_at_startup_and_config_applies 
tests/ace/tui/test_xprompt_browser_jump.py::test_opened_filter_types_leading_apostrophe_instead_of_jumping 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_legacy_panel_state_is_ignored_at_startup_and_config_applies 
tests/test_bead/test_cli_note.py::test_note_rejects_blank_entry_without_writing_or_committing 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_fix_issue_prefix_rewrites_config_and_preserves_existing_ids 
tests/agents_sync/test_publication_repair.py::test_repair_manifest_restores_entries_for_intact_on_disk_hoods 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[embedded] 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_rejects_blank_entry_without_writing_or_committing 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[embedded] 
tests/ace/tui/test_statistics_pane_loading.py::test_stale_xprompt_focus_result_is_discarded_and_rescheduled 
[gw12] [ 98%] PASSED tests/agents_sync/test_publication_repair.py::test_repair_manifest_restores_entries_for_intact_on_disk_hoods 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_loading.py::test_stale_xprompt_focus_result_is_discarded_and_rescheduled 
tests/ace/tui/test_agent_fold_persistence.py::test_late_load_uses_in_memory_full_rebuild_refresh 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_late_load_uses_in_memory_full_rebuild_refresh 
tests/test_bead/test_cli_doctor.py::test_fix_issue_prefix_with_nothing_to_repair 
tests/test_bead/test_cli_note.py::test_note_defaults_author_from_agent_identity 
[gw6] [ 98%] PASSED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_bool_digit_picks_visible_option 
tests/ace/tui/test_changespec_grouped_navigation.py::test_navigate_banner_to_cl_triggers_refresh_even_when_idx_unchanged 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_navigate_banner_to_cl_triggers_refresh_even_when_idx_unchanged 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_count_each_standalone_agent 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_count_each_standalone_agent 
tests/ace/tui/test_statistics_view_number_select.py::test_jump_key_non_digit_cancels_prefix_and_continues_to_modal[escape] 
tests/ace/tui/test_statistics_pane_loading.py::test_stale_perf_group_result_is_discarded_and_rescheduled 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_fix_issue_prefix_with_nothing_to_repair 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_loading.py::test_stale_perf_group_result_is_discarded_and_rescheduled 
[gw11] [ 98%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_mounts_single_quickstart_panel 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[compatibility] 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_standalone_workflow_steps_navigate_to_workflow_owner[compatibility] 
tests/agents_sync/test_publication_repair.py::test_repair_manifest_skips_and_reports_a_hood_with_a_pruned_run_file 
tests/ace/tui/test_agent_fold_persistence.py::test_fold_state_install_disarms_panel_isolation_restore 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_fold_state_install_disarms_panel_isolation_restore 
tests/ace/tui/test_config_edit_modal_editors_widget.py::test_scalar_input_selects_all_on_open 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_defaults_author_from_agent_identity 
tests/test_bead/test_cli_note.py::test_note_defaults_author_from_store_owner_without_agent_identity 
[gw12] [ 98%] PASSED tests/agents_sync/test_publication_repair.py::test_repair_manifest_skips_and_reports_a_hood_with_a_pruned_run_file 
tests/test_bead/test_cli_doctor.py::test_plain_doctor_forwards_roots_without_planning_or_writing 
tests/ace/tui/test_statistics_pane_loading.py::test_refresh_preserves_selection_and_hidden_tick_is_inert 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_visible_when_saved_queries_exist 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_plain_doctor_forwards_roots_without_planning_or_writing 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_clan_workflow_step_walks_workflow_clan_tribe_one_level_at_a_time 
tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_focused_cl_group_snaps_to_banner 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_focused_cl_group_snaps_to_banner 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_clan_workflow_step_walks_workflow_clan_tribe_one_level_at_a_time 
tests/ace/tui/test_agent_fold_persistence.py::test_group_folds_survive_a_fresh_session_but_panel_intent_does_not 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_group_folds_survive_a_fresh_session_but_panel_intent_does_not 
tests/agents_sync/test_git_sync.py::test_full_sync_transaction_commits_and_pushes_only_payload 
tests/agents_sync/test_publication_repair.py::test_repair_manifest_is_a_noop_when_already_complete 
tests/test_bead/test_cli_doctor.py::test_doctor_root_discovery_degrades_to_explicit_unavailable 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_keep_sequential_family_as_one_lane 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_workflow_step_jump_history_restores_exact_script_row 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_doctor_root_discovery_degrades_to_explicit_unavailable 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_keep_sequential_family_as_one_lane 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_workflow_step_jump_history_restores_exact_script_row 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_alternate_tab.py::test_persisted_file_contains_both_lines_in_order 
tests/ace/tui/test_agent_fold_persistence.py::test_rapid_mutations_coalesce_to_latest_generation 
tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_focused_banner_collapses_it 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_defaults_author_from_store_owner_without_agent_identity 
[gw10] [ 98%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_opened_filter_types_leading_apostrophe_instead_of_jumping 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_rapid_mutations_coalesce_to_latest_generation 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_focused_banner_collapses_it 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_nested_monitor_navigates_to_starter 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_nested_monitor_navigates_to_starter 
tests/test_bead/test_cli_doctor.py::test_fix_preview_cancellation_never_opens_mutation 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_fix_preview_cancellation_never_opens_mutation 
tests/ace/tui/test_config_center_history.py::test_remember_on_empty_history_seeds_current_with_no_alternate 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_remember_on_empty_history_seeds_current_with_no_alternate 
tests/test_bead/test_cli_note.py::test_note_single_token_at_path_expands 
[gw12] [ 98%] PASSED tests/agents_sync/test_publication_repair.py::test_repair_manifest_is_a_noop_when_already_complete 
[gw4] [ 98%] PASSED tests/agents_sync/test_git_sync.py::test_full_sync_transaction_commits_and_pushes_only_payload 
tests/ace/tui/test_xprompt_browser_jump.py::test_filtering_after_a_jump_clears_the_stale_back_stack 
tests/ace/tui/test_agent_fold_persistence.py::test_flush_waits_for_latest_queued_generation 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_persistence.py::test_flush_waits_for_latest_queued_generation 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_l_on_family_container_reveals_monitor_nested_under_mid_family_starter 
tests/ace/tui/test_config_center_history.py::test_remember_with_a_different_tab_shifts_current_into_alternate 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_l_on_family_container_reveals_monitor_nested_under_mid_family_starter 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_remember_with_a_different_tab_shifts_current_into_alternate 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_single_token_at_path_expands 
tests/agents_sync/test_publication_repair.py::test_repair_manifest_never_reads_a_foreign_owners_path_family 
tests/test_bead/test_cli_doctor.py::test_confirmed_fix_uses_update_events_and_one_aggregate_commit 
[gw6] [ 98%] PASSED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_scalar_input_selects_all_on_open 
tests/ace/tui/test_changespec_grouped_navigation.py::test_expand_collapsed_banner_reanchors_focus_to_first_cl 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_expand_collapsed_banner_reanchors_focus_to_first_cl 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_count_clan_direct_members_without_family_descendants 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_count_clan_direct_members_without_family_descendants 
tests/test_bead/test_cli_note.py::test_note_multi_token_text_still_joins_with_spaces 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_collapses_selected_clan_then_siblings_then_status_group 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_collapses_selected_clan_then_siblings_then_status_group 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_l_on_selected_monitor_targets_family_fold_not_starter 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_l_on_selected_monitor_targets_family_fold_not_starter 
tests/ace/tui/test_config_center_history.py::test_remember_with_the_same_tab_returns_the_identical_object 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_remember_with_the_same_tab_returns_the_identical_object 
tests/ace/tui/test_config_edit_modal_editors_widget.py::test_multiline_string_uses_textarea 
tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_all_collapses_visible_l0_banners 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_collapses_sibling_clan_when_selected_clan_is_already_closed 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_all_collapses_visible_l0_banners 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_collapses_sibling_clan_when_selected_clan_is_already_closed 
tests/ace/tui/test_config_center_history.py::test_three_way_sequence_keeps_only_the_two_most_recent_sections 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_three_way_sequence_keeps_only_the_two_most_recent_sections 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_capital_h_on_selected_monitor_collapses_family_and_reanchors 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_capital_h_on_selected_monitor_collapses_family_and_reanchors 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_confirmed_fix_uses_update_events_and_one_aggregate_commit 
[gw12] [ 98%] PASSED tests/agents_sync/test_publication_repair.py::test_repair_manifest_never_reads_a_foreign_owners_path_family 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_collapses_selected_open_clan_container_without_reanchor 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_collapses_selected_open_clan_container_without_reanchor 
tests/ace/tui/test_config_center_history.py::test_toggle_sequence_ping_pongs_between_exactly_two_sections 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_dedupe_stable_identities_across_clans_and_panels 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_dedupe_stable_identities_across_clans_and_panels 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_direct_clan_member_navigates_to_clan_then_tribe 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_multi_token_text_still_joins_with_spaces 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_toggle_sequence_ping_pongs_between_exactly_two_sections 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_direct_clan_member_navigates_to_clan_then_tribe 
tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_all_collapses_only_deepest_visible_cl_group_level 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_all_collapses_only_deepest_visible_cl_group_level 
tests/test_bead/test_cli_doctor.py::test_stale_preview_performs_no_updates_or_commit 
tests/test_bead/test_cli_note.py::test_handle_bead_note_auto_commit_message 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_stale_preview_performs_no_updates_or_commit 
tests/agents_sync/test_publication_repair_git.py::test_repair_commits_and_pushes_a_resigned_snapshot 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_rejects_stale_ambiguous_and_self_referential_parent_edges 
[gw8] [ 98%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_jump_key_non_digit_cancels_prefix_and_continues_to_modal[escape] 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_rejects_stale_ambiguous_and_self_referential_parent_edges 
tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence0] 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence0] 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_single_open_selected_clan_preserves_group_wide_end_state 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_single_open_selected_clan_preserves_group_wide_end_state 
tests/test_bead/test_cli_doctor.py::test_confirmation_requires_interactive_yes 
tests/agents_sync/test_git_sync.py::test_full_sync_recovers_dirty_payload_before_pull 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_confirmation_requires_interactive_yes 
[gw11] [ 98%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_visible_when_saved_queries_exist 
tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_all_collapses_next_deepest_cl_group_level 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_collapse_all_collapses_next_deepest_cl_group_level 
tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence1] 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence1] 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_rejects_cycles_and_inconsistent_tree_depth 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_rejects_cycles_and_inconsistent_tree_depth 
[gw10] [ 98%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_filtering_after_a_jump_clears_the_stale_back_stack 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agent_statuses_dedupe_terminal_owner_and_unread_state 
tests/test_bead/test_cli_doctor.py::test_fix_projection_repairs_expected_drift_and_second_run_is_noop 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_narrows_deep_descendant_to_enclosing_clan 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agent_statuses_dedupe_terminal_owner_and_unread_state 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_narrows_deep_descendant_to_enclosing_clan 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_hidden_when_patches_exist 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_rejects_conflicting_explicit_and_persisted_parent_keys 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_rejects_conflicting_explicit_and_persisted_parent_keys 
tests/ace/tui/test_statistics_view_number_select.py::test_repeated_jump_key_cancels_armed_selection 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_loading.py::test_refresh_preserves_selection_and_hidden_tick_is_inert 
tests/ace/tui/test_xprompt_browser_jump.py::test_zero_items_apostrophe_is_a_silent_no_op 
tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence2] 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence2] 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_handle_bead_note_auto_commit_message 
tests/ace/tui/test_changespec_grouped_navigation.py::test_expand_all_peels_one_level_off_visible_collapsed_banners 
tests/test_bead/test_cli_note.py::test_note_edit_rewrites_text_and_preserves_original_authorship 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_expand_all_peels_one_level_off_visible_collapsed_banners 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_closes_lanes_then_all_group_clans_then_group 
tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_row_h_closes_lanes_then_all_group_clans_then_group 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_rejects_orphan_script_and_duplicate_top_level_owner 
tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence3] 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence3] 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_rejects_orphan_script_and_duplicate_top_level_owner 
[gw4] [ 98%] PASSED tests/agents_sync/test_git_sync.py::test_full_sync_recovers_dirty_payload_before_pull 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_group_clan_scope_isolates_status_panel_and_merged_layout 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_grouping_banner_selects_tribe_and_selected_panel_has_no_parent 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_keep_legacy_parallel_family_as_one_lane 
tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence4] 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_group_clan_scope_isolates_status_panel_and_merged_layout 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agents_keep_legacy_parallel_family_as_one_lane 
[gw12] [ 98%] PASSED tests/agents_sync/test_publication_repair_git.py::test_repair_commits_and_pushes_a_resigned_snapshot 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_alternate_never_equals_current_for_any_reachable_sequence[sequence4] 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_grouping_banner_selects_tribe_and_selected_panel_has_no_parent 
tests/ace/tui/test_changespec_grouped_navigation.py::test_jump_targets_include_collapsed_banner_in_render_order 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_jump_targets_include_collapsed_banner_in_render_order 
[gw11] [ 98%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_hidden_when_patches_exist 
tests/ace/tui/test_config_center_history.py::test_validated_history_drops_an_alternate_equal_to_current 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_validated_history_drops_an_alternate_equal_to_current 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_selected_clan_narrowing_isolates_sibling_groups_and_panels 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_top_level_selects_single_split_tribe_but_not_merged_layout 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_selected_clan_narrowing_isolates_sibling_groups_and_panels 
tests/agents_sync/test_publication_repair_git.py::test_repair_is_a_noop_when_nothing_has_drifted 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_top_level_selects_single_split_tribe_but_not_merged_layout 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_fix_projection_repairs_expected_drift_and_second_run_is_noop 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_visible_when_specs_are_filtered_out 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_edit_rewrites_text_and_preserves_original_authorship 
[gw6] [ 98%] PASSED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_multiline_string_uses_textarea 
tests/ace/tui/test_config_center_history.py::test_validated_history_keeps_a_distinct_alternate 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_history.py::test_validated_history_keeps_a_distinct_alternate 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_group_clan_scope_isolates_date_and_project_groups 
tests/ace/tui/test_agent_fold_transitions_tools.py::test_tools_panel_h_navigates_while_capital_h_compacts_detail 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tools.py::test_tools_panel_h_navigates_while_capital_h_compacts_detail 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_group_clan_scope_isolates_date_and_project_groups 
[gw8] [ 98%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_repeated_jump_key_cancels_armed_selection 
tests/test_bead/test_cli_note.py::test_note_edit_rejects_out_of_range_ordinal_without_writing 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agent_screenshot_cardinality_is_31_for_56_concrete_agents 
tests/ace/tui/test_changespec_grouped_navigation.py::test_banner_focus_valid_when_group_still_present 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_banner_focus_valid_when_group_still_present 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_sase_agent_screenshot_cardinality_is_31_for_56_concrete_agents 
tests/test_bead/test_cli_doctor.py::test_fix_projection_refuses_row_set_drift 
tests/ace/tui/test_config_edit_modal_editors_widget.py::test_yaml_textarea_uses_yaml_language 
tests/ace/tui/test_config_center_navigation.py::test_repeated_first_navigation_is_idempotent 
tests/ace/tui/test_agent_fold_transitions_tools.py::test_tools_panel_detail_clamp_does_not_fall_through_to_folds 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tools.py::test_tools_panel_detail_clamp_does_not_fall_through_to_folds 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_group_clan_collapse_reanchors_direct_member_once_without_persistence 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_navigation.py::test_repeated_first_navigation_is_idempotent 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_group_clan_collapse_reanchors_direct_member_once_without_persistence 
[gw12] [ 98%] PASSED tests/agents_sync/test_publication_repair_git.py::test_repair_is_a_noop_when_nothing_has_drifted 
tests/ace/tui/test_changespec_grouped_navigation.py::test_banner_focus_invalid_when_group_filtered_out 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_banner_focus_invalid_when_group_filtered_out 
tests/ace/tui/test_agent_fold_transitions_tools.py::test_capital_l_still_expands_all_folds_on_axe_but_not_patches 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tools.py::test_capital_l_still_expands_all_folds_on_axe_but_not_patches 
tests/ace/tui/test_statistics_view_number_select.py::test_range_input_keeps_jump_key_as_text 
tests/ace/tui/test_config_center_navigation.py::test_activation_callback_observes_committed_success_and_not_refocus 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_collapsed_child_banner_scopes_clan_step_to_open_parent 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_collapsed_child_banner_scopes_clan_step_to_open_parent 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_navigation.py::test_activation_callback_observes_committed_success_and_not_refocus 
tests/agents_sync/test_purge_local_state.py::test_dry_run_reports_full_closure_without_mutation 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_edit_rejects_out_of_range_ordinal_without_writing 
tests/agents_sync/test_git_sync.py::test_full_sync_clears_stale_index_lock_before_recovery 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_fix_projection_refuses_row_set_drift 
[gw12] [ 98%] PASSED tests/agents_sync/test_purge_local_state.py::test_dry_run_reports_full_closure_without_mutation 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_family_then_clan_before_group_fold 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_family_then_clan_before_group_fold 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_finished_multi_member_family_is_one_done_lane 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_finished_multi_member_family_is_one_done_lane 
tests/test_bead/test_cli_note.py::test_note_edit_requires_text 
[gw11] [ 98%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_visible_when_specs_are_filtered_out 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_standalone_lane_falls_through_to_group_wide_clan_sweep 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_standalone_lane_falls_through_to_group_wide_clan_sweep 
tests/ace/tui/test_changespec_grouped_navigation.py::test_banner_focus_valid_when_unset 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_banner_focus_valid_when_unset 
tests/ace/tui/test_config_center_navigation.py::test_activation_callback_is_silent_for_construction_and_mount_failures 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_aliased_plan_family_before_group_fold 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_aliased_plan_family_before_group_fold 
tests/test_bead/test_cli_doctor.py::test_projection_repair_guard_refuses_unexpected_shapes[fields0-current_updates0-reduced_updates0-changes unexpected field(s): status] 
tests/agents_sync/test_purge_local_state.py::test_apply_removes_full_closure_and_leaves_local_state_untouched 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_projection_repair_guard_refuses_unexpected_shapes[fields0-current_updates0-reduced_updates0-changes unexpected field(s): status] 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_hides_after_first_patch_arrives 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_navigation.py::test_activation_callback_is_silent_for_construction_and_mount_failures 
tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_malformed_and_duplicate_clans_fail_closed_per_candidate 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_group_clans.py::test_malformed_and_duplicate_clans_fail_closed_per_candidate 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_workflow_step_owner_before_group[agent] 
tests/test_bead/test_cli_doctor.py::test_projection_repair_guard_refuses_unexpected_shapes[fields1-current_updates1-reduced_updates1-changes unexpected field(s): title] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_projection_repair_guard_refuses_unexpected_shapes[fields1-current_updates1-reduced_updates1-changes unexpected field(s): title] 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_workflow_step_owner_before_group[agent] 
[gw12] [ 98%] PASSED tests/agents_sync/test_purge_local_state.py::test_apply_removes_full_closure_and_leaves_local_state_untouched 
tests/ace/tui/test_config_center_navigation.py::test_activation_callback_is_silent_for_switch_failure 
[gw6] [ 98%] PASSED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_yaml_textarea_uses_yaml_language 
tests/ace/tui/test_changespec_grouped_navigation.py::test_jk_in_grouped_mode_walks_collapsed_banner_stops 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_jk_in_grouped_mode_walks_collapsed_banner_stops 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_capital_h_on_agent_collapses_only_its_group 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_nested_starting_lane_rolls_up_to_running 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_nested_starting_lane_rolls_up_to_running 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_capital_h_on_agent_collapses_only_its_group 
[gw10] [ 98%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_zero_items_apostrophe_is_a_silent_no_op 
[gw4] [ 98%] PASSED tests/agents_sync/test_git_sync.py::test_full_sync_clears_stale_index_lock_before_recovery 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_workflow_step_owner_before_group[bash] 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_workflow_step_owner_before_group[bash] 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_navigation.py::test_activation_callback_is_silent_for_switch_failure 
tests/test_bead/test_cli_doctor.py::test_projection_repair_guard_refuses_unexpected_shapes[fields2-current_updates2-reduced_updates2-moves closed_at later] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_doctor.py::test_projection_repair_guard_refuses_unexpected_shapes[fields2-current_updates2-reduced_updates2-moves closed_at later] 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_edit_requires_text 
tests/agents_sync/test_purge_local_state.py::test_no_imported_state_reports_empty_closure 
[gw8] [ 98%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_range_input_keeps_jump_key_as_text 
[gw12] [ 98%] PASSED tests/agents_sync/test_purge_local_state.py::test_no_imported_state_reports_empty_closure 
tests/ace/tui/test_config_edit_modal_layout_widget.py::test_large_yaml_value_keeps_editor_and_hints_visible 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_capital_h_inside_l1_collapses_l1_then_parent_l0 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_capital_h_inside_l1_collapses_l1_then_parent_l0 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_workflow_step_owner_before_group[python] 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_workflow_step_owner_before_group[python] 
tests/test_bead/test_cli_note.py::test_note_remove_retracts_the_record_and_history_keeps_it 
tests/test_bead/test_cli_epic_symbols.py::test_epic_symbols_parser_accepts_optional_id_and_format 
tests/ace/tui/test_xprompt_browser_jump.py::test_jump_works_when_the_row_list_owns_focus 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_epic_symbols.py::test_epic_symbols_parser_accepts_optional_id_and_format 
tests/ace/tui/test_config_center_navigation.py::test_activation_callback_failure_does_not_fail_navigation 
tests/ace/tui/test_changespec_grouped_navigation.py::test_hooks_or_collapse_routes_to_cl_grouped_collapse 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouped_navigation.py::test_hooks_or_collapse_routes_to_cl_grouped_collapse 
tests/agents_sync/test_purge_local_state.py::test_unwritable_artifact_reported_without_aborting_sweep 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_navigation.py::test_activation_callback_failure_does_not_fail_navigation 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_l_on_collapsed_l1_banner_expands_only_that_l1 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_l_on_collapsed_l1_banner_expands_only_that_l1 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_workflow_step_owner_before_group[pre_prompt] 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_collapses_workflow_step_owner_before_group[pre_prompt] 
tests/test_bead/test_cli_epic_symbols.py::test_fast_path_defers_epic_symbols_to_argparse 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_epic_symbols.py::test_fast_path_defers_epic_symbols_to_argparse 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_family_container_projects_members_and_settled_statuses 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_family_container_projects_members_and_settled_statuses 
[gw12] [ 98%] PASSED tests/agents_sync/test_purge_local_state.py::test_unwritable_artifact_reported_without_aborting_sweep 
tests/ace/tui/test_config_center_navigation.py::test_construction_failure_keeps_home_and_allows_retry 
tests/ace/tui/test_statistics_view_number_select.py::test_configured_prefix_arms_the_same_number_selection 
tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_advances_by_project_to_by_date 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_l_expands_agent_fold_without_artifact_pane_focus 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_advances_by_project_to_by_date 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_l_expands_agent_fold_without_artifact_pane_focus 
[gw11] [ 98%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_hides_after_first_patch_arrives 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_l_expands_child_owner_but_saturated_hidden_leaf_is_noop 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_l_expands_child_owner_but_saturated_hidden_leaf_is_noop 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_navigation.py::test_construction_failure_keeps_home_and_allows_retry 
tests/test_bead/test_cli_epic_symbols.py::test_epic_symbols_lists_only_the_requested_bead_tree 
tests/agents_sync/test_referenced_by_outbox.py::test_referenced_by_outbox_is_idempotent_updates_and_acknowledges 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_reappears_after_last_patch_disappears 
[gw12] [ 98%] PASSED tests/agents_sync/test_referenced_by_outbox.py::test_referenced_by_outbox_is_idempotent_updates_and_acknowledges 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_remove_retracts_the_record_and_history_keeps_it 
tests/ace/tui/test_config_center_navigation.py::test_mount_failure_keeps_home_and_allows_retry 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_capital_h_then_l_round_trip_clears_group_focus 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_capital_h_then_l_round_trip_clears_group_focus 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_l_expands_running_parent_with_family_child 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_l_expands_running_parent_with_family_child 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive 
tests/test_bead/test_cli_note.py::test_note_remove_rejects_out_of_range_ordinal_without_writing 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_navigation.py::test_mount_failure_keeps_home_and_allows_retry 
tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_advances_by_date_to_by_status 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_advances_by_date_to_by_status 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_summary_counts_use_custom_agent_status_bucket 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_summary_counts_use_custom_agent_status_bucket 
tests/agents_sync/test_referenced_by_outbox.py::test_referenced_by_quarantine_retry_and_terminal_drop 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_clan_l_is_a_binary_outer_fold_and_second_l_is_clamped 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_clan_l_is_a_binary_outer_fold_and_second_l_is_clamped 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_epic_symbols.py::test_epic_symbols_lists_only_the_requested_bead_tree 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_equal_status_group_keys_fold_independently_between_panels 
tests/ace/tui/test_statistics_pane_loading.py::test_loader_queries_current_activity_and_previous_equal_window 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_equal_status_group_keys_fold_independently_between_panels 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_loading.py::test_loader_queries_current_activity_and_previous_equal_window 
[gw12] [ 98%] PASSED tests/agents_sync/test_referenced_by_outbox.py::test_referenced_by_quarantine_retry_and_terminal_drop 
tests/agents_sync/test_git_sync.py::test_full_sync_failure_after_payload_write_restores_clean_tree 
tests/ace/tui/test_config_center_priority_tab.py::test_tab_switches_when_the_active_pane_does_not_consume_it 
[gw6] [ 98%] PASSED tests/ace/tui/test_config_edit_modal_layout_widget.py::test_large_yaml_value_keeps_editor_and_hints_visible 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_remove_rejects_out_of_range_ordinal_without_writing 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_priority_tab.py::test_tab_switches_when_the_active_pane_does_not_consume_it 
tests/test_bead/test_cli_epic_symbols.py::test_epic_symbols_json_includes_empty_result_for_unrelated_bead 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_clan_member_l_l_and_child_member_capital_h_are_isolated 
tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_wraps_back_to_by_project 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_wraps_back_to_by_project 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_clan_member_l_l_and_child_member_capital_h_are_isolated 
[gw10] [ 98%] PASSED tests/ace/tui/test_xprompt_browser_jump.py::test_jump_works_when_the_row_list_owns_focus 
tests/test_bead/test_cli_note.py::test_note_remove_forbids_text 
tests/ace/tui/test_statistics_pane_rendering.py::test_renderers_use_projected_labels_and_canonical_project_colors 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_capital_h_collapses_every_open_lane_before_status_group 
[gw4] [ 98%] PASSED tests/agents_sync/test_git_sync.py::test_full_sync_failure_after_payload_write_restores_clean_tree 
tests/agents_sync/test_referenced_by_planning.py::test_plan_referenced_by_requests_for_document_sidecar_refs 
tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_capital_h_collapses_every_open_lane_before_status_group 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_renderers_use_projected_labels_and_canonical_project_colors 
[gw12] [ 98%] PASSED tests/agents_sync/test_referenced_by_planning.py::test_plan_referenced_by_requests_for_document_sidecar_refs 
tests/ace/tui/test_config_center_priority_tab.py::test_tab_is_swallowed_when_the_active_pane_consumes_it 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_epic_symbols.py::test_epic_symbols_json_includes_empty_result_for_unrelated_bead 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_planner_only_approved_family_stays_running 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_xprompt_edit_and_forward_handlers_are_synchronous 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_planner_only_approved_family_stays_running 
[gw10] [ 98%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_xprompt_edit_and_forward_handlers_are_synchronous 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_collapsed_clan_masks_member_state_until_reopened 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_collapsed_clan_masks_member_state_until_reopened 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_note_remove_forbids_text 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_priority_tab.py::test_tab_is_swallowed_when_the_active_pane_consumes_it 
tests/agents_sync/test_referenced_by_planning.py::test_prose_referenced_by_requests_for_an_exact_path_match 
tests/ace/tui/test_changespec_grouping_cycle.py::test_three_cycles_returns_to_by_project 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_lane_collapse_saturates_remaining_open_lanes_when_selected_is_closed 
tests/ace/tui/test_statistics_pane_rendering.py::test_overview_bucket_panel_discloses_grouping_only_when_aggregated 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_three_cycles_returns_to_by_project 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_lane_collapse_saturates_remaining_open_lanes_when_selected_is_closed 
[gw12] [ 98%] PASSED tests/agents_sync/test_referenced_by_planning.py::test_prose_referenced_by_requests_for_an_exact_path_match 
tests/test_bead/test_cli_note.py::test_handle_bead_note_edit_and_remove_auto_commit_messages 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_overview_bucket_panel_discloses_grouping_only_when_aggregated 
tests/test_bead/test_cli_epic_symbols.py::test_epic_symbols_reports_empty_working_tree 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_xprompts_session_restores_row_by_name_around_headers 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_per_workflow_capital_h_runs_before_group_collapse 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_per_workflow_capital_h_runs_before_group_collapse 
tests/ace/tui/test_config_center_priority_tab.py::test_panes_without_the_hook_are_unaffected 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_epic_symbols.py::test_epic_symbols_reports_empty_working_tree 
tests/agents_sync/test_referenced_by_planning.py::test_prose_referenced_by_requests_skips_a_near_miss 
tests/ace/tui/test_statistics_pane_rendering.py::test_all_project_plan_and_question_values_need_no_scope_markers 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_collapsed_child_banner_scopes_lane_step_to_its_open_parent 
[gw12] [ 98%] PASSED tests/agents_sync/test_referenced_by_planning.py::test_prose_referenced_by_requests_skips_a_near_miss 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_all_project_plan_and_question_values_need_no_scope_markers 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_collapsed_child_banner_scopes_lane_step_to_its_open_parent 
tests/ace/tui/test_changespec_grouping_cycle.py::test_fold_state_preserved_after_cycle_round_trip 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_fold_state_preserved_after_cycle_round_trip 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_note.py::test_handle_bead_note_edit_and_remove_auto_commit_messages 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_retreats_loader_family_hidden_step_one_level 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_retreats_loader_family_hidden_step_one_level 
tests/ace/tui/test_statistics_pane_rendering.py::test_project_filtered_plan_and_question_values_need_no_scope_markers 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_project_filtered_plan_and_question_values_need_no_scope_markers 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[init] 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_lane_collapse_isolated_by_panel_and_merged_layout 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_lane_collapse_isolated_by_panel_and_merged_layout 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_clan_projection_recurses_into_sequential_family 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_clan_projection_recurses_into_sequential_family 
tests/test_bead/test_cli_open.py::test_open_parser_sets_bead_subcommand_and_id 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[init] 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_open.py::test_open_parser_sets_bead_subcommand_and_id 
tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_retreats_standalone_workflow_hidden_step_one_level 
tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_grouping_modes_render_distinctive_columns_and_rows[usage-distinctive_copy0] 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_tree.py::test_capital_h_retreats_standalone_workflow_hidden_step_one_level 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_grouping_modes_render_distinctive_columns_and_rows[usage-distinctive_copy0] 
tests/test_bead/test_cli_open.py::test_handle_bead_open_reopens_issue 
tests/ace/tui/test_changespec_grouping_cycle.py::test_per_mode_registry_dict_grows_lazily 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_per_mode_registry_dict_grows_lazily 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_malformed_lane_fails_closed_while_valid_sibling_collapses 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_malformed_lane_fails_closed_while_valid_sibling_collapses 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[create] 
tests/ace/tui/test_agent_group_focus.py::test_focused_group_is_panel_scoped_and_remapped_to_global_indices 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_group_focus.py::test_focused_group_is_panel_scoped_and_remapped_to_global_indices 
tests/agents_sync/test_git_sync.py::test_payload_commit_force_stages_user_ignored_hood 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_open.py::test_handle_bead_open_reopens_issue 
tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_grouping_modes_render_distinctive_columns_and_rows[model-distinctive_copy1] 
tests/ace/tui/test_agent_fold_transitions_groups.py::test_duplicate_lane_owner_is_not_mutated_as_a_bulk_candidate 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_groups.py::test_duplicate_lane_owner_is_not_mutated_as_a_bulk_candidate 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_grouping_modes_render_distinctive_columns_and_rows[model-distinctive_copy1] 
[gw8] [ 98%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_configured_prefix_arms_the_same_number_selection 
[gw10] [ 98%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_xprompts_session_restores_row_by_name_around_headers 
[gw4] [ 98%] PASSED tests/agents_sync/test_git_sync.py::test_payload_commit_force_stages_user_ignored_hood 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[create] 
tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_clears_current_patch_group_key 
tests/test_bead/test_cli_open.py::test_handle_bead_open_missing_id_exits_with_update_style_error 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_clears_current_patch_group_key 
tests/ace/tui/test_agent_group_focus.py::test_focused_group_uses_selected_tribe_panel 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_group_focus.py::test_focused_group_uses_selected_tribe_panel 
tests/agents_sync/test_rendering.py::test_renderer_escapes_markdown_tables_and_contains_no_volatile_text 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering.py::test_renderer_escapes_markdown_tables_and_contains_no_volatile_text 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_clan_counts_settle_handed_off_family_planner_as_done 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_clan_counts_settle_handed_off_family_planner_as_done 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_enter_returns_while_xprompt_file_read_is_blocked 
tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_grouping_modes_render_distinctive_columns_and_rows[project-distinctive_copy2] 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_grouping_modes_render_distinctive_columns_and_rows[project-distinctive_copy2] 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_walks_member_family_clan_tribe_without_changing_folds 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_open.py::test_handle_bead_open_missing_id_exits_with_update_style_error 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_walks_member_family_clan_tribe_without_changing_folds 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list] 
tests/test_bead/test_cli_open.py::test_handle_bead_open_reopens_closed_ancestors 
tests/agents_sync/test_rendering.py::test_agent_and_family_pages_render_relative_breadcrumbs 
[gw11] [ 98%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_reappears_after_last_patch_disappears 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering.py::test_agent_and_family_pages_render_relative_breadcrumbs 
tests/ace/tui/test_agent_group_focus.py::test_focused_group_merged_panels_includes_all_rendered_agents 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_group_focus.py::test_focused_group_merged_panels_includes_all_rendered_agents 
tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_on_axe_tab_is_silent_noop 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_on_axe_tab_is_silent_noop 
tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_grouping_modes_render_distinctive_columns_and_rows[pairing-distinctive_copy3] 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_grouping_modes_render_distinctive_columns_and_rows[pairing-distinctive_copy3] 
tests/ace/tui/test_statistics_xprompt_picker_modal.py::test_picker_filters_cached_rows_highlights_focus_and_selects 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_parent_navigation_preserves_selection_bookkeeping_and_history 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_parent_navigation_preserves_selection_bookkeeping_and_history 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_full] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_full] 
tests/agents_sync/test_rendering.py::test_agent_and_family_neighbor_links_resolve_inside_payload 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_open.py::test_handle_bead_open_reopens_closed_ancestors 
tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_ignores_saved_query_cache_invalidates 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering.py::test_agent_and_family_neighbor_links_resolve_inside_payload 
tests/ace/tui/test_agent_group_focus.py::test_focused_group_stale_key_returns_none 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_group_focus.py::test_focused_group_stale_key_returns_none 
tests/ace/tui/test_statistics_pane_rendering.py::test_swarm_rows_and_focus_header_label_the_swarm_kind 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_swarm_rows_and_focus_header_label_the_swarm_kind 
tests/test_bead/test_cli_pages.py::test_pages_parser_defaults_to_dry_run_and_bare_group_prints_help 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_parent_ladder_is_grouping_mode_independent 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_parent_ladder_is_grouping_mode_independent 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_pages.py::test_pages_parser_defaults_to_dry_run_and_bare_group_prints_help 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_json] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_json] 
tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_on_agents_tab_does_not_touch_cl_state 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_on_agents_tab_does_not_touch_cl_state 
tests/agents_sync/test_rendering.py::test_agent_and_family_pages_render_sorted_escaped_and_truncated_variables 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering.py::test_agent_and_family_pages_render_sorted_escaped_and_truncated_variables 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_clan_counts_settle_answered_family_planner_as_done 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_clan_counts_settle_answered_family_planner_as_done 
tests/test_bead/test_cli_pages.py::test_refresh_json_is_machine_readable 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_pages.py::test_refresh_json_is_machine_readable 
tests/ace/tui/test_statistics_pane_rendering.py::test_plans_questions_render_feedback_and_coverage_floor 
tests/ace/tui/test_agent_group_focus.py::test_focused_group_without_panel_group_uses_rendered_full_list 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_plans_questions_render_feedback_and_coverage_floor 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_group_focus.py::test_focused_group_without_panel_group_uses_rendered_full_list 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_priority_tab.py::test_panes_without_the_hook_are_unaffected 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_reaches_root_and_sole_default_panel 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_reaches_root_and_sole_default_panel 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_json_limit] 
tests/test_bead/test_cli_pages.py::test_url_prints_resolved_hosted_page 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_json_limit] 
tests/agents_sync/test_rendering_bead_links.py::test_agent_page_renders_bead_then_epic_bullets_above_model 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_bead_links.py::test_agent_page_renders_bead_then_epic_bullets_above_model 
tests/ace/tui/test_statistics_pane_rendering.py::test_xprompt_focus_header_labels_the_swarm_kind 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_xprompt_focus_header_labels_the_swarm_kind 
tests/ace/tui/test_agent_group_kill.py::test_action_kill_routes_to_group_when_banner_focused 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_group_kill.py::test_action_kill_routes_to_group_when_banner_focused 
tests/ace/tui/test_config_center_resume.py::test_repeated_opener_without_history_keeps_one_zero_pane_home 
tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_on_cls_tab_does_not_touch_agents_state 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_on_cls_tab_does_not_touch_agents_state 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_pages.py::test_url_prints_resolved_hosted_page 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[agent] 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[agent] 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_limit] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_limit] 
tests/agents_sync/test_git_sync.py::test_non_fast_forward_recomputes_and_retries_push_once 
tests/agents_sync/test_rendering_bead_links.py::test_agent_page_unlinked_bead_renders_plain_escaped_text 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_bead_links.py::test_agent_page_unlinked_bead_renders_plain_escaped_text 
tests/ace/tui/test_statistics_pane_rendering.py::test_commits_tile_shows_distinct_agents_and_committing_runs 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_commits_tile_shows_distinct_agents_and_committing_runs 
tests/test_bead/test_cli_plus_one.py::test_plus_one_parser_requires_evidence_and_accepts_all_public_options 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_parser_requires_evidence_and_accepts_all_public_options 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[bash] 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[bash] 
tests/agents_sync/test_rendering_bead_links.py::test_run_absent_from_bead_links_mapping_renders_unchanged 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_bead_links.py::test_run_absent_from_bead_links_mapping_renders_unchanged 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_limit_zero] 
[gw11] [ 98%] PASSED tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_ignores_saved_query_cache_invalidates 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_limit_zero] 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_container_unread_is_attributed_once_to_projected_member 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_container_unread_is_attributed_once_to_projected_member 
tests/test_bead/test_cli_plus_one.py::test_plus_one_parser_accepts_verified_after_close_flag 
tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_schedules_patch_grouping_mode_save 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_schedules_patch_grouping_mode_save 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_parser_accepts_verified_after_close_flag 
tests/ace/tui/test_agent_group_kill.py::test_action_kill_on_clan_container_cascades_to_real_members 
tests/ace/tui/test_statistics_pane_rendering.py::test_projects_by_project_uses_patches_header_and_spec_footnote 
[gw7] [ 98%] PASSED tests/ace/tui/test_agent_group_kill.py::test_action_kill_on_clan_container_cascades_to_real_members 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_projects_by_project_uses_patches_header_and_spec_footnote 
[gw4] [ 98%] PASSED tests/agents_sync/test_git_sync.py::test_non_fast_forward_recomputes_and_retries_push_once 
[gw8] [ 98%] PASSED tests/ace/tui/test_statistics_xprompt_picker_modal.py::test_picker_filters_cached_rows_highlights_focus_and_selects 
tests/test_bead/test_cli_plus_one.py::test_plus_one_verified_after_close_reopens_and_clears_assignee 
tests/agents_sync/test_rendering_bead_links.py::test_family_page_header_renders_single_distinct_bead 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_bead_links.py::test_family_page_header_renders_single_distinct_bead 
tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[python] 
[gw5] [ 98%] PASSED tests/ace/tui/test_agent_fold_transitions_navigation.py::test_h_loader_aliased_plan_family_accepts_every_workflow_step_kind[python] 
tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_accepts_nested_string 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_accepts_nested_string 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed] 
tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_drilldown_discloses_per_row_truncation 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_drilldown_discloses_per_row_truncation 
tests/ace/tui/test_config_hub_pane.py::test_legacy_xprompts_resume_opens_config_hub_on_default_subtab 
tests/agents_sync/test_rendering_bead_links.py::test_family_page_header_caps_distinct_beads_and_reports_remainder 
tests/ace/tui/test_changespec_grouping_cycle.py::test_rapid_patch_cycles_save_latest_mode 
tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_accepts_nested_string 
tests/agents_sync/test_links.py::test_commit_tag_links_from_sidecar_checkout 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_full] 
tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_legend_splits_share_denominators 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_accepts_nested_string 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_bead_links.py::test_family_page_header_caps_distinct_beads_and_reports_remainder 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_rapid_patch_cycles_save_latest_mode 
[gw5] [ 98%] PASSED tests/agents_sync/test_links.py::test_commit_tag_links_from_sidecar_checkout 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_legend_splits_share_denominators 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_full] 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_resume.py::test_repeated_opener_without_history_keeps_one_zero_pane_home 
[gw7] [ 98%] PASSED tests/ace/tui/test_config_hub_pane.py::test_legacy_xprompts_resume_opens_config_hub_on_default_subtab 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_queue_counts_are_orthogonal_and_dedupe_container_flat_rows 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_queue_counts_are_orthogonal_and_dedupe_container_flat_rows 
tests/ace/tui/test_statistics_xprompt_picker_modal.py::test_picker_cancel_is_distinct_from_all_xprompts 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_verified_after_close_reopens_and_clears_assignee 
tests/agents_sync/test_rendering_bead_links.py::test_bead_linked_agent_page_golden 
tests/ace/tui/test_commits_config.py::test_commits_default_query_is_exposed_in_config_inventory 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_bead_links.py::test_bead_linked_agent_page_golden 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_json] 
tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_truncation_is_explicit 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_truncation_is_explicit 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_json] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_commits_default_query_is_exposed_in_config_inventory 
tests/agents_sync/test_links.py::test_commit_tag_links_from_linked_repo_checkout 
[gw5] [ 98%] PASSED tests/agents_sync/test_links.py::test_commit_tag_links_from_linked_repo_checkout 
tests/test_bead/test_cli_plus_one.py::test_plus_one_verified_after_close_rejects_non_closed_bead 
tests/ace/tui/test_config_hub_pane.py::test_remembered_subtab_shows_matching_caption 
tests/ace/tui/test_config_center_resume.py::test_direct_initial_tab_mounts_only_that_target 
tests/agents_sync/test_rendering_commits.py::test_commit_tables_link_escape_and_format_utc 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_commits.py::test_commit_tables_link_escape_and_format_utc 
tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_unavailable_and_no_reference_states_use_effective_keys 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_resume.py::test_direct_initial_tab_mounts_only_that_target 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_rendering.py::test_xprompts_unavailable_and_no_reference_states_use_effective_keys 
tests/ace/tui/test_commits_config.py::test_stitches_default_query_is_exposed_in_config_inventory 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_limit] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_stitches_default_query_is_exposed_in_config_inventory 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_limit] 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_verified_after_close_rejects_non_closed_bead 
tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_emits_cl_grouping_toast 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_emits_cl_grouping_toast 
tests/agents_sync/test_links.py::test_commit_tag_degrades_when_checkout_project_is_unresolvable 
[gw5] [ 98%] PASSED tests/agents_sync/test_links.py::test_commit_tag_degrades_when_checkout_project_is_unresolvable 
tests/test_bead/test_cli_plus_one.py::test_plus_one_withheld_reopen_reports_and_leaves_bead_closed 
[gw10] [ 98%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_enter_returns_while_xprompt_file_read_is_blocked 
tests/agents_sync/test_rendering_commits.py::test_family_page_unions_lane_commits_with_member_attribution_winning 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_commits.py::test_family_page_unions_lane_commits_with_member_attribution_winning 
tests/ace/tui/test_statistics_pane_view_navigation.py::test_numbered_eight_view_strip_fits_each_statistics_layout_tier[130-full] 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_view_navigation.py::test_numbered_eight_view_strip_fits_each_statistics_layout_tier[130-full] 
tests/ace/tui/test_config_center_resume.py::test_generic_reopen_is_home_first_then_repeated_opener_resumes 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_filters] 
tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_rejects_wrong_types[False] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_rejects_wrong_types[False] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_filters] 
tests/ace/tui/models/test_agent_summary_status_counts.py::test_queued_waiters_partition_waiting_counts 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_summary_status_counts.py::test_queued_waiters_partition_waiting_counts 
tests/agents_sync/test_rendering_commits.py::test_unrecognized_remote_keeps_commits_unlinked[ssh://git@example.invalid/x/y.git-None] 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_commits.py::test_unrecognized_remote_keeps_commits_unlinked[ssh://git@example.invalid/x/y.git-None] 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_withheld_reopen_reports_and_leaves_bead_closed 
tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_rejects_wrong_types[24] 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_status_closed_default_limit] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_rejects_wrong_types[24] 
tests/agents_sync/test_prompt_archive.py::test_prepare_prompt_archive_links_and_copies_all_reference_classes 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_status_closed_default_limit] 
tests/ace/tui/test_statistics_pane_view_navigation.py::test_numbered_eight_view_strip_fits_each_statistics_layout_tier[120-compact] 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_view_navigation.py::test_numbered_eight_view_strip_fits_each_statistics_layout_tier[120-compact] 
tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_advances_by_project_to_by_status 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_advances_by_project_to_by_status 
[gw5] [ 98%] PASSED tests/agents_sync/test_prompt_archive.py::test_prepare_prompt_archive_links_and_copies_all_reference_classes 
tests/agents_sync/test_git_sync.py::test_bounded_lock_contention_is_a_benign_skip 
tests/test_bead/test_cli_plus_one.py::test_plus_one_malformed_agent_metadata_falls_back_and_reopens 
tests/agents_sync/test_rendering_commits.py::test_unrecognized_remote_keeps_commits_unlinked[ssh://git@example.invalid/x/y.git-gitlab] 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_commits.py::test_unrecognized_remote_keeps_commits_unlinked[ssh://git@example.invalid/x/y.git-gitlab] 
[gw8] [ 98%] PASSED tests/ace/tui/test_statistics_xprompt_picker_modal.py::test_picker_cancel_is_distinct_from_all_xprompts 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_status_closed_unlimited] 
[gw4] [ 98%] PASSED tests/agents_sync/test_git_sync.py::test_bounded_lock_contention_is_a_benign_skip 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_ctrl_i_loads_non_yaml_xprompt_into_prompt_bar 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_status_closed_unlimited] 
tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_rejects_wrong_types[value2] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_rejects_wrong_types[value2] 
tests/ace/tui/test_statistics_pane_view_navigation.py::test_numbered_eight_view_strip_fits_each_statistics_layout_tier[90-compact] 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_view_navigation.py::test_numbered_eight_view_strip_fits_each_statistics_layout_tier[90-compact] 
tests/agents_sync/test_prompt_archive.py::test_render_prompt_document_keeps_body_xprompt_reference_verbatim 
tests/ace/tui/models/test_agent_tree.py::test_project_clan_tree_inserts_container_and_three_depths 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_tree.py::test_project_clan_tree_inserts_container_and_three_depths 
tests/agents_sync/test_rendering_commits.py::test_commit_rendering_is_bounded_and_validates_link_shas 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_commits.py::test_commit_rendering_is_bounded_and_validates_link_shas 
tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_advances_by_status_to_by_date 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_advances_by_status_to_by_date 
[gw7] [ 98%] PASSED tests/ace/tui/test_config_hub_pane.py::test_remembered_subtab_shows_matching_caption 
[gw5] [ 98%] PASSED tests/agents_sync/test_prompt_archive.py::test_render_prompt_document_keeps_body_xprompt_reference_verbatim 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_mixed_status_closed_default_limit] 
tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_rejects_wrong_types[value3] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_mixed_status_closed_default_limit] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_commits_default_query_schema_rejects_wrong_types[value3] 
tests/ace/tui/test_statistics_pane_view_navigation.py::test_numbered_eight_view_strip_fits_each_statistics_layout_tier[70-micro] 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_view_navigation.py::test_numbered_eight_view_strip_fits_each_statistics_layout_tier[70-micro] 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_malformed_agent_metadata_falls_back_and_reopens 
tests/agents_sync/test_rendering_kinship.py::test_projection_orders_ancestors_descendants_and_hood_groups 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_kinship.py::test_projection_orders_ancestors_descendants_and_hood_groups 
tests/ace/tui/test_statistics_xprompt_picker_modal.py::test_picker_rows_share_the_statistics_kind_labels 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_default_limit] 
tests/ace/tui/test_config_hub_pane.py::test_resize_switches_caption_variant_without_reloading_children 
tests/agents_sync/test_prompt_archive.py::test_artifact_target_resolver_handles_pinned_and_builtin_destinations 
[gw8] [ 98%] PASSED tests/ace/tui/test_statistics_xprompt_picker_modal.py::test_picker_rows_share_the_statistics_kind_labels 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_default_limit] 
[gw5] [ 98%] PASSED tests/agents_sync/test_prompt_archive.py::test_artifact_target_resolver_handles_pinned_and_builtin_destinations 
tests/ace/tui/test_statistics_pane_view_navigation.py::test_view_cycle_reuses_composite_result_and_updates_strip 
tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_rejects_wrong_types[False] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_rejects_wrong_types[False] 
tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_wraps_back_to_by_project 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_wraps_back_to_by_project 
tests/agents_sync/test_rendering_kinship.py::test_family_is_one_lane_and_never_lists_its_members 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_kinship.py::test_family_is_one_lane_and_never_lists_its_members 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_explicit_open_no_fallback] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_explicit_open_no_fallback] 
tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_rejects_wrong_types[24] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_rejects_wrong_types[24] 
[gw6] [ 98%] PASSED tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states 
tests/agents_sync/test_rendering_kinship.py::test_lone_lane_has_no_neighbor_groups 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_kinship.py::test_lone_lane_has_no_neighbor_groups 
tests/ace/tui/models/test_agent_tree.py::test_presentation_anchor_handles_orphans_and_cycles_deterministically 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_tree.py::test_presentation_anchor_handles_orphans_and_cycles_deterministically 
tests/agents_sync/test_prompt_archive.py::test_patch_locator_resolves_only_current_project_pr 
[gw5] [ 98%] PASSED tests/agents_sync/test_prompt_archive.py::test_patch_locator_resolves_only_current_project_pr 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_resume.py::test_generic_reopen_is_home_first_then_repeated_opener_resumes 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_empty_no_fallback] 
tests/ace/tui/test_changespec_grouping_cycle.py::test_three_reverse_cycles_returns_to_by_project 
tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_rejects_wrong_types[value2] 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_three_reverse_cycles_returns_to_by_project 
tests/ace/tui/test_config_edit_modal_scope_widget.py::test_cycle_scope_changes_target 
tests/ace/tui/test_surface_tokens.py::test_unchanged_metadata_is_stable 
tests/agents_sync/test_rendering_kinship.py::test_historical_double_dash_name_uses_facade_ancestor_chain 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_rejects_wrong_types[value2] 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_kinship.py::test_historical_double_dash_name_uses_facade_ancestor_chain 
[gw8] [ 98%] PASSED tests/ace/tui/test_surface_tokens.py::test_unchanged_metadata_is_stable 
tests/agents_sync/test_prompt_archive.py::test_prepare_prompt_archive_accepts_expanded_planner_prompt 
tests/ace/tui/test_config_center_resume.py::test_switching_changes_resume_target_and_home_only_close_retains_it 
[gw5] [ 98%] PASSED tests/agents_sync/test_prompt_archive.py::test_prepare_prompt_archive_accepts_expanded_planner_prompt 
tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_rejects_wrong_types[value3] 
tests/agents_sync/test_rendering_kinship.py::test_each_relation_group_is_capped_with_a_roster_tail 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_stitches_default_query_schema_rejects_wrong_types[value3] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_empty_no_fallback] 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_kinship.py::test_each_relation_group_is_capped_with_a_roster_tail 
tests/agents_sync/test_git_sync.py::test_missing_configured_remote_is_not_created 
tests/test_bead/test_cli_plus_one.py::test_plus_one_human_fallback_uses_current_time_and_reopens 
[gw4] [ 98%] PASSED tests/agents_sync/test_git_sync.py::test_missing_configured_remote_is_not_created 
tests/agents_sync/test_prompt_archive.py::test_prompt_name_reuses_same_run_and_suffixes_another_run 
tests/agents_sync/test_rendering_variables.py::test_agent_variables_render_inline_previews_and_container_blocks 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_empty_json] 
[gw10] [ 98%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_ctrl_i_loads_non_yaml_xprompt_into_prompt_bar 
tests/ace/tui/test_changespec_grouping_cycle.py::test_forward_then_reverse_returns_to_by_project 
[gw5] [ 98%] PASSED tests/agents_sync/test_prompt_archive.py::test_prompt_name_reuses_same_run_and_suffixes_another_run 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_variables.py::test_agent_variables_render_inline_previews_and_container_blocks 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_forward_then_reverse_returns_to_by_project 
tests/ace/tui/test_commits_config.py::test_valid_custom_commits_query_is_parsed_once_for_startup 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_valid_custom_commits_query_is_parsed_once_for_startup 
tests/ace/tui/test_surface_tokens.py::test_surface_tokens_are_isolated 
[gw8] [ 98%] PASSED tests/ace/tui/test_surface_tokens.py::test_surface_tokens_are_isolated 
tests/ace/tui/models/test_agent_tree.py::test_project_clan_tree_keeps_generations_separate 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_tree.py::test_project_clan_tree_keeps_generations_separate 
tests/agents_sync/test_prompt_archive.py::test_publish_prompt_archive_missing_agents_target_is_nonfatal 
[gw5] [ 98%] PASSED tests/agents_sync/test_prompt_archive.py::test_publish_prompt_archive_missing_agents_target_is_nonfatal 
tests/agents_sync/test_rendering_variables.py::test_family_container_blocks_retain_member_attribution 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_variables.py::test_family_container_blocks_retain_member_attribution 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_empty_json] 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_enter_loads_raw_definition_and_binds_source 
tests/ace/tui/test_commits_config.py::test_valid_custom_stitches_query_is_parsed_once_for_startup 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_valid_custom_stitches_query_is_parsed_once_for_startup 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_human_fallback_uses_current_time_and_reopens 
[gw6] [ 98%] PASSED tests/ace/tui/test_config_edit_modal_scope_widget.py::test_cycle_scope_changes_target 
tests/agents_sync/test_prompt_archive.py::test_publish_prompt_archive_without_artifacts_is_git_idempotent 
tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_on_axe_tab_is_silent_noop 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_on_axe_tab_is_silent_noop 
tests/agents_sync/test_rendering_variables.py::test_container_block_and_preview_truncation_is_visible_and_bounded 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_variables.py::test_container_block_and_preview_truncation_is_visible_and_bounded 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show] 
tests/test_bead/test_cli_plus_one.py::test_plus_one_accepts_shorthand_refs_and_promotes_draft_task 
tests/ace/tui/test_commits_config.py::test_legacy_commits_key_falls_back_with_deprecation_warning 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_legacy_commits_key_falls_back_with_deprecation_warning 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show] 
tests/ace/tui/test_surface_tokens.py::test_creation_and_removal_are_visible 
[gw8] [ 98%] PASSED tests/ace/tui/test_surface_tokens.py::test_creation_and_removal_are_visible 
[gw3] [ 98%] PASSED tests/ace/tui/test_statistics_pane_view_navigation.py::test_view_cycle_reuses_composite_result_and_updates_strip 
tests/ace/tui/test_config_edit_modal_scope_widget.py::test_scope_selector_row_pick_changes_target 
[gw7] [ 98%] PASSED tests/ace/tui/test_config_hub_pane.py::test_resize_switches_caption_variant_without_reloading_children 
tests/ace/tui/models/test_agent_tree.py::test_clan_tree_does_not_invent_a_patch_banner_from_one_member 
tests/ace/tui/test_commits_config.py::test_stitches_key_wins_when_both_configured 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_tree.py::test_clan_tree_does_not_invent_a_patch_banner_from_one_member 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_stitches_key_wins_when_both_configured 
tests/agents_sync/test_rendering_variables.py::test_container_block_uses_a_fence_longer_than_nested_backticks 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_compact] 
[gw12] [ 98%] PASSED tests/agents_sync/test_rendering_variables.py::test_container_block_uses_a_fence_longer_than_nested_backticks 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_compact] 
tests/ace/tui/test_statistics_pane_view_navigation.py::test_eight_view_keyboard_and_mouse_navigation_share_order 
tests/ace/tui/test_changespec_grouping_integration.py::test_o_cycles_widget_through_every_grouping_mode 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_integration.py::test_o_cycles_widget_through_every_grouping_mode 
tests/ace/tui/test_config_hub_pane.py::test_config_lands_on_the_first_catalog_subtab_with_a_fresh_session 
[gw5] [ 98%] PASSED tests/agents_sync/test_prompt_archive.py::test_publish_prompt_archive_without_artifacts_is_git_idempotent 
[gw13] [ 98%] PASSED tests/ace/tui/test_config_center_resume.py::test_switching_changes_resume_target_and_home_only_close_retains_it 
tests/ace/tui/test_commits_config.py::test_invalid_runtime_query_falls_back_with_diagnostic[False] 
tests/agents_sync/test_revival_input_publication.py::test_publication_prefers_archive_over_later_live_prompt 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_json] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_invalid_runtime_query_falls_back_with_diagnostic[False] 
[gw12] [ 98%] PASSED tests/agents_sync/test_revival_input_publication.py::test_publication_prefers_archive_over_later_live_prompt 
[gw7] [ 98%] PASSED tests/ace/tui/test_config_hub_pane.py::test_config_lands_on_the_first_catalog_subtab_with_a_fresh_session 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_json] 
tests/ace/tui/test_surface_tokens.py::test_refresh_pulse_updates_agents_token 
[gw8] [ 98%] PASSED tests/ace/tui/test_surface_tokens.py::test_refresh_pulse_updates_agents_token 
tests/agents_sync/test_git_sync.py::test_pull_rebase_conflict_is_aborted_cleanly 
[gw2] [ 98%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_accepts_shorthand_refs_and_promotes_draft_task 
tests/ace/tui/test_config_center_resume.py::test_direct_entry_establishes_resume_target_after_success 
tests/ace/tui/test_config_hub_pane.py::test_config_subtab_visited_earlier_this_session_is_where_reopen_lands 
tests/ace/tui/test_commits_config.py::test_invalid_runtime_query_falls_back_with_diagnostic[repo:] 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_invalid_runtime_query_falls_back_with_diagnostic[repo:] 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_phase_json] 
tests/agents_sync/test_revival_input_publication.py::test_legacy_publication_reads_live_prompt_when_archive_is_absent 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_phase_json] 
[gw12] [ 98%] PASSED tests/agents_sync/test_revival_input_publication.py::test_legacy_publication_reads_live_prompt_when_archive_is_absent 
tests/agents_sync/test_prompt_archive_migration.py::test_migration_is_dry_run_complete_and_idempotent 
tests/test_bead/test_cli_plus_one.py::test_plus_one_public_entry_dispatch_uses_current_agent 
tests/ace/tui/test_changespec_grouping_integration.py::test_per_mode_fold_state_survives_cycle_round_trip 
[gw1] [ 98%] PASSED tests/ace/tui/test_changespec_grouping_integration.py::test_per_mode_fold_state_survives_cycle_round_trip 
tests/ace/tui/models/test_agent_tree.py::test_project_clan_tree_nests_disk_shaped_monitor_under_starter 
[gw0] [ 98%] PASSED tests/ace/tui/models/test_agent_tree.py::test_project_clan_tree_nests_disk_shaped_monitor_under_starter 
[gw7] [ 98%] PASSED tests/ace/tui/test_config_hub_pane.py::test_config_subtab_visited_earlier_this_session_is_where_reopen_lands 
tests/ace/tui/test_commits_config.py::test_missing_runtime_query_uses_bundled_value_without_warning 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_missing_runtime_query_uses_bundled_value_without_warning 
tests/agents_sync/test_revival_input_publication.py::test_dismissed_publication_after_cleanup_uses_launch_archive 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_phase_parent_epic_plan] 
[gw9] [ 98%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_phase_parent_epic_plan] 
tests/ace/tui/test_surface_tokens.py::test_nested_agent_archive_is_ignored 
[gw8] [ 98%] PASSED tests/ace/tui/test_surface_tokens.py::test_nested_agent_archive_is_ignored 
tests/ace/tui/test_config_hub_pane_launch_flags.py::test_launch_direct_entry_opens_launch 
[gw4] [ 98%] PASSED tests/agents_sync/test_git_sync.py::test_pull_rebase_conflict_is_aborted_cleanly 
[gw7] [ 98%] PASSED tests/ace/tui/test_config_hub_pane_launch_flags.py::test_launch_direct_entry_opens_launch 
tests/ace/tui/test_commits_config.py::test_configured_explicit_limit_is_left_alone 
[gw11] [ 98%] PASSED tests/ace/tui/test_commits_config.py::test_configured_explicit_limit_is_left_alone 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_epic_expansion_compact] 
[gw5] [ 98%] PASSED tests/agents_sync/test_prompt_archive_migration.py::test_migration_is_dry_run_complete_and_idempotent 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_epic_expansion_compact] 
tests/ace/tui/test_changespec_grouping_integration.py::test_query_change_drops_collapsed_group_without_crash 
[gw1] [ 99%] PASSED tests/ace/tui/test_changespec_grouping_integration.py::test_query_change_drops_collapsed_group_without_crash 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_enter_loads_raw_definition_and_binds_source 
tests/ace/tui/test_commits_config.py::test_startup_project_precedence_is_explicit_then_config_then_current 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_config.py::test_startup_project_precedence_is_explicit_then_config_then_current 
tests/ace/tui/test_config_hub_pane_launch_flags.py::test_launch_result_refreshes_app_indicators 
tests/ace/tui/models/test_agent_tree.py::test_project_clan_tree_keeps_tagged_and_disk_shaped_monitors_identical 
[gw12] [ 99%] PASSED tests/agents_sync/test_revival_input_publication.py::test_dismissed_publication_after_cleanup_uses_launch_archive 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree.py::test_project_clan_tree_keeps_tagged_and_disk_shaped_monitors_identical 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_launch_flags.py::test_launch_result_refreshes_app_indicators 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[ready] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[ready] 
tests/ace/tui/test_surface_tokens.py::test_chop_history_is_not_walked 
[gw8] [ 99%] PASSED tests/ace/tui/test_surface_tokens.py::test_chop_history_is_not_walked 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_ctrl_i_stages_declared_inputs_into_frontmatter 
tests/agents_sync/test_prompt_archive_migration.py::test_migration_preserves_different_canonical_destination 
tests/ace/tui/test_commits_config.py::test_startup_project_remains_absent_without_any_known_project 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_config.py::test_startup_project_remains_absent_without_any_known_project 
tests/agents_sync/test_revival_input_publication.py::test_legacy_dismissed_publication_keeps_inline_prompt_without_archive 
[gw12] [ 99%] PASSED tests/agents_sync/test_revival_input_publication.py::test_legacy_dismissed_publication_keeps_inline_prompt_without_archive 
tests/ace/tui/test_changespec_grouping_integration.py::test_collapse_then_filter_reload_does_not_resurrect_stale_collapse 
[gw1] [ 99%] PASSED tests/ace/tui/test_changespec_grouping_integration.py::test_collapse_then_filter_reload_does_not_resurrect_stale_collapse 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_public_entry_dispatch_uses_current_agent 
tests/ace/tui/test_config_hub_pane_launch_flags.py::test_embedded_launch_change_then_close_refreshes_indicators_once 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[blocked] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[blocked] 
tests/test_bead/test_cli_plus_one.py::test_plus_one_repeat_is_noop_with_note_guidance 
tests/ace/tui/test_commits_config.py::test_known_startup_project_is_displayed_before_first_collection[configured] 
tests/agents_sync/test_status.py::test_plain_status_reconciles_cache_without_running_git 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_launch_flags.py::test_embedded_launch_change_then_close_refreshes_indicators_once 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_migration.py::test_migration_preserves_different_canonical_destination 
[gw12] [ 99%] PASSED tests/agents_sync/test_status.py::test_plain_status_reconciles_cache_without_running_git 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[stats] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[stats] 
tests/ace/tui/models/test_agent_tree.py::test_agent_tree_title_names_bash_python_and_roots_not_shells 
tests/ace/tui/test_surface_tokens.py::test_lumberjack_status_change_is_visible 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree.py::test_agent_tree_title_names_bash_python_and_roots_not_shells 
[gw8] [ 99%] PASSED tests/ace/tui/test_surface_tokens.py::test_lumberjack_status_change_is_visible 
tests/ace/tui/test_changespec_grouping_integration.py::test_agents_cycle_does_not_swap_cl_widget_render 
[gw1] [ 99%] PASSED tests/ace/tui/test_changespec_grouping_integration.py::test_agents_cycle_does_not_swap_cl_widget_render 
tests/ace/tui/test_config_hub_pane_launch_flags.py::test_embedded_launch_unchanged_close_does_not_refresh_indicators 
tests/agents_sync/test_prompt_archive_migration.py::test_migration_restarts_when_archive_commit_already_exists 
tests/agents_sync/test_status.py::test_plain_status_reports_publication_quarantine 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_pane_view_navigation.py::test_eight_view_keyboard_and_mouse_navigation_share_order 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[dep_add] 
[gw12] [ 99%] PASSED tests/agents_sync/test_status.py::test_plain_status_reports_publication_quarantine 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_repeat_is_noop_with_note_guidance 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_launch_flags.py::test_embedded_launch_unchanged_close_does_not_refresh_indicators 
tests/agents_sync/test_git_sync.py::test_network_git_environment_is_noninteractive 
[gw4] [ 99%] PASSED tests/agents_sync/test_git_sync.py::test_network_git_environment_is_noninteractive 
tests/ace/tui/test_statistics_pane_view_navigation.py::test_every_view_selection_path_keeps_heading_tab_rail_and_view_aligned 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[dep_add] 
tests/test_bead/test_cli_plus_one.py::test_plus_one_rejects_non_task_without_mutation 
tests/ace/tui/test_changespec_grouping_integration.py::test_tab_switch_preserves_each_tabs_grouping_mode 
[gw1] [ 99%] PASSED tests/ace/tui/test_changespec_grouping_integration.py::test_tab_switch_preserves_each_tabs_grouping_mode 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_config.py::test_known_startup_project_is_displayed_before_first_collection[configured] 
tests/agents_sync/test_status.py::test_plain_status_stays_quiet_for_an_active_agent_publication 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_migration.py::test_migration_restarts_when_archive_commit_already_exists 
tests/ace/tui/test_surface_tokens.py::test_project_spec_and_bead_manifest_invalidate_patches 
tests/ace/tui/test_config_hub_pane_launch_flags.py::test_config_hub_strip_thresholds_grow_for_the_flags_child 
[gw8] [ 99%] PASSED tests/ace/tui/test_surface_tokens.py::test_project_spec_and_bead_manifest_invalidate_patches 
tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_uses_latest_explicit_clan_tribe 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_uses_latest_explicit_clan_tribe 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[update] 
[gw12] [ 99%] PASSED tests/agents_sync/test_status.py::test_plain_status_stays_quiet_for_an_active_agent_publication 
tests/ace/tui/test_commits_config.py::test_known_startup_project_is_displayed_before_first_collection[ace-query] 
tests/agents_sync/test_prompt_archive_migration.py::test_migration_recovers_when_only_plans_push_remains 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_launch_flags.py::test_config_hub_strip_thresholds_grow_for_the_flags_child 
tests/ace/tui/test_changespec_grouping_integration.py::test_axe_cycle_is_silent_noop_for_both_tabs 
[gw1] [ 99%] PASSED tests/ace/tui/test_changespec_grouping_integration.py::test_axe_cycle_is_silent_noop_for_both_tabs 
tests/agents_sync/test_status.py::test_missing_or_corrupt_status_never_implies_network[None] 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_rejects_non_task_without_mutation 
[gw12] [ 99%] PASSED tests/agents_sync/test_status.py::test_missing_or_corrupt_status_never_implies_network[None] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[update] 
tests/ace/tui/test_config_hub_pane_launch_flags.py::test_flags_resume_falls_back_when_rollout_is_off 
tests/test_bead/test_cli_plus_one.py::test_plus_one_reports_missing_task_and_blank_evidence[missing-Evidence-issue not found: missing] 
tests/ace/tui/test_surface_tokens.py::test_absent_paths_are_stable 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_launch_flags.py::test_flags_resume_falls_back_when_rollout_is_off 
[gw8] [ 99%] PASSED tests/ace/tui/test_surface_tokens.py::test_absent_paths_are_stable 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_resume.py::test_direct_entry_establishes_resume_target_after_success 
tests/agents_sync/test_status.py::test_missing_or_corrupt_status_never_implies_network[{broken] 
tests/ace/tui/test_changespec_jk_navigation.py::test_patch_list_update_highlight_suppresses_programmatic_selection 
[gw1] [ 99%] PASSED tests/ace/tui/test_changespec_jk_navigation.py::test_patch_list_update_highlight_suppresses_programmatic_selection 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_migration.py::test_migration_recovers_when_only_plans_push_remains 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[open] 
tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_uses_context_when_declarer_is_omitted 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_uses_context_when_declarer_is_omitted 
[gw12] [ 99%] PASSED tests/agents_sync/test_status.py::test_missing_or_corrupt_status_never_implies_network[{broken] 
tests/ace/tui/test_config_hub_pane_launch_flags.py::test_flags_off_prefix_keeps_five_child_numbering 
tests/ace/tui/test_config_center_resume.py::test_new_process_loads_remembered_admin_center_section 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_config.py::test_known_startup_project_is_displayed_before_first_collection[ace-query] 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_reports_missing_task_and_blank_evidence[missing-Evidence-issue not found: missing] 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_scope_widget.py::test_scope_selector_row_pick_changes_target 
tests/agents_sync/test_status.py::test_explicit_refresh_fetches_once_and_updates_cached_diagnostics 
tests/agents_sync/test_prompt_archive_validation.py::test_clean_archive_validates_without_diagnostics 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_validation.py::test_clean_archive_validates_without_diagnostics 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[open] 
[gw12] [ 99%] PASSED tests/agents_sync/test_status.py::test_explicit_refresh_fetches_once_and_updates_cached_diagnostics 
tests/test_bead/test_cli_plus_one.py::test_plus_one_reports_missing_task_and_blank_evidence[unused-   -note cannot be empty or blank] 
tests/ace/tui/test_changespec_jk_navigation.py::test_patch_list_user_highlight_still_posts_selection 
[gw1] [ 99%] PASSED tests/ace/tui/test_changespec_jk_navigation.py::test_patch_list_user_highlight_still_posts_selection 
tests/agents_sync/test_git_sync_outbox.py::test_all_project_sync_isolates_failures 
tests/ace/tui/test_surface_tokens.py::test_stat_permission_error_is_indeterminate 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_launch_flags.py::test_flags_off_prefix_keeps_five_child_numbering 
[gw4] [ 99%] PASSED tests/agents_sync/test_git_sync_outbox.py::test_all_project_sync_isolates_failures 
tests/ace/tui/test_commits_config.py::test_inferred_current_project_scopes_stitches_after_async_inventory 
[gw8] [ 99%] PASSED tests/ace/tui/test_surface_tokens.py::test_stat_permission_error_is_indeterminate 
tests/ace/tui/test_config_edit_modal_scope_widget.py::test_new_overlay_switches_scope_to_created_overlay 
tests/agents_sync/test_prompt_archive_validation.py::test_prompt_archive_listing_does_not_hash_artifact_payloads 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_validation.py::test_prompt_archive_listing_does_not_hash_artifact_payloads 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[close] 
tests/agents_sync/test_status.py::test_refresh_aborts_before_git_when_shutdown_is_requested 
tests/ace/tui/test_config_hub_pane_launch_flags.py::test_flags_direct_entry_shows_flags_caption 
[gw12] [ 99%] PASSED tests/agents_sync/test_status.py::test_refresh_aborts_before_git_when_shutdown_is_requested 
tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_wire_enrichment_loads_clan_summary 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_wire_enrichment_loads_clan_summary 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_launch_flags.py::test_flags_direct_entry_shows_flags_caption 
tests/agents_sync/test_prompt_archive_validation.py::test_xprompt_style_body_links_are_validated_as_ordinary_markdown 
tests/ace/tui/test_timestamps_builder.py::TestCollapsed::test_collapsed_single_entry_no_folded_indicator 
[gw1] [ 99%] PASSED tests/ace/tui/test_timestamps_builder.py::TestCollapsed::test_collapsed_single_entry_no_folded_indicator 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_validation.py::test_xprompt_style_body_links_are_validated_as_ordinary_markdown 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[close] 
tests/agents_sync/test_status.py::test_revalidate_only_never_runs_git 
tests/ace/tui/test_surface_tokens.py::test_scandir_permission_error_is_indeterminate 
[gw12] [ 99%] PASSED tests/agents_sync/test_status.py::test_revalidate_only_never_runs_git 
[gw8] [ 99%] PASSED tests/ace/tui/test_surface_tokens.py::test_scandir_permission_error_is_indeterminate 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_reports_missing_task_and_blank_evidence[unused-   -note cannot be empty or blank] 
tests/ace/tui/test_config_hub_pane_navigation.py::test_home_digits_stop_at_six 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[close_phases] 
tests/agents_sync/test_prompt_archive_validation.py::test_each_archive_diagnostic_has_a_single_purpose_built_source 
tests/test_bead/test_cli_plus_one.py::test_plus_one_uses_canonical_commit_and_deferred_push 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_validation.py::test_each_archive_diagnostic_has_a_single_purpose_built_source 
tests/ace/tui/test_timestamps_builder.py::TestCollapsed::test_collapsed_shows_last_entry_not_first 
[gw1] [ 99%] PASSED tests/ace/tui/test_timestamps_builder.py::TestCollapsed::test_collapsed_shows_last_entry_not_first 
tests/agents_sync/test_status.py::test_status_rejects_conflicting_network_modes 
[gw12] [ 99%] PASSED tests/agents_sync/test_status.py::test_status_rejects_conflicting_network_modes 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_home_digits_stop_at_six 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[close_phases] 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_ctrl_i_stages_declared_inputs_into_frontmatter 
tests/agents_sync/test_prompt_archive_validation.py::test_inline_artifact_link_is_validated_outside_code_fences 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_validation.py::test_inline_artifact_link_is_validated_outside_code_fences 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_config.py::test_inferred_current_project_scopes_stitches_after_async_inventory 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_uses_remembered_or_first_stop[stops1-remembered1-expected1] 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_uses_remembered_or_first_stop[stops1-remembered1-expected1] 
tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_uses_latest_explicit_clan_summary 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_uses_latest_explicit_clan_summary 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[close_phases_not_epic] 
tests/ace/tui/test_surface_tokens.py::test_probe_snapshot_includes_every_surface 
[gw8] [ 99%] PASSED tests/ace/tui/test_surface_tokens.py::test_probe_snapshot_includes_every_surface 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[close_phases_not_epic] 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_uses_canonical_commit_and_deferred_push 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_ctrl_i_is_inert_for_yaml_backed_rows 
tests/ace/tui/test_config_hub_pane_navigation.py::test_filter_brackets_cycle_config_subtabs 
tests/ace/tui/test_commits_pane_collection.py::test_sidecar_snapshot_coverage_is_directional 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_sidecar_snapshot_coverage_is_directional 
tests/ace/tui/test_timestamps_builder.py::TestExpanded::test_expanded_shows_commit_and_rewind_entries_only 
[gw1] [ 99%] PASSED tests/ace/tui/test_timestamps_builder.py::TestExpanded::test_expanded_shows_commit_and_rewind_entries_only 
tests/agents_sync/test_prompt_archive_validation.py::test_pending_manifest_run_without_queue_entry_is_a_nonfailing_warning 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_validation.py::test_pending_manifest_run_without_queue_entry_is_a_nonfailing_warning 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_uses_remembered_or_first_stop[stops2-None-expected2] 
tests/test_bead/test_cli_plus_one.py::test_plus_one_idempotent_retry_skips_commit_and_push 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_uses_remembered_or_first_stop[stops2-None-expected2] 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_scope_widget.py::test_new_overlay_switches_scope_to_created_overlay 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[rm] 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_filter_brackets_cycle_config_subtabs 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[rm] 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_uses_remembered_or_first_stop[stops3-remembered3-None] 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_uses_remembered_or_first_stop[stops3-remembered3-None] 
tests/agents_sync/test_git_sync_outbox.py::test_full_sync_acknowledges_publication_outbox_after_success 
tests/agents_sync/test_prompt_archive_validation.py::test_pending_manifest_run_reports_unpublished_even_when_queued 
tests/ace/tui/test_commits_pane_collection.py::test_show_merges_snapshot_covers_every_merge_visibility_mode 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_validation.py::test_pending_manifest_run_reports_unpublished_even_when_queued 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_show_merges_snapshot_covers_every_merge_visibility_mode 
[gw4] [ 99%] PASSED tests/agents_sync/test_git_sync_outbox.py::test_full_sync_acknowledges_publication_outbox_after_success 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_plus_one.py::test_plus_one_idempotent_retry_skips_commit_and_push 
tests/ace/tui/test_config_edit_modal_validation_widget.py::test_reset_to_default_plans_unset 
tests/ace/tui/test_surface_tokens.py::test_proc_token_tracks_store_file 
tests/ace/tui/test_config_hub_pane_navigation.py::test_config_number_prefix_selects_alphabetic_subtabs 
[gw8] [ 99%] PASSED tests/ace/tui/test_surface_tokens.py::test_proc_token_tracks_store_file 
tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_omits_summary_without_declaration 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[rm_multiple] 
tests/test_bead/test_cli_read_single_store.py::test_read_commands_use_primary_store_from_primary_workspace 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_omits_summary_without_declaration 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_preserves_legacy_no_keyword_fallback 
tests/ace/tui/test_timestamps_builder.py::TestFullyExpanded::test_fully_expanded_shows_all_entries 
[gw1] [ 99%] PASSED tests/ace/tui/test_timestamps_builder.py::TestFullyExpanded::test_fully_expanded_shows_all_entries 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_preserves_legacy_no_keyword_fallback 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_resume.py::test_new_process_loads_remembered_admin_center_section 
tests/ace/tui/test_commits_pane_collection.py::test_snapshot_coverage_trusts_truncation_metadata_not_row_count 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_snapshot_coverage_trusts_truncation_metadata_not_row_count 
tests/agents_sync/test_prompt_archive_validation.py::test_full_validate_check_set_passes_with_pending_queue_and_unpublished_prompt 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_validation.py::test_full_validate_check_set_passes_with_pending_queue_and_unpublished_prompt 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_read_single_store.py::test_read_commands_use_primary_store_from_primary_workspace 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[rm_multiple] 
tests/test_bead/test_cli_read_single_store.py::test_read_commands_use_sibling_store_from_sibling_workspace 
tests/ace/tui/models/test_agent_tribe_summary.py::test_snapshot_preserves_mixed_unit_order_and_aggregates_loaded_rows 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_pane_view_navigation.py::test_every_view_selection_path_keeps_heading_tab_rail_and_view_aligned 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_snapshot_preserves_mixed_unit_order_and_aggregates_loaded_rows 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_read_single_store.py::test_read_commands_use_sibling_store_from_sibling_workspace 
tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[exact] 
tests/ace/tui/test_config_center_resume.py::test_persisted_tab_seeds_home_and_repeated_opener_resume 
tests/agents_sync/test_prompt_archive_validation.py::test_missing_plans_checkout_is_a_nonfailing_warning 
[gw5] [ 99%] PASSED tests/agents_sync/test_prompt_archive_validation.py::test_missing_plans_checkout_is_a_nonfailing_warning 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_config_number_prefix_selects_alphabetic_subtabs 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[sync_status] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[sync_status] 
tests/test_bead/test_cli_read_single_store.py::test_read_commands_use_sibling_store_from_sibling_subdirectory 
tests/ace/tui/test_timestamps_builder.py::TestFullyExpanded::test_rebase_entry_uses_rebase_color 
[gw1] [ 99%] PASSED tests/ace/tui/test_timestamps_builder.py::TestFullyExpanded::test_rebase_entry_uses_rebase_color 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_read_single_store.py::test_read_commands_use_sibling_store_from_sibling_subdirectory 
tests/ace/tui/models/test_agent_tribe_summary.py::test_attention_digest_and_default_identity_use_unit_statuses 
tests/ace/tui/test_sync.py::TestSyncTaskSuccess::test_returns_success_on_sync_success 
tests/ace/tui/test_statistics_perf.py::test_populated_perf_renderable_covers_every_panel 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_attention_digest_and_default_identity_use_unit_statuses 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskSuccess::test_returns_success_on_sync_success 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_populated_perf_renderable_covers_every_panel 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_ctrl_i_is_inert_for_yaml_backed_rows 
tests/agents_sync/test_publication.py::test_targeted_publication_captures_complete_hood_and_is_byte_stable 
tests/test_bead/test_cli_refs.py::test_ref_parser_defaults_to_list_and_documents_options 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_refs.py::test_ref_parser_defaults_to_list_and_documents_options 
tests/ace/tui/test_config_hub_pane_navigation.py::test_config_prefix_repeats_out_of_range_and_non_digit_cancel 
tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_retains_direct_tribe_fallback 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_missing] 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_clan_metadata.py::test_project_clan_tree_retains_direct_tribe_fallback 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_missing] 
tests/ace/tui/models/test_agent_tribe_summary.py::test_family_unit_counts_and_children_use_concrete_planner_projection 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_family_unit_counts_and_children_use_concrete_planner_projection 
tests/ace/tui/test_statistics_perf.py::test_hero_tiles_include_delta_and_startup_sparkline 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_hero_tiles_include_delta_and_startup_sparkline 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_tab_switches_admin_center_tab_on_eligible_row 
tests/test_bead/test_cli_refs.py::test_ref_add_list_and_rm_round_trip_through_the_slow_path 
tests/ace/tui/test_tmux_agent_modal.py::test_row_text_marks_ready_not_installed_and_routing_disabled 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_row_text_marks_ready_not_installed_and_routing_disabled 
tests/ace/tui/models/test_agent_tribe_summary.py::test_tribe_queue_count_is_scoped_and_aggregate_is_queued 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_tribe_queue_count_is_scoped_and_aggregate_is_queued 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[create_invalid_type] 
tests/ace/tui/test_statistics_perf.py::test_telemetry_disabled_keeps_log_panels_and_names_config_key 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_telemetry_disabled_keeps_log_panels_and_names_config_key 
tests/ace/tui/test_sync.py::TestSyncTaskSuccess::test_returns_success_on_resolved_status 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_config_prefix_repeats_out_of_range_and_non_digit_cancel 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskSuccess::test_returns_success_on_resolved_status 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_refs.py::test_ref_add_list_and_rm_round_trip_through_the_slow_path 
tests/ace/tui/models/test_agent_tribe_summary.py::test_workflow_unit_counts_agent_steps_once_and_never_as_nested 
tests/ace/tui/test_statistics_perf.py::test_missing_logs_render_empty_states_while_telemetry_table_stays 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_workflow_unit_counts_agent_steps_once_and_never_as_nested 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_missing_logs_render_empty_states_while_telemetry_table_stays 
tests/ace/tui/test_tmux_agent_modal.py::test_row_text_marks_soft_disable_without_routing_disabled_label 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_row_text_marks_soft_disable_without_routing_disabled_label 
tests/test_bead/test_cli_refs.py::test_ref_add_reports_a_missing_issue_without_crashing 
tests/ace/tui/models/test_agent_tree_folds.py::test_clan_and_members_fold_independently_through_recursive_ancestors 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_folds.py::test_clan_and_members_fold_independently_through_recursive_ancestors 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[create_invalid_type] 
tests/ace/tui/test_config_hub_pane_navigation.py::test_configured_config_prefix_selects_subtab 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_validation_widget.py::test_reset_to_default_plans_unset 
tests/agents_sync/test_git_sync_outbox.py::test_full_sync_keeps_outbox_request_when_agent_page_did_not_materialize 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_resume.py::test_persisted_tab_seeds_home_and_repeated_opener_resume 
[gw5] [ 99%] PASSED tests/agents_sync/test_publication.py::test_targeted_publication_captures_complete_hood_and_is_byte_stable 
[gw4] [ 99%] PASSED tests/agents_sync/test_git_sync_outbox.py::test_full_sync_keeps_outbox_request_when_agent_page_did_not_materialize 
tests/ace/tui/models/test_agent_tribe_summary.py::test_finished_family_projects_all_members_to_done 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_finished_family_projects_all_members_to_done 
tests/ace/tui/test_statistics_perf.py::test_absent_log_source_uses_present_false_empty_state 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_absent_log_source_uses_present_false_empty_state 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_configured_config_prefix_selects_subtab 
tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_workspace_dir_error 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_workspace_dir_error 
tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[create_missing_parent] 
tests/ace/tui/test_config_edit_modal_validation_widget.py::test_client_constraint_blocks_plan 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[create_missing_parent] 
tests/ace/tui/test_config_center_resume.py::test_invalid_persisted_tab_keeps_no_history_home 
tests/ace/tui/test_tmux_agent_modal.py::test_description_strip_shows_exact_command 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_description_strip_shows_exact_command 
tests/agents_sync/test_publication.py::test_refresh_adds_optional_chat_and_preserves_temporarily_absent_run 
tests/ace/tui/models/test_agent_tribe_summary.py::test_machine_qualified_children_compact_against_presented_containers 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_machine_qualified_children_compact_against_presented_containers 
tests/ace/tui/test_statistics_perf.py::test_provider_and_workflow_group_modes_change_the_latency_table 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_provider_and_workflow_group_modes_change_the_latency_table 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_refs.py::test_ref_add_reports_a_missing_issue_without_crashing 
tests/ace/tui/test_config_hub_pane_navigation.py::test_bare_child_digit_stays_local_until_config_prefix 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_tab_switches_admin_center_tab_on_eligible_row 
tests/test_bead/test_cli_history.py::test_history_parser_contract_and_missing_id_error 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_history_parser_contract_and_missing_id_error 
tests/test_bead/test_cli_refs.py::test_ref_add_exits_when_the_rust_core_declines 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_refs.py::test_ref_add_exits_when_the_rust_core_declines 
tests/ace/tui/models/test_agent_tribe_summary.py::test_local_machine_clan_with_family_projects_to_one_presented_unit 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_local_machine_clan_with_family_projects_to_one_presented_unit 
tests/ace/tui/test_statistics_perf.py::test_subsystem_row_with_histogram_and_no_counter_renders_em_dash 
tests/ace/tui/models/test_agent_tree_folds.py::test_clan_tree_query_retains_complete_immediate_parent_chain 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_subsystem_row_with_histogram_and_no_counter_renders_em_dash 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_folds.py::test_clan_tree_query_retains_complete_immediate_parent_chain 
tests/test_bead/test_cli_refs.py::test_show_renders_resolved_and_missing_references 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_bare_child_digit_stays_local_until_config_prefix 
tests/ace/tui/test_tmux_agent_modal.py::test_description_strip_shows_install_hint_when_not_installed 
tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_claim_failure 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_description_strip_shows_install_hint_when_not_installed 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_claim_failure 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_shift_tab_switches_admin_center_tab_on_yaml_backed_row 
tests/test_bead/test_cli_history.py::test_lost_notes_parser_contract_and_restore_requires_scan_mode 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_lost_notes_parser_contract_and_restore_requires_scan_mode 
tests/ace/tui/models/test_agent_tribe_summary.py::test_reference_tribe_counts_six_lane_statuses_and_eight_nested 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_reference_tribe_counts_six_lane_statuses_and_eight_nested 
tests/ace/tui/test_statistics_perf.py::test_wide_and_narrow_startup_stalls_switch_without_changing_data 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_wide_and_narrow_startup_stalls_switch_without_changing_data 
tests/test_bead/test_cli_history.py::test_lost_notes_yes_requires_restore 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_lost_notes_yes_requires_restore 
tests/ace/tui/models/test_agent_tribe_summary.py::test_snapshot_carries_description 
tests/ace/tui/test_config_hub_pane_navigation.py::test_config_filter_keeps_prefix_digits_as_text 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_summary.py::test_snapshot_carries_description 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_refs.py::test_show_renders_resolved_and_missing_references 
tests/ace/tui/test_statistics_perf.py::test_empty_agent_runs_still_paint_populated_perf 
tests/ace/tui/test_tmux_agent_modal.py::test_navigation_skips_not_installed_rows 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_empty_agent_runs_still_paint_populated_perf 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[exact] 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_navigation_skips_not_installed_rows 
tests/test_bead/test_cli_history.py::test_history_compact_lists_event_metadata_and_changed_fields 
tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_checkout_failure 
tests/test_bead/test_cli_refs.py::test_ref_list_resolve_json_returns_machine_readable_outcomes 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_checkout_failure 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_config_filter_keeps_prefix_digits_as_text 
tests/ace/tui/models/test_agent_wait_beads.py::test_agent_without_bead_wait_performs_no_store_call 
tests/ace/tui/models/test_agent_tree_ordering.py::test_project_clan_tree_sorts_direct_member_units_by_status_priority 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_wait_beads.py::test_agent_without_bead_wait_performs_no_store_call 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_ordering.py::test_project_clan_tree_sorts_direct_member_units_by_status_priority 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_validation_widget.py::test_client_constraint_blocks_plan 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_resume.py::test_invalid_persisted_tab_keeps_no_history_home 
tests/ace/tui/test_statistics_perf.py::test_missing_perf_snapshot_has_distinct_recovery_guidance 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_missing_perf_snapshot_has_distinct_recovery_guidance 
tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[provider-cap] 
tests/agents_sync/test_git_sync_outbox.py::test_drop_retired_removes_only_retired_requests_and_reports_them 
tests/ace/tui/models/test_agent_wait_beads.py::test_memory_snapshot_distinguishes_cold_cache_miss 
tests/ace/tui/test_config_hub_pane_navigation.py::test_relationship_children_own_tab_keys 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_wait_beads.py::test_memory_snapshot_distinguishes_cold_cache_miss 
[gw4] [ 99%] PASSED tests/agents_sync/test_git_sync_outbox.py::test_drop_retired_removes_only_retired_requests_and_reports_them 
[gw5] [ 99%] PASSED tests/agents_sync/test_publication.py::test_refresh_adds_optional_chat_and_preserves_temporarily_absent_run 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_refs.py::test_ref_list_resolve_json_returns_machine_readable_outcomes 
tests/ace/tui/test_config_edit_modal_validation_widget.py::test_live_validation_error_appears_and_clears 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_history_compact_lists_event_metadata_and_changed_fields 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_relationship_children_own_tab_keys 
tests/ace/tui/test_statistics_perf.py::test_all_time_retention_note_appears_in_the_coverage_strip 
tests/ace/tui/test_tmux_agent_modal.py::test_enter_launches_highlighted_provider 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_all_time_retention_note_appears_in_the_coverage_strip 
tests/ace/tui/test_config_center_resume.py::test_blocked_write_keeps_navigation_responsive_and_persists_latest 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_enter_launches_highlighted_provider 
tests/test_bead/test_cli_refs.py::test_show_without_references_omits_refs_section 
tests/ace/tui/models/test_agent_wait_beads.py::test_two_resolves_inside_ttl_use_one_store_call 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_wait_beads.py::test_two_resolves_inside_ttl_use_one_store_call 
tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_workflow_error_status 
tests/test_bead/test_cli_history.py::test_history_labels_redundant_duplicate_close_in_all_formats 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_workflow_error_status 
tests/ace/tui/test_config_hub_pane_navigation.py::test_busy_child_blocks_config_subtab_switch 
tests/agents_sync/test_publication.py::test_targeted_publication_accepts_family_container_request 
tests/ace/tui/test_statistics_perf.py::test_probes_report_enabled_env_vars 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_probes_report_enabled_env_vars 
tests/ace/tui/models/test_agent_tree_ordering.py::test_project_clan_tree_keeps_same_bucket_launch_order_stable 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_shift_tab_switches_admin_center_tab_on_yaml_backed_row 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_ordering.py::test_project_clan_tree_keeps_same_bucket_launch_order_stable 
tests/ace/tui/models/test_agent_wait_beads.py::test_multiple_beads_are_resolved_in_one_batch 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_wait_beads.py::test_multiple_beads_are_resolved_in_one_batch 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_busy_child_blocks_config_subtab_switch 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_refs.py::test_show_without_references_omits_refs_section 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_history_labels_redundant_duplicate_close_in_all_formats 
tests/ace/tui/test_statistics_perf.py::test_perf_tiles_are_plain_and_do_not_navigate 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_list_focused_digits_select_admin_center_tabs 
tests/test_bead/test_cli_resolution.py::test_find_beads_location_separate_repo_prefers_workspace_local_clone 
tests/ace/tui/models/test_agent_wait_beads.py::test_unavailable_store_result_is_negatively_cached 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_wait_beads.py::test_unavailable_store_result_is_negatively_cached 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_resolution.py::test_find_beads_location_separate_repo_prefers_workspace_local_clone 
tests/ace/tui/test_tmux_agent_modal.py::test_selector_key_launches_provider 
tests/ace/tui/test_config_hub_pane_navigation.py::test_busy_config_child_blocks_top_level_switch_and_close 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[provider-cap] 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_selector_key_launches_provider 
tests/test_bead/test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable 
tests/test_bead/test_cli_resolution.py::test_find_beads_location_local_mode_still_uses_primary_workspace 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_resolution.py::test_find_beads_location_local_mode_still_uses_primary_workspace 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_hub_pane_navigation.py::test_busy_config_child_blocks_top_level_switch_and_close 
tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_workflow_execution_error 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_workflow_execution_error 
tests/test_bead/test_cli_resolution.py::test_find_beads_location_sidecar_store_uses_plans_clone 
[gw5] [ 99%] PASSED tests/agents_sync/test_publication.py::test_targeted_publication_accepts_family_container_request 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_resolution.py::test_find_beads_location_sidecar_store_uses_plans_clone 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable 
tests/ace/tui/models/test_agent_tree_ordering.py::test_project_clan_tree_sorts_family_unit_by_displayed_anchor_status 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_ordering.py::test_project_clan_tree_sorts_family_unit_by_displayed_anchor_status 
tests/ace/tui/test_config_pane_widget.py::test_config_pane_loads_and_populates_tree 
tests/test_bead/test_cli_resolution.py::test_find_beads_location_split_sidecar_uses_repository_root 
tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[aggregate-cap] 
tests/agents_sync/test_publication.py::test_family_lane_and_member_requests_publish_identical_payloads 
tests/ace/tui/test_tmux_agent_modal.py::test_safe_launch_strips_bypass_args 
tests/test_bead/test_cli_history.py::test_history_full_shows_reopen_clearing_closed_at 
tests/agents_sync/test_git_sync_outbox.py::test_sync_without_drop_retired_keeps_and_reports_retired_requests 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_safe_launch_strips_bypass_args 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_resolution.py::test_find_beads_location_split_sidecar_uses_repository_root 
[gw4] [ 99%] PASSED tests/agents_sync/test_git_sync_outbox.py::test_sync_without_drop_retired_keeps_and_reports_retired_requests 
tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_unparseable_output 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskFailure::test_returns_failure_on_unparseable_output 
tests/test_bead/test_cli_resolution.py::test_find_beads_location_in_tree_prefers_current_checkout 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_resolution.py::test_find_beads_location_in_tree_prefers_current_checkout 
tests/test_bead/test_cli_resolution.py::test_find_beads_location_non_vc_walkup_fallback_when_primary_unknown 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_resolution.py::test_find_beads_location_non_vc_walkup_fallback_when_primary_unknown 
tests/ace/tui/models/test_agent_tree_ordering.py::test_project_clan_tree_ranks_starting_with_running 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_ordering.py::test_project_clan_tree_ranks_starting_with_running 
tests/ace/tui/test_tmux_agent_modal.py::test_launch_failure_keeps_modal_open_and_notifies_error 
tests/ace/tui/models/test_agent_wait_beads.py::test_warm_wait_bead_statuses_batches_and_dedupes_by_project 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_launch_failure_keeps_modal_open_and_notifies_error 
[gw12] [ 99%] PASSED tests/ace/tui/models/test_agent_wait_beads.py::test_warm_wait_bead_statuses_batches_and_dedupes_by_project 
tests/test_bead/test_cli_resolution.py::test_find_beads_location_non_vc_variant_workspace_maps_to_primary 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_resolution.py::test_find_beads_location_non_vc_variant_workspace_maps_to_primary 
tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_released_on_success 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_released_on_success 
tests/test_bead/test_cli_resolution.py::test_get_project_opens_warm_store_without_materialization 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[aggregate-cap] 
tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[updates] 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[updates] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_history_full_shows_reopen_clearing_closed_at 
tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[above-old-default-cap] 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_resolution.py::test_get_project_opens_warm_store_without_materialization 
tests/ace/tui/test_config_center_state.py::test_valid_pair_round_trips_with_exact_two_line_wire_value 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_valid_pair_round_trips_with_exact_two_line_wire_value 
tests/ace/tui/test_tmux_agent_modal.py::test_on_unmount_cancels_running_workers 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_on_unmount_cancels_running_workers 
tests/ace/tui/models/test_agent_tree_rendering.py::test_clan_and_member_rows_render_identity_colors_tribes_and_depth_guides 
tests/test_bead/test_cli_history.py::test_history_json_envelope_field_filter_and_newest_limit 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_rendering.py::test_clan_and_member_rows_render_identity_colors_tribes_and_depth_guides 
tests/test_bead/test_cli_resolution.py::test_bead_list_materializes_missing_split_sidecar 
tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_released_on_checkout_failure 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_released_on_checkout_failure 
tests/ace/tui/test_config_center_state.py::test_legacy_tasks_current_migrates_to_procs_on_load 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_legacy_tasks_current_migrates_to_procs_on_load 
tests/agents_sync/test_inventory.py::test_inventory_keeps_active_and_dismissed_states_but_rejects_imports 
[gw4] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_inventory_keeps_active_and_dismissed_states_but_rejects_imports 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_perf.py::test_perf_tiles_are_plain_and_do_not_navigate 
tests/ace/tui/test_config_center_state.py::test_persisted_xprompts_resume_maps_to_config 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_persisted_xprompts_resume_maps_to_config 
tests/ace/tui/test_tmux_agent_modal.py::test_panel_t_opens_tmux_agent_modal 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_history_json_envelope_field_filter_and_newest_limit 
tests/ace/tui/models/test_agent_tree_rendering.py::test_family_identity_color_requires_a_real_member 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_rendering.py::test_family_identity_color_requires_a_real_member 
tests/ace/tui/test_statistics_runners.py::test_summary_derives_current_limit_comparison_and_surfaces_caveats 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[above-old-default-cap] 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_runners.py::test_summary_derives_current_limit_comparison_and_surfaces_caveats 
tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_released_on_workflow_exception 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_released_on_workflow_exception 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_panel_t_opens_tmux_agent_modal 
tests/ace/tui/test_config_center_state.py::test_legacy_tasks_alternate_migrates_to_procs_on_load 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_legacy_tasks_alternate_migrates_to_procs_on_load 
tests/test_bead/test_cli_history.py::test_history_unknown_id_exits_nonzero_with_clear_message 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_resume.py::test_blocked_write_keeps_navigation_responsive_and_persists_latest 
tests/ace/tui/test_commits_pane_collection.py::test_explicit_limit_truncates_and_remains_visible 
[gw2] [ 99%] PASSED tests/test_bead/test_cli_resolution.py::test_bead_list_materializes_missing_split_sidecar 
tests/ace/tui/test_statistics_runners.py::test_timeline_uses_fixed_zero_baseline_peak_scale_and_bounded_columns 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_runners.py::test_timeline_uses_fixed_zero_baseline_peak_scale_and_bounded_columns 
tests/ace/tui/test_config_center_state.py::test_missing_and_unreadable_state_return_empty_history 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_missing_and_unreadable_state_return_empty_history 
tests/ace/tui/test_config_center_resume.py::test_write_failure_is_nonfatal_and_same_tab_can_retry 
tests/ace/tui/test_config_hub_catalog.py::test_config_subtab_order_omits_flags_when_rollout_is_off 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_catalog.py::test_config_subtab_order_omits_flags_when_rollout_is_off 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_validation_widget.py::test_live_validation_error_appears_and_clears 
tests/ace/tui/test_statistics_runners.py::test_runner_context_omits_partial_note_when_no_rows_were_skipped 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_runners.py::test_runner_context_omits_partial_note_when_no_rows_were_skipped 
tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[] 
tests/ace/tui/test_tmux_agent_modal.py::test_panel_t_outside_tmux_warns_instead_of_opening 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[] 
tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_not_released_on_dir_error 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_not_released_on_dir_error 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_list_focused_digits_select_admin_center_tabs 
tests/ace/tui/test_config_hub_catalog.py::test_config_catalog_does_not_resolve_flags_at_import 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_catalog.py::test_config_catalog_does_not_resolve_flags_at_import 
tests/ace/tui/models/test_agent_tree_rendering.py::test_clan_row_renders_unread_count_in_both_fold_states 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tree_rendering.py::test_clan_row_renders_unread_count_in_both_fold_states 
[gw1] [ 99%] PASSED tests/ace/tui/test_tmux_agent_modal.py::test_panel_t_outside_tmux_warns_instead_of_opening 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_history_unknown_id_exits_nonzero_with_clear_message 
tests/ace/tui/test_config_edit_modal_validation_widget.py::test_schema_validation_blocks_write 
tests/ace/tui/test_statistics_runners.py::test_occupancy_contains_every_exact_row_and_current_day_styles 
tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[missing\n] 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_runners.py::test_occupancy_contains_every_exact_row_and_current_day_styles 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[missing\n] 
tests/ace/tui/test_config_hub_catalog.py::test_admin_center_flags_call_site_uses_snapshot_enabled 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_catalog.py::test_admin_center_flags_call_site_uses_snapshot_enabled 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_list_focused_out_of_range_digits_are_no_ops 
tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_memory_glossary_bare_digit_selects_admin_tab_prefixed_follows 
tests/test_bead/test_cli_history.py::test_lost_notes_reports_overwrites_in_stable_order_and_supports_scope 
tests/ace/tui/test_statistics_runners.py::test_busiest_slices_sort_by_peak_average_then_time 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_runners.py::test_busiest_slices_sort_by_peak_average_then_time 
tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[tasks] 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[tasks] 
tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_not_released_on_claim_failure 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskWorkspaceLifecycle::test_workspace_not_released_on_claim_failure 
tests/agents_sync/test_inventory.py::test_portable_metadata_sanitizes_output_variables 
[gw4] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_portable_metadata_sanitizes_output_variables 
tests/ace/tui/test_statistics_runners.py::test_idle_and_carry_in_payloads_render_even_when_launch_views_are_empty 
tests/ace/tui/test_top_bar_order.py::test_top_bar_places_updates_indicator_left_of_model 
tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[tasks\nlogs\nconfig\n] 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_runners.py::test_idle_and_carry_in_payloads_render_even_when_launch_views_are_empty 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[tasks\nlogs\nconfig\n] 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_top_level_row_resolves_to_its_own_roster_unit 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_top_level_row_resolves_to_its_own_roster_unit 
[gw5] [ 99%] PASSED tests/agents_sync/test_publication.py::test_family_lane_and_member_requests_publish_identical_payloads 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_pane_widget.py::test_config_pane_loads_and_populates_tree 
tests/ace/tui/test_statistics_runners.py::test_missing_runner_payload_has_distinct_recovery_guidance 
tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[tasks\nmissing\n] 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_runners.py::test_missing_runner_payload_has_distinct_recovery_guidance 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[tasks\nmissing\n] 
tests/ace/tui/test_config_pane_widget.py::test_config_pane_restores_session_bookmark_by_path 
tests/agents_sync/test_publication.py::test_registered_family_lane_without_runs_is_rejected 
tests/ace/tui/test_sync.py::TestSyncTaskEnvVar::test_env_var_restored_after_success 
[gw5] [ 99%] PASSED tests/agents_sync/test_publication.py::test_registered_family_lane_without_runs_is_rejected 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskEnvVar::test_env_var_restored_after_success 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_resume.py::test_write_failure_is_nonfatal_and_same_tab_can_retry 
tests/ace/tui/test_statistics_runners.py::test_wide_and_narrow_compositions_switch_without_changing_data 
tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[\xff\n] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_lost_notes_reports_overwrites_in_stable_order_and_supports_scope 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_runners.py::test_wide_and_narrow_compositions_switch_without_changing_data 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[\xff\n] 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_validation_widget.py::test_schema_validation_blocks_write 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_memory_glossary_bare_digit_selects_admin_tab_prefixed_follows 
tests/ace/tui/test_config_center_resume.py::test_failed_resume_retains_prior_target_and_remains_retryable 
tests/agents_sync/test_publication.py::test_targeted_publication_rejects_request_for_empty_hood 
tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx] 
tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_memory_bare_digit_selects_admin_tab_prefixed_follows 
[gw5] [ 99%] PASSED tests/agents_sync/test_publication.py::test_targeted_publication_rejects_request_for_empty_hood 
tests/ace/tui/test_statistics_scope_header.py::test_statistics_view_catalog_is_the_authoritative_ordered_source 
tests/test_bead/test_cli_history.py::test_lost_notes_ignores_append_only_chain 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_family_member_resolves_to_family_roster_unit 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_malformed_or_oversized_state_returns_empty_history[xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx] 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_family_member_resolves_to_family_roster_unit 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_scope_header.py::test_statistics_view_catalog_is_the_authoritative_ordered_source 
tests/ace/tui/test_config_edit_modal_vim_widget.py::test_two_stage_escape_backs_out_of_modal 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_list_focused_out_of_range_digits_are_no_ops 
tests/ace/tui/test_sync.py::TestSyncTaskEnvVar::test_env_var_restored_after_failure 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskEnvVar::test_env_var_restored_after_failure 
[gw1] [ 99%] PASSED tests/ace/tui/test_top_bar_order.py::test_top_bar_places_updates_indicator_left_of_model 
tests/ace/tui/test_config_center_state.py::test_degenerate_duplicate_pair_keeps_current_and_drops_alternate 
tests/ace/tui/test_statistics_scope_header.py::test_statistics_view_description_text_uses_cell_width 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_scope_header.py::test_statistics_view_description_text_uses_cell_width 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_degenerate_duplicate_pair_keeps_current_and_drops_alternate 
tests/agents_sync/test_publication.py::test_full_reconciliation_discovers_only_commit_eligible_hoods 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_digits_type_in_an_opened_filter 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_explicit_limit_truncates_and_remains_visible 
tests/ace/tui/test_statistics_scope_header.py::test_statistics_view_description_text_uses_terminal_cells_not_python_len 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_lost_notes_ignores_append_only_chain 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_scope_header.py::test_statistics_view_description_text_uses_terminal_cells_not_python_len 
tests/ace/tui/test_config_center_state.py::test_save_atomically_replaces_existing_state 
tests/agents_sync/test_inventory.py::test_primary_remote_resolution_is_optional[0-git@github.com:acme/project.git\n-git@github.com:acme/project.git] 
[gw4] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_primary_remote_resolution_is_optional[0-git@github.com:acme/project.git\n-git@github.com:acme/project.git] 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_save_atomically_replaces_existing_state 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_memory_bare_digit_selects_admin_tab_prefixed_follows 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_clan_member_resolves_to_clan_container 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_clan_member_resolves_to_clan_container 
tests/ace/tui/test_top_bar_order.py::test_mixed_updates_indicator_keeps_narrow_top_bar_in_bounds 
tests/ace/tui/test_commits_pane_collection.py::test_type_filter_uses_uncapped_backend_candidates_before_host_limit 
tests/ace/tui/test_statistics_scope_header.py::test_description_rail_repaints_only_when_the_variant_changes 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_scope_header.py::test_description_rail_repaints_only_when_the_variant_changes 
tests/test_bead/test_cli_history.py::test_lost_notes_restore_is_provenanced_and_idempotent 
tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_trailing_newlines_stripped 
[gw12] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_trailing_newlines_stripped 
tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_snippets_bare_digit_still_follows_locally 
tests/ace/tui/test_sync.py::TestSyncTaskEnvVar::test_env_var_preserves_previous_value 
[gw8] [ 99%] PASSED tests/ace/tui/test_sync.py::TestSyncTaskEnvVar::test_env_var_preserves_previous_value 
tests/ace/tui/test_statistics_scope_header.py::test_scope_renderables_cover_range_group_project_and_status 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_scope_header.py::test_scope_renderables_cover_range_group_project_and_status 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_snippets_bare_digit_still_follows_locally 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_lost_notes_restore_is_provenanced_and_idempotent 
tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_into_existing_section 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_pane_widget.py::test_config_pane_restores_session_bookmark_by_path 
[gw12] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_into_existing_section 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_resume.py::test_failed_resume_retains_prior_target_and_remains_retryable 
tests/ace/tui/test_config_hub_pane.py::test_numbered_config_strip_fits_each_layout_tier[97-full] 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_pane.py::test_numbered_config_strip_fits_each_layout_tier[97-full] 
[gw5] [ 99%] PASSED tests/agents_sync/test_publication.py::test_full_reconciliation_discovers_only_commit_eligible_hoods 
tests/ace/tui/test_statistics_scope_header.py::test_scope_resize_only_repaints_when_compact_mode_changes 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_scope_header.py::test_scope_resize_only_repaints_when_compact_mode_changes 
tests/test_bead/test_cli_history.py::test_lost_notes_restore_yes_skips_non_tty_confirmation 
tests/ace/tui/test_config_hub_pane.py::test_numbered_config_strip_fits_each_layout_tier[73-compact] 
tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_narrows_tree 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_pane.py::test_numbered_config_strip_fits_each_layout_tier[73-compact] 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_workflow_child_resolves_to_workflow_root 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_workflow_child_resolves_to_workflow_root 
tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_index_query_picks_up_appended_plan_submitted_at 
tests/ace/tui/test_config_center_resume.py::test_custom_opener_opens_home_resumes_and_is_displayed 
tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_first_alphabetically 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_two_stage_escape_backs_out_of_modal 
[gw12] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_first_alphabetically 
tests/agents_sync/test_inventory_history.py::test_inventory_synthesizes_run_for_linked_commit_without_local_artifact 
tests/ace/tui/test_config_hub_pane.py::test_numbered_config_strip_fits_each_layout_tier[70-micro] 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_pane.py::test_numbered_config_strip_fits_each_layout_tier[70-micro] 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_type_filter_uses_uncapped_backend_candidates_before_host_limit 
tests/ace/tui/test_statistics_scope_header.py::test_runner_resize_only_repaints_when_composition_threshold_changes 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_scope_header.py::test_runner_resize_only_repaints_when_composition_threshold_changes 
tests/ace/tui/test_config_hub_pane.py::test_opening_config_constructs_only_the_active_child 
tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_last_alphabetically 
tests/ace/tui/test_config_edit_modal_vim_widget.py::test_enter_submits_from_normal_mode 
[gw12] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_last_alphabetically 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_lost_notes_restore_yes_skips_non_tty_confirmation 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_digits_type_in_an_opened_filter 
[gw5] [ 99%] PASSED tests/agents_sync/test_inventory_history.py::test_inventory_synthesizes_run_for_linked_commit_without_local_artifact 
tests/ace/tui/test_commits_pane_collection.py::test_relative_filter_reparse_reuses_snapshot_cache_key 
[gw11] [ 99%] PASSED tests/ace/tui/test_commits_pane_collection.py::test_relative_filter_reparse_reuses_snapshot_cache_key 
tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_into_empty_section 
tests/ace/tui/test_statistics_scope_header.py::test_perf_resize_only_repaints_when_composition_threshold_changes 
tests/agents_sync/test_inventory.py::test_primary_remote_resolution_is_optional[0-\n-None] 
[gw4] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_primary_remote_resolution_is_optional[0-\n-None] 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_scope_header.py::test_perf_resize_only_repaints_when_composition_threshold_changes 
[gw12] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_into_empty_section 
tests/test_bead/test_cli_history.py::test_lost_notes_declined_confirmation_writes_nothing 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_row_without_a_presented_anchor_keeps_label_but_has_no_cursor_unit 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_row_without_a_presented_anchor_keeps_label_but_has_no_cursor_unit 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_brackets_cycle_config_subtabs_from_xprompt_list_and_filter 
tests/agents_sync/test_inventory_history.py::test_inventory_diagnoses_unrepresentable_family_history_without_phantom_run 
[gw5] [ 99%] PASSED tests/agents_sync/test_inventory_history.py::test_inventory_diagnoses_unrepresentable_family_history_without_phantom_run 
tests/ace/tui/test_config_center_session.py::test_distinct_ace_apps_do_not_share_session_state 
[gw8] [ 99%] PASSED tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_index_query_picks_up_appended_plan_submitted_at 
tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_no_xprompts_section 
[gw12] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_no_xprompts_section 
tests/ace/tui/test_statistics_scope_header.py::test_description_width_changes_do_not_repaint_statistics_body 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_scope_header.py::test_description_width_changes_do_not_repaint_statistics_body 
tests/agents_sync/test_inventory_history.py::test_inventory_preserves_legacy_member_attribution_beside_family_lane_history 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_lost_notes_declined_confirmation_writes_nothing 
tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_with_inputs 
[gw12] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestInsertXpromptIntoConfig::test_insert_with_inputs 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_resume.py::test_custom_opener_opens_home_resumes_and_is_displayed 
tests/ace/tui/test_statistics_view_number_select.py::test_number_prefix_selects_second_seventh_and_eighth_views 
[gw5] [ 99%] PASSED tests/agents_sync/test_inventory_history.py::test_inventory_preserves_legacy_member_attribution_beside_family_lane_history 
tests/test_bead/test_cli_history.py::test_lost_notes_unknown_scoped_id_exits_nonzero 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_group_target_is_explicitly_labeled_as_a_group 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_group_target_is_explicitly_labeled_as_a_group 
tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_loader_agent_plan_times_reflects_mid_run_update 
tests/ace/tui/test_config_hub_catalog.py::test_registered_catalog_is_alphabetized_with_all_first 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_hub_catalog.py::test_registered_catalog_is_alphabetized_with_all_first 
tests/ace/tui/test_config_center_resume.py::test_literal_opener_remains_typeable_and_cannot_nest_modal 
[gw1] [ 99%] PASSED tests/ace/tui/test_top_bar_order.py::test_mixed_updates_indicator_keeps_narrow_top_bar_in_bounds 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_pane.py::test_opening_config_constructs_only_the_active_child 
tests/agents_sync/test_inventory_history.py::test_inventory_disambiguates_historical_runs_that_share_a_timestamp_id 
tests/ace/tui/test_config_hub_catalog.py::test_config_subtab_order_includes_flags_when_rollout_is_on 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_hub_catalog.py::test_config_subtab_order_includes_flags_when_rollout_is_on 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_lost_notes_unknown_scoped_id_exits_nonzero 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_enter_submits_from_normal_mode 
tests/ace/tui/test_config_hub_pane.py::test_subtab_cycle_caches_children_and_does_not_reload 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_pane.py::test_subtab_cycle_caches_children_and_does_not_reload 
[gw5] [ 99%] PASSED tests/agents_sync/test_inventory_history.py::test_inventory_disambiguates_historical_runs_that_share_a_timestamp_id 
tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds 
tests/test_bead/test_cli_history.py::test_history_rejects_negative_limit[--limit] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_history_rejects_negative_limit[--limit] 
tests/ace/tui/test_config_hub_catalog.py::test_registered_specs_carry_reviewed_full_and_compact_copy 
tests/ace/tui/test_config_edit_modal_vim_widget.py::test_normal_mode_edit_fires_live_validation 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_hub_catalog.py::test_registered_specs_carry_reviewed_full_and_compact_copy 
tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_uses_remembered_or_first_stop[stops0-remembered0-expected0] 
tests/agents_sync/test_inventory.py::test_primary_remote_resolution_is_optional[1-git@github.com:acme/project.git\n-None] 
[gw0] [ 99%] PASSED tests/ace/tui/models/test_agent_tribe_entry_target.py::test_shared_resolver_uses_remembered_or_first_stop[stops0-remembered0-expected0] 
[gw4] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_primary_remote_resolution_is_optional[1-git@github.com:acme/project.git\n-None] 
[gw8] [ 99%] PASSED tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_loader_agent_plan_times_reflects_mid_run_update 
tests/ace/tui/test_config_hub_pane.py::test_failed_child_mount_leaves_previous_child_visible 
[gw11] [ 99%] PASSED tests/ace/tui/test_config_center_session.py::test_distinct_ace_apps_do_not_share_session_state 
tests/agents_sync/test_inventory_history.py::test_inventory_diagnoses_and_drops_stale_solo_family_metadata 
tests/ace/tui/test_config_hub_catalog.py::test_active_specs_keep_catalog_derived_description_order 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_hub_catalog.py::test_active_specs_keep_catalog_derived_description_order 
tests/test_bead/test_cli_history.py::test_history_rejects_negative_limit[-n] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_history.py::test_history_rejects_negative_limit[-n] 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_pane.py::test_failed_child_mount_leaves_previous_child_visible 
tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[config] 
[gw11] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[config] 
[gw5] [ 99%] PASSED tests/agents_sync/test_inventory_history.py::test_inventory_diagnoses_and_drops_stale_solo_family_metadata 
tests/test_bead/test_cli_id_shorthand.py::test_show_and_history_accept_unique_shorthand 
tests/ace/tui/test_config_hub_catalog.py::test_config_subtab_description_text_uses_cell_width 
tests/ace/tui/test_config_hub_pane.py::test_direct_entry_opens_requested_child_once 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_hub_catalog.py::test_config_subtab_description_text_uses_cell_width 
tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_index_query_picks_up_appended_feedback_submitted_at 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_hub_pane.py::test_direct_entry_opens_requested_child_once 
tests/agents_sync/test_inventory.py::test_is_imported_accepts_current_bundle_provenance_markers[marker2] 
tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[logs] 
[gw0] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_is_imported_accepts_current_bundle_provenance_markers[marker2] 
[gw11] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[logs] 
tests/agents_sync/test_inventory_history.py::test_inventory_selection_excludes_and_diagnoses_classifier_errors 
[gw5] [ 99%] PASSED tests/agents_sync/test_inventory_history.py::test_inventory_selection_excludes_and_diagnoses_classifier_errors 
tests/ace/tui/test_config_pane_widget.py::test_config_pane_edit_sibling_repos_opens_normal_editor 
[gw1] [ 99%] PASSED tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds 
tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[procs] 
[gw11] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[procs] 
tests/agents_sync/test_links.py::test_family_member_commit_tag_links_to_lane_page_without_member_anchor 
[gw5] [ 99%] PASSED tests/agents_sync/test_links.py::test_family_member_commit_tag_links_to_lane_page_without_member_anchor 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_id_shorthand.py::test_show_and_history_accept_unique_shorthand 
tests/ace/tui/test_tui_log_setup.py::test_install_attaches_handler 
[gw1] [ 99%] PASSED tests/ace/tui/test_tui_log_setup.py::test_install_attaches_handler 
tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[projects] 
[gw11] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[projects] 
[gw8] [ 99%] PASSED tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_index_query_picks_up_appended_feedback_submitted_at 
tests/agents_sync/test_links.py::test_commit_tag_falls_back_to_global_label_for_non_hosted_sidecar 
[gw5] [ 99%] PASSED tests/agents_sync/test_links.py::test_commit_tag_falls_back_to_global_label_for_non_hosted_sidecar 
tests/test_bead/test_cli_id_shorthand.py::test_create_update_close_and_remove_canonicalize_shorthand 
tests/agents_sync/test_inventory.py::test_dismissed_inventory_rejects_legacy_step_output_import_marker 
[gw0] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_dismissed_inventory_rejects_legacy_step_output_import_marker 
tests/agents_sync/test_inventory.py::test_primary_remote_resolution_swallows_git_failure 
[gw4] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_primary_remote_resolution_swallows_git_failure 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_narrows_tree 
tests/ace/tui/test_tui_log_setup.py::test_install_is_idempotent 
[gw1] [ 99%] PASSED tests/ace/tui/test_tui_log_setup.py::test_install_is_idempotent 
tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_updates_title_match_count 
tests/ace/tui/test_timestamps_builder.py::TestCollapsed::test_collapsed_shows_folded_count 
[gw8] [ 99%] PASSED tests/ace/tui/test_timestamps_builder.py::TestCollapsed::test_collapsed_shows_folded_count 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_brackets_cycle_config_subtabs_from_xprompt_list_and_filter 
tests/ace/tui/test_tui_log_setup.py::test_warning_lands_in_tui_log 
[gw1] [ 99%] PASSED tests/ace/tui/test_tui_log_setup.py::test_warning_lands_in_tui_log 
tests/ace/tui/test_config_pane_widget.py::test_config_pane_jump_selects_matching_path 
tests/ace/tui/test_xprompt_browser_load_keymap.py::test_tab_switches_main_tab_after_typed_filter_text 
tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[statistics] 
tests/agents_sync/test_inventory.py::test_inventory_relationships_skip_tribe_wait_targets 
[gw0] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_inventory_relationships_skip_tribe_wait_targets 
tests/agents_sync/test_links.py::test_member_commit_tag_falls_back_to_lane_for_non_hosted_sidecar 
[gw11] [ 99%] PASSED tests/ace/tui/test_config_center_state.py::test_valid_single_tab_round_trips_with_exact_wire_value[statistics] 
[gw5] [ 99%] PASSED tests/agents_sync/test_links.py::test_member_commit_tag_falls_back_to_lane_for_non_hosted_sidecar 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_pane_widget.py::test_config_pane_edit_sibling_repos_opens_normal_editor 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_resume.py::test_literal_opener_remains_typeable_and_cannot_nest_modal 
tests/ace/tui/test_timestamps_builder.py::TestCollapsed::test_collapsed_no_timestamps_shows_nothing 
[gw8] [ 99%] PASSED tests/ace/tui/test_timestamps_builder.py::TestCollapsed::test_collapsed_no_timestamps_shows_nothing 
tests/ace/tui/test_tui_log_setup.py::test_exception_traceback_lands_in_tui_log 
[gw1] [ 99%] PASSED tests/ace/tui/test_tui_log_setup.py::test_exception_traceback_lands_in_tui_log 
tests/ace/tui/test_statistics_view_number_select.py::test_non_digit_cancels_prefix_and_continues_to_modal[q] 
[gw9] [ 99%] PASSED tests/test_bead/test_cli_id_shorthand.py::test_create_update_close_and_remove_canonicalize_shorthand 
tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_successful_write_toast 
tests/ace/tui/test_config_center_session.py::test_provisional_display_does_not_replace_requested_selection 
tests/ace/tui/test_statistics_view_number_select.py::test_repeated_prefix_rearms_before_view_selection 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_session.py::test_provisional_display_does_not_replace_requested_selection 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_number_prefix_selects_second_seventh_and_eighth_views 
tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_short_form_blank_lines 
[gw9] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_short_form_blank_lines 
tests/ace/tui/test_config_center_session.py::test_direct_config_center_modals_get_independent_session_state 
[gw13] [ 99%] PASSED tests/ace/tui/test_config_center_session.py::test_direct_config_center_modals_get_independent_session_state 
tests/ace/tui/test_tui_log_setup.py::test_info_below_threshold_is_filtered 
[gw1] [ 99%] PASSED tests/ace/tui/test_tui_log_setup.py::test_info_below_threshold_is_filtered 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_normal_mode_edit_fires_live_validation 
tests/agents_sync/test_inventory.py::test_is_imported_accepts_current_bundle_provenance_markers[marker0] 
tests/ace/tui/test_statistics_view_number_select.py::test_number_prefix_ignores_out_of_range_digit 
[gw4] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_is_imported_accepts_current_bundle_provenance_markers[marker0] 
tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_long_form_multiple_inputs 
tests/ace/tui/test_config_edit_modal_vim_widget.py::test_ctrl_r_toggles_reset_from_insert_mode 
tests/agents_sync/test_inventory_history.py::test_inventory_discovers_real_legacy_names_and_reconciles_unrelated_hood 
[gw9] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_long_form_multiple_inputs 
tests/ace/tui/test_config_edit_modal_vim_widget.py::test_normal_mode_dd_edits_yaml_editor 
tests/ace/tui/test_statistics_view_number_select.py::test_bare_digit_keeps_switching_admin_center_tabs 
tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_long_form_with_inputs 
[gw1] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_long_form_with_inputs 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_pane_widget.py::test_config_pane_jump_selects_matching_path 
tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_short_form_multiline 
[gw9] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_short_form_multiline 
[gw0] [ 99%] PASSED tests/agents_sync/test_inventory_history.py::test_inventory_discovers_real_legacy_names_and_reconciles_unrelated_hood 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_browser_load_keymap.py::test_tab_switches_main_tab_after_typed_filter_text 
tests/ace/tui/test_config_pane_widget.py::test_config_pane_edit_opens_edit_modal 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_updates_title_match_count 
[gw11] [ 99%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_non_digit_cancels_prefix_and_continues_to_modal[q] 
tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_short_form_no_inputs 
[gw10] [ 99%] PASSED tests/ace/tui/test_xprompt_config_insert.py::TestGenerateXpromptYaml::test_short_form_no_inputs 
[gw5] [ 99%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_repeated_prefix_rearms_before_view_selection 
tests/ace/tui/test_config_pane_widget.py::test_config_filter_brackets_cycle_subtabs_and_tab_switches_main_tab 
tests/ace/tui/test_statistics_view_number_select.py::test_non_digit_cancels_prefix_and_continues_to_modal[escape] 
tests/ace/tui/test_config_center_session.py::test_ace_app_reuses_one_session_state_across_modals 
tests/ace/tui/test_config_pane_widget.py::test_config_pane_modified_only_toggle 
tests/agents_sync/test_inventory.py::test_is_imported_accepts_current_bundle_provenance_markers[marker1] 
[gw4] [ 99%] PASSED tests/agents_sync/test_inventory.py::test_is_imported_accepts_current_bundle_provenance_markers[marker1] 
[gw13] [ 99%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_bare_digit_keeps_switching_admin_center_tabs 
[gw6] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_normal_mode_dd_edits_yaml_editor 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_successful_write_toast 
[gw3] [ 99%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_number_prefix_ignores_out_of_range_digit 
tests/ace/tui/test_config_center_session.py::test_home_only_open_does_not_create_panes_or_mutate_bookmarks 
tests/ace/tui/test_config_edit_modal_vim_widget.py::test_ctrl_s_confirms_from_yaml_editor 
[gw5] [ 99%] PASSED tests/ace/tui/test_config_center_session.py::test_ace_app_reuses_one_session_state_across_modals 
[gw8] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_ctrl_r_toggles_reset_from_insert_mode 
[gw2] [ 99%] PASSED tests/ace/tui/test_config_pane_widget.py::test_config_pane_edit_opens_edit_modal 
[gw12] [ 99%] PASSED tests/ace/tui/test_config_center_session.py::test_home_only_open_does_not_create_panes_or_mutate_bookmarks 
tests/ace/tui/test_config_hub_catalog.py::test_catalog_drops_top_level_xprompts_and_maps_legacy_resume 
[gw8] [ 99%] PASSED tests/ace/tui/test_config_hub_catalog.py::test_catalog_drops_top_level_xprompts_and_maps_legacy_resume 
[gw3] [ 99%] PASSED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_ctrl_s_confirms_from_yaml_editor 
[gw11] [ 99%] PASSED tests/ace/tui/test_statistics_view_number_select.py::test_non_digit_cancels_prefix_and_continues_to_modal[escape] 
[gw7] [ 99%] PASSED tests/ace/tui/test_config_pane_widget.py::test_config_filter_brackets_cycle_subtabs_and_tab_switches_main_tab 
[gw0] [100%] PASSED tests/ace/tui/test_config_pane_widget.py::test_config_pane_modified_only_toggle 

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.



=================================== FAILURES ===================================
_______________ test_contract_manifest_matches_marker_selection ________________
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

    def test_contract_manifest_matches_marker_selection() -> None:
        tool = _load_refresh_tool()
    
        current = tool.collect_contract_files()
        committed = _read_manifest()
    
>       assert current == committed, (
            "tests/contract_manifest.txt is stale; run "
            "`just refresh-contract-manifest`.\n"
            f"marker currently selects: {current}\n"
            f"committed manifest:       {committed}"
        )
E       AssertionError: tests/contract_manifest.txt is stale; run `just refresh-contract-manifest`.
E         marker currently selects: []
E         committed manifest:       ['tests/ace/tui/test_visual_fixture_host_paths.py', 'tests/test_agent_stop_hook_config.py', 'tests/test_agent_tribe_terminology.py', 'tests/test_check_sase_core_rs_bindings_tool.py', 'tests/test_ci_bootstrap_sidecars_tool.py', 'tests/test_commit_type_tag_contract.py', 'tests/test_config_schema.py', 'tests/test_config_schema_ace.py', 'tests/test_config_schema_beads.py', 'tests/test_config_schema_extensions.py', 'tests/test_config_schema_gate_shell.py', 'tests/test_config_schema_keymaps.py', 'tests/test_config_schema_runtime_limits.py', 'tests/test_core_finalizer_facade.py', 'tests/test_demo_media_postprocessor.py', 'tests/test_gemini_active_surface_guard.py', 'tests/test_github_actions_ci_master_gate.py', 'tests/test_github_actions_ci_workflow.py', 'tests/test_github_actions_publish.py', 'tests/test_github_actions_setup_sase.py', 'tests/test_justfile_lint.py', 'tests/test_justfile_sase_core_dir.py', 'tests/test_patch_stitch_terminology_audit.py', 'tests/test_probe_core_floor_tool.py', 'tests/test_project_display_presentation_audit.py', 'tests/test_ratchet_core_revision_tool.py', 'tests/test_ratchet_core_window_source_normalization.py', 'tests/test_ratchet_core_window_tool_core.py', 'tests/test_ratchet_core_window_tool_guardrails.py', 'tests/test_ratchet_core_window_tool_modes.py', 'tests/test_ratchet_core_window_tool_reconciliation.py', 'tests/test_ruff_config.py', 'tests/test_run_pytest_command.py', 'tests/test_run_pytest_contention.py', 'tests/test_run_pytest_health.py', 'tests/test_run_pytest_main.py', 'tests/test_run_pytest_scoped.py', 'tests/test_run_pytest_tmpdir.py', 'tests/test_run_pytest_workers.py', 'tests/test_rust_install_cleanup.py', 'tests/test_sase_bead_tool.py', 'tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py', 'tests/test_sase_core_rs_bead_resolution_smoke_tool.py', 'tests/test_sase_core_rs_feature_flag_state_smoke_tool.py', 'tests/test_sase_core_rs_glossary_line_break_smoke_tool.py', 'tests/test_sase_core_rs_plan_header_smoke_tool.py', 'tests/test_sase_core_rs_telemetry_smoke_tool.py', 'tests/test_sase_core_wheel_cache_tool.py', 'tests/test_sase_migrate_statuses.py', 'tests/test_sdd_canonical_layout.py', 'tests/test_setup_required_plugins_tool.py', 'tests/test_suite_gate.py', 'tests/test_suite_gate_budget.py', 'tests/test_suite_gate_lease.py', 'tests/test_suite_gate_reclaim.py', 'tests/test_timezone_display_guard.py', 'tests/test_validate_changelog_tool.py', 'tests/test_validate_dependency_group_tool.py', 'tests/test_validate_sase_core_rs_contracts_tool.py', 'tests/test_validate_sase_core_rs_environment_tool.py', 'tests/test_validate_sase_core_rs_tool.py', 'tests/test_validate_sase_core_rs_version_tool.py', 'tests/test_validate_test_environment_tool.py']
E       assert [] == ['tests/ace/t...ract.py', ...]
E         
E         Right contains 63 more items, first extra item: 'tests/ace/tui/test_visual_fixture_host_paths.py'
E         
E         Full diff:
E         + []
E         - [
E         -     'tests/ace/tui/test_visual_fixture_host_paths.py',...
E         
E         ...Full output truncated (63 lines hidden), use '-vv' to show

tests/test_contract_manifest.py:204: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:472: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=985636) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/actions/update_toast.py:87: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py::test_tab_completes_bead_plus_to_plus_one
tests/completion/test_zsh_smoke.py::test_dynamic_slot_fetches_fixture_candidates_and_caches
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask #zz-"ask #zzz-fixture-xprompt"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask %mo-"ask %model"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask @file:e-"ask @file:explicit:abc123"]
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=985636) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 0 poisoning change(s) across 0 test(s); 53135 warming mutation(s) filtered; 558 cooling mutation(s) filtered; 1539 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.pytest_cache/sase-global-leaks.json -
============================= slowest 20 durations =============================
88.34s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
42.96s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
31.74s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
28.51s teardown tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
23.69s call     tests/test_user_question_gates.py::test_shell_backed_question_settles_its_gate_shell_and_streams_output
23.09s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
22.16s call     tests/completion/test_install_zsh.py::test_real_zsh_zcompile_and_registration
21.60s call     tests/test_proc_env_isolation.py::test_sase_ml_file_families_ignore_inherited_live_proc_env
21.51s call     tests/gate_shell/test_settlement_followup.py::test_done_marker_carries_the_followup_outcome_and_agent
18.33s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_noop_closes_without_restart
16.94s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_skipped_editables_with_wheel_core_open_mixed_preview
16.73s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
16.67s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_confirm_executes_and_restarts
16.60s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_true_noop_does_not_restart
16.54s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes
16.53s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_cancel_keeps_admin_center_open
16.43s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_dev_update_shows_all_commit_groups
15.87s call     tests/gate_shell/test_settlement_followup.py::test_creator_live_leaves_the_workspace_claim_alone
15.76s call     tests/test_agent_name_migration.py::test_migrates_artifacts_refs_notifications_and_history
15.74s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
=========================== short test summary info ============================
FAILED tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
==== 1 failed, 38948 passed, 14 skipped, 80 warnings in 1373.35s (0:22:53) =====
error: recipe `test-cost` failed on line 420 with exit code 1
error: recipe `check-full` failed on line 684 with exit code 1

