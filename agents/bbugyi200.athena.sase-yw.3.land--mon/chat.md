# Chat History - ace-run (sase-yw.3.land--mon)

- **TIMESTAMP:** 2026-09-09 17:28:26 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-yw.3.land--mon

## Prompt

sase monitor start --command 'core_repo="/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core"; main_repo="/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11"; core_status=0; visual_status=0; (cd "$core_repo" && just check) || core_status=$?; echo "SASE_YW3_CORE_CHECK_STATUS=$core_status"; (cd "$main_repo" && just test-visual) || visual_status=$?; echo "SASE_YW3_VISUAL_STATUS=$visual_status"; if [ "$core_status" -ne 0 ] || [ "$visual_status" -ne 0 ]; then exit 1; fi' --reason 'Reproduce both unrelated PROPOSED FOLLOW-UP reports before task classification'

## Response

./scripts/check.sh all
    Blocking waiting for file lock on build directory
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 34.36s
    Finished `test` profile [unoptimized + debuginfo] target(s) in 4.13s
     Running unittests src/lib.rs (/mnt/poseidon/cargo-target/debug/deps/sase_core-0723d6ffde64b841)

running 2360 tests
test agent_archive::tests::validates_capabilities_against_persisted_inputs ... ok
test agent_clan_tribe::tests::absent_declarations_resolve_to_none ... ok
test agent_clan_tribe::tests::absent_summaries_resolve_to_none ... ok
test agent_clan_tribe::tests::latest_explicit_declaration_wins_and_omissions_do_not_clear ... ok
test agent_clan_tribe::tests::latest_explicit_summary_wins_and_omissions_do_not_clear ... ok
test agent_archive::tests::validates_archive_key_and_visibility ... ok
test agent_clan_tribe::tests::repeated_summaries_and_generations_are_scoped ... ok
test agent_clan_tribe::tests::stable_identity_breaks_equal_timestamp_summary_ties ... ok
test agent_clan_tribe::tests::repeated_declarations_and_generations_are_scoped ... ok
test agent_clan_tribe::tests::stable_identity_breaks_equal_timestamp_ties ... ok
test agent_cleanup::execution::tests::bundle_filename_and_shard_match_dismissed_layout ... ok
test agent_cleanup::execution::tests::release_workspace_text_removes_empty_running_field ... ok
test agent_cleanup::execution::tests::release_workspace_text_removes_matching_claim_and_cleans_field ... ok
test agent_cleanup::execution::tests::delete_agent_artifact_markers_removes_loader_files_only ... ok
test agent_cleanup::execution::tests::mark_running_hook_mentor_and_comment_suffixes_as_killed ... ok
test agent_cleanup::execution::tests::save_dismissed_bundle_json_writes_sharded_pretty_json ... ok
test agent_cleanup::execution::tests::save_dismissed_bundle_json_replaces_existing_bundle ... ok
test agent_cleanup::planner::tests::broad_scopes_keep_workflow_step_children_cascade_only ... ok
test agent_cleanup::planner::tests::broad_scopes_act_on_family_member_child_rows_directly ... ok
test agent_cleanup::planner::tests::clan_scope_deduplicates_already_selected_live_monitor ... ok
test agent_cleanup::planner::tests::clan_scope_dismisses_sequential_family_and_monitor_rows ... ok
test agent_cleanup::planner::tests::all_panels_kill_and_dismiss_partitions_targets ... ok
test agent_cleanup::planner::tests::clan_scope_keeps_active_parallel_family_root_from_dismissal ... ok
test agent_cleanup::planner::tests::clan_scope_filters_generation_and_partitions_with_workflow_cascade ... ok
test agent_cleanup::planner::tests::completed_workflow_parent_gets_timestamp_and_workflow_releases ... ok
test agent_cleanup::planner::tests::clan_scope_without_generation_selects_all_generations ... ok
test agent_cleanup::planner::tests::direct_child_side_effects_include_child_not_siblings ... ok
test agent_cleanup::planner::tests::custom_scope_owner_does_not_stop_unrelated_sibling_monitor ... ok
test agent_cleanup::planner::tests::direct_live_monitor_selection_is_a_monitor_stop ... ok
test agent_cleanup::planner::tests::dismiss_side_effects_allow_duplicate_historical_names ... ok
test agent_cleanup::planner::tests::direct_workflow_child_does_not_release_parent_workspace_claim ... ok
test agent_cleanup::planner::tests::dismissable_statuses_include_stopped ... ok
test agent_cleanup::planner::tests::dismiss_side_effects_preserve_names ... ok
test agent_cleanup::planner::tests::dismissable_statuses_include_tale_done ... ok
test agent_cleanup::planner::tests::dismissing_parallel_root_cascades_only_after_members_finish ... ok
test agent_cleanup::planner::tests::explicit_child_only_completed_target_becomes_dismiss_item ... ok
test agent_cleanup::planner::tests::explicit_child_only_running_target_becomes_kill_item ... ok
test agent_cleanup::planner::tests::explicit_identities_dismiss_sequential_family_and_monitor_rows ... ok
test agent_cleanup::planner::tests::explicit_identities_select_only_marked_targets ... ok
test agent_cleanup::planner::tests::focused_panel_selects_matching_tribe_and_dismisses_completed ... ok
test agent_cleanup::planner::tests::no_op_plan_reports_none_severity ... ok
test agent_cleanup::planner::tests::killing_one_parallel_member_leaves_root_and_siblings_untouched ... ok
test agent_cleanup::planner::tests::rejects_previous_cleanup_wire_schema ... ok
test agent_cleanup::planner::tests::parallel_family_root_kill_cascades_to_live_members_only ... ok
test agent_cleanup::planner::tests::running_owner_kill_releases_owner_workspace_not_monitor_claim ... ok
test agent_cleanup::planner::tests::stopped_row_is_dismissed_not_killed_or_failed ... ok
test agent_cleanup::planner::tests::terminal_monitor_is_dismissed_not_stopped ... ok
test agent_cleanup::planner::tests::selected_owner_cascades_to_nested_live_monitor ... ok
test agent_cleanup::planner::tests::tribe_scope_uses_parent_tribe_for_workflow_children_but_skips_child_directly ... ok
test agent_cleanup::planner::tests::unknown_kill_kind_is_skipped ... ok
test agent_cleanup::planner::tests::workflow_parent_cascade_deduplicates_child_inputs ... ok
test agent_family::tests::absent_parent_reports_absent ... ok
test agent_family::tests::dismissed_parent_reports_dismissed ... ok
test agent_family::tests::newest_terminal_visible_parent_wins ... ok
test agent_family::tests::duplicate_newest_timestamp_reports_ambiguous ... ok
test agent_family::tests::non_terminal_parent_reports_running ... ok
test agent_archive::tests::query_agent_archive_returns_paged_summary_rows ... ok
test agent_group_archive::tests::missing_ref_prompt_preview_loads_as_none ... ok
test agent_group_archive::tests::load_group_keeps_refs_when_bundle_files_are_missing ... ok
test agent_group_archive::tests::missing_group_name_loads_as_none ... ok
test agent_identity::identity::tests::explicit_owner_prevents_mismatched_strip ... ok
test agent_identity::identity::tests::family_hood_ancestors_and_membership_are_canonical ... ok
test agent_group_archive::tests::corrupt_and_missing_group_files_are_tolerated ... ok
test agent_group_archive::tests::delete_group_removes_only_requested_metadata_record ... ok
test agent_identity::identity::tests::globalization_normalizes_archive_and_round_trips ... ok
test agent_group_archive::tests::mark_group_revived_preserves_metadata ... ok
test agent_identity::identity::tests::link_targets_distinguish_family_and_solo ... ok
test agent_identity::identity::tests::hood_membership_never_raises_for_historical_candidates ... ok
test agent_identity::identity::tests::localization_covers_all_owner_cases ... ok
test agent_identity::identity::tests::owner_roots_validate_and_parse_longest_prefix ... ok
test agent_identity::identity::tests::owner_aware_hood_ancestors_membership_and_links_use_semantic_remainder ... ok
test agent_group_archive::tests::save_list_and_load_preserve_group_name ... ok
test agent_group_archive::tests::recent_groups_replace_same_group_id ... ok
test agent_group_archive::tests::recent_groups_tolerate_corrupt_files_and_mark_revived ... ok
test agent_identity::identity::tests::username_and_owner_validation_matrix ... ok
test agent_archive::tests::mark_agent_archive_bundles_revived_updates_projection_without_bundle_mutation ... ok
test agent_identity::identity::tests::historical_family_classification_is_total_and_canonical ... ok
test agent_identity::identity::tests::ownership_classification_never_parses_names ... ok
test agent_identity::relationships::tests::historical_family_names_validate_in_relationship_batches ... ok
test agent_identity::relationships::tests::complete_mapping_rewrites_all_run_id_fields_in_input_order ... ok
test agent_identity::relationships::tests::graph_projection_rejects_current_owner_localization_collisions ... ok
test agent_group_archive::tests::whitespace_group_name_normalizes_to_none ... ok
test agent_identity::relationships::tests::rejects_bad_container_members_and_names ... ok
test agent_identity::identity::tests::owner_aware_globalization_rejects_foreign_roots ... ok
test agent_identity::relationships::tests::rejects_duplicate_runs_names_and_containers ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_clan_declaration_and_join ... ok
test agent_identity::relationships::tests::graph_projection_localizes_global_name_relationship_targets ... ok
test agent_identity::relationships::tests::serde_contract_rejects_machine_local_and_unknown_state ... ok
test agent_identity::identity::tests::unsafe_names_and_empty_remainders_fail ... ok
test agent_identity::relationships::tests::valid_mixed_batch_returns_canonical_summary ... ok
test agent_identity::relationships::tests::mapping_must_be_complete_unique_and_exact ... ok
test agent_identity::relationships::tests::required_optional_and_cross_owner_targets_are_enforced ... ok
test agent_launch::admission::tests::external_wait_facts_gate_admission ... ok
test agent_identity::relationships::tests::rejects_self_duplicate_and_cyclic_edges ... ok
test agent_launch::admission::tests::reconcile_keeps_latest_phase_and_identity ... ok
test agent_launch::admission::tests::skipped_predecessor_is_terminal_and_does_not_retarget ... ok
test agent_launch::admission::tests::next_actions_reserve_then_wait_then_dispatch_agent ... ok
test agent_launch::condition::tests::argv_is_not_interpolated ... ok
test agent_launch::admission::tests::proc_payload_fingerprint_uses_code_digest ... ok
test agent_launch::admission::tests::summary_counts_partial_success_without_collapsing_errors ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_family_and_direct_tribe ... ok
test agent_identity::relationships::tests::graph_projection_localizes_full_owner_matrix ... ok
test agent_launch::condition::tests::classify_exit_classes ... ok
test agent_launch::proc_runtime::tests::duration_parser_matches_sase_grammar ... ok
test agent_launch::proc_runtime::tests::phases_and_origin_are_stable ... ok
test agent_launch::proc_runtime::tests::ordinary_cwd_requires_an_existing_directory ... ok
test agent_launch::proc_runtime::tests::prepare_bash_script_uses_argv_without_interpolation ... ok
test agent_launch::proc_runtime::tests::prepare_proc_script_preserves_an_inherited_user_bin_directory ... ok
test agent_launch::proc_runtime::tests::prepare_python_script_uses_sase_interpreter ... ok
test agent_launch::condition::tests::missing_interpreter_and_digest_mismatch_are_errors ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_identity_with_queue_directive ... ok
test agent_launch::admission::tests::condition_units_check_after_waits_and_fail_interrupted_checks ... ok
test agent_launch::admission::tests::dispatching_without_identity_fails_instead_of_redoing_spawn ... ok
test agent_launch::proc_runtime::tests::relative_cwd_rejects_parent_escape ... ok
test agent_launch::condition::tests::secret_inputs_are_stripped_and_workspace_is_not_shared ... ok
test agent_launch::proc_runtime::tests::workspace_false_without_cwd_is_rejected ... ok
test agent_launch::tests::agent_unit_legacy_json_defaults_to_plain_identity ... ok
test agent_launch::tests::agent_unit_identity_forms_round_trip_json ... ok
test agent_launch::condition::tests::cancel_path_settles_as_condition_error ... ok
test agent_launch::tests::claim_workspace_rejects_duplicate_nonzero_but_allows_zero ... ok
test agent_launch::tests::allocate_and_claim_picks_first_available_workspace ... ok
test agent_launch::admission::tests::dispatch_fingerprint_is_stable_for_same_payload ... ok
test agent_launch::proc_runtime::tests::relative_cwd_stays_inside_the_lease ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_never_copies_forbidden_identity_from_the_base ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_preserves_inherited_path_and_prefixes_interpreter_once ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_does_not_duplicate_an_already_prefixed_interpreter_dir ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_falls_back_to_default_path_without_a_base ... ok
test agent_launch::proc_runtime::tests::shell_names_reject_family_qualification ... ok
test agent_launch::proc_runtime::tests::symlink_cwd_cannot_escape_the_lease ... ok
test agent_launch::proc_runtime::tests::workspace_true_without_project_is_rejected ... ok
test agent_launch::tests::fanout_plan_round_trips_slots ... ok
test agent_group_archive::tests::recent_groups_are_capped_and_list_newest_first ... ok
test agent_group_archive::tests::save_and_list_pages_saved_groups_newest_first ... ok
test agent_launch::tests::occupancy_proceeds_when_no_occupant_record ... ok
test agent_launch::tests::launch_request_round_trips_json_shape ... ok
test agent_launch::tests::occupancy_proceeds_when_occupant_is_caller ... ok
test agent_launch::tests::occupancy_proceeds_when_occupant_pid_is_dead ... ok
test agent_launch::tests::occupancy_refuses_and_flags_disagreement_when_running_field_missing ... ok
test agent_launch::tests::occupancy_refuses_and_flags_disagreement_when_running_pid_differs ... ok
test agent_launch::tests::occupancy_refuses_when_occupant_is_live_other_pid ... ok
test agent_launch::tests::occupancy_refuses_when_running_field_disagrees_with_dead_occupant ... ok
test agent_launch::tests::parse_directive_args_text_block_corpus_matches_python ... ok
test agent_launch::tests::prepared_wire_preserves_null_claim_request ... ok
test agent_launch::tests::render_alternative_prompt_empty_branch_does_not_invent_space ... ok
test agent_launch::tests::prepare_agent_launch_deferred_and_home_claim_shapes ... ok
test agent_launch::tests::prepare_agent_launch_writes_prompt_and_shapes_process_data ... ok
test agent_launch::tests::timestamp_batch_rejects_invalid_format ... ok
test agent_launch::tests::timestamp_batch_allocates_unique_visible_timestamps ... ok
test agent_launch::tests::transfer_numbered_workspace_matches_pid_when_claim_name_changes ... ok
test agent_launch::tests::timestamp_batch_starts_after_previous_allocation ... ok
test agent_launch::tests::transfer_placeholder_workspace_still_matches_claim_name ... ok
test agent_launch::tests::transfer_workspace_claim_matches_pid_and_preserves_claim_name ... ok
test agent_launch::tests::transfer_workspace_claim_preserves_unknown_suffix_fields ... ok
test agent_launch::tests::transfer_workspace_claim_updates_claim_name ... ok
test agent_launch::tests::fanout_planner_time_waits_defer_workspace ... ok
test agent_launch::tests::fanout_planner_deprecated_time_directive_is_not_special ... ok
test agent_identity::relationships::tests::rejects_schema_unsafe_oversized_and_owner_mismatch ... ok
test agent_launch::tests::fanout_planner_does_not_support_removed_name_spellings ... ok
test agent_launch::tests::fanout_planner_extracts_repeat_slots ... ok
test agent_launch::tests::fanout_planner_t_xprompt_defer_workspace ... ok
test agent_launch::tests::typed_launch_clan_summary_keeps_unbalanced_inner_closer ... ok
test agent_launch::tests::typed_launch_composes_disjoint_queue_and_fanout ... ok
test agent_launch::tests::typed_launch_plan_preserves_clan_declaration_and_join ... ok
test agent_launch::tests::typed_launch_plan_builds_mixed_proc_agent_wait_graph ... ok
test agent_launch::tests::typed_launch_plan_rejects_wait_cycles ... ok
test agent_launch::tests::typed_launch_plan_resolves_forward_proc_wait ... ok
test agent_launch::tests::workspace_claims_keep_suffix_corrupt_rows_occupied ... ok
test agent_launch::tests::workspace_claims_parse_valid_rows_and_ignore_malformed ... ok
test agent_name_template::tests::compares_by_auto_sequence_order ... ok
test agent_name_template::tests::derives_namespace_template_shapes ... ok
test agent_launch::tests::fanout_planner_unclosed_brace_reports_missing_close ... ok
test agent_name_template::tests::generates_shortlex_tokens ... ok
test agent_launch::tests::fanout_planner_empty_branch_removes_space_before_punctuation ... ok
test agent_launch::tests::fanout_planner_rejects_repeated_models_with_brace_alternatives ... ok
test agent_launch::tests::fanout_planner_preserves_named_alt_ids_and_values_only ... ok
test agent_launch::tests::fanout_planner_brace_single_branch_has_implicit_empty_variant ... ok
test agent_launch::tests::fanout_planner_empty_branch_removes_leading_space ... ok
test agent_launch::tests::fanout_planner_rejects_same_value_repeated_model_directives ... ok
test agent_launch::tests::fanout_planner_empty_branch_removes_trailing_space ... ok
test agent_launch::tests::fanout_planner_correlated_group_mixes_named_and_unnamed_ids ... ok
test agent_launch::tests::fanout_planner_correlates_transitive_alt_keys ... ok
test agent_launch::tests::fanout_planner_correlates_shared_named_alt_keys ... ok
test agent_launch::tests::fanout_planner_allocates_unnamed_alt_ids_after_named_ids ... ok
test agent_launch::tests::fanout_planner_preserves_repeat_bead_association ... ok
test agent_launch::tests::fanout_planner_brace_named_text_blocks ... ok
test agent_launch::tests::fanout_planner_single_shared_key_collapses_to_one_slot ... ok
test agent_launch::tests::fanout_planner_brace_nested_pipes_do_not_split ... ok
test agent_launch::tests::fanout_planner_cartesian_products_independent_correlated_groups ... ok
test agent_launch::tests::fanout_planner_model_value_fanout_after_directive_colon ... ok
test agent_launch::tests::fanout_planner_composes_cartesian_alt_ids ... ok
test agent_launch::tests::fanout_planner_single_top_level_model_is_single_launch ... ok
test agent_launch::tests::fanout_planner_model_alt_ids_preserve_named_model_branches ... ok
test agent_launch::tests::fanout_planner_empty_branch_collapses_multiple_spaces ... ok
test agent_name_template::tests::matches_template_tokens ... ok
test agent_launch::tests::fanout_planner_brace_named_and_numeric_branch_ids ... ok
test agent_launch::tests::fanout_planner_brace_composes_cartesian_with_paren_alt ... ok
test agent_launch::tests::fanout_planner_ignores_alternative_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout_planner_empty_branch_collapses_between_words ... ok
test agent_launch::tests::fanout_planner_strips_branch_effort_for_slot_naming ... ok
test agent_launch::tests::fanout_planner_ignores_wait_forms_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout_planner_brace_branch_text_keeps_commas ... ok
test agent_launch::tests::typed_launch_plan_rejects_agent_directives_on_proc ... ok
test agent_launch::tests::fanout_planner_brace_model_branches_report_model_slots ... ok
test agent_launch::tests::fanout_planner_brace_value_fanout_after_directive_colon ... ok
test agent_launch::tests::fanout_planner_splits_model_branches_and_alternatives ... ok
test agent_launch::tests::fanout_planner_rejects_repeated_top_level_models_with_alternatives ... ok
test agent_launch::tests::fanout_planner_empty_branch_preserves_newlines_and_indentation ... ok
test agent_launch::tests::fanout_planner_brace_model_branches_match_paren_parity ... ok
test agent_launch::tests::typed_launch_clan_summary_ignores_inner_text_block_marker ... ok
test agent_launch::tests::fanout_planner_splits_multi_prompt_outside_fences ... ok
test agent_launch::tests::fanout_planner_unvalued_model_markers_do_not_count_as_repeated ... ok
test agent_launch::tests::fanout_planner_empty_branch_preserves_following_directive_separator ... ok
test agent_launch::tests::fanout_planner_rejects_paren_multi_model_directive ... ok
test agent_launch::tests::fanout_planner_value_fanouts_compose_cartesian ... ok
test agent_launch::tests::fanout_planner_ignores_models_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout_planner_brace_shorthand_splits_pipe_branches ... ok
test agent_launch::tests::typed_launch_plan_captures_if_fence_without_duplicate_form_error ... ok
test agent_launch::tests::fanout_planner_preserves_repeat_and_id_inside_literal_zones ... ok
test agent_launch::tests::fanout_planner_rejects_repeated_top_level_model_directives ... ok
test agent_launch::tests::extract_first_model_value_strips_known_effort_suffix ... ok
test agent_launch::tests::typed_launch_plan_preserves_family_and_direct_tribe ... ok
test agent_launch::tests::fanout_planner_brace_value_fanout_after_effort_e_alias ... ok
test agent_launch::tests::typed_launch_plan_rejects_conflicting_identity_forms ... ok
test agent_launch::tests::typed_launch_plan_validates_proc_project_policy ... ok
test agent_launch::tests::launch_inline_scanner_preserves_argument_parser_precedence ... ok
test agent_launch::tests::typed_launch_plan_keeps_fenced_proc_options ... ok
test agent_launch::tests::typed_launch_plan_rejects_bare_if_without_owned_fence ... ok
test agent_launch::tests::typed_launch_rejects_wait_queue_keywords_and_proc_queue ... ok
test agent_name_template::tests::rejects_invalid_or_multiple_markers ... ok
test agent_name_template::tests::parses_exactly_one_marker ... ok
test agent_name_template::tests::parses_keyed_markers ... ok
test agent_name_template::tests::renders_template_shapes ... ok
test agent_name_template::tests::scans_markers_with_round_trip_byte_spans ... ok
test agent_name_template::tests::scanner_ignores_invalid_braced_and_jinja_forms ... ok
test agent_name_template::tests::render_and_match_are_exact_inverses ... ok
test agent_launch::tests::typed_launch_parses_queue_spellings_and_round_trips ... ok
test agent_ownership::planner::tests::clan_generation_mismatch_blocks_claim_overwrite ... ok
test agent_ownership::planner::tests::live_and_container_owners_are_not_selected_without_authorization ... ok
test agent_ownership::planner::tests::cleanup_guard_returns_internal_reservation_state ... ok
test agent_ownership::planner::tests::cleanup_does_not_select_dotted_prefix_descendants_by_name_only ... ok
test agent_ownership::planner::tests::incomplete_discovery_and_truncated_closure_block_cleanup ... ok
test agent_runtime::tests::answered_question_gap_between_segments_is_excluded ... ok
test agent_ownership::planner::tests::cleanup_closure_follows_retry_and_incoming_relationships_once ... ok
test agent_ownership::planner::tests::reservations_reuse_current_owner_aliases_and_planned_owner ... ok
test agent_ownership::planner::tests::reservations_block_batch_duplicate_aliases_and_foreign_namespace ... ok
test agent_runtime::tests::approved_plan_followup_starts_a_new_active_segment ... ok
test agent_runtime::tests::admission_predicate_excludes_serial_children_only ... ok
test agent_ownership::planner::tests::overlapping_roots_deduplicate_effects_with_attribution ... ok
test agent_runtime::tests::earliest_valid_stop_or_finish_is_shared_runtime_end ... ok
test agent_runtime::tests::clan_members_launched_independently_count_individually ... ok
test agent_runtime::tests::empty_input_has_zero_inactive_runtime ... ok
test agent_runtime::tests::family_interval_merge_unions_overlap_and_fills_monitor_gap ... ok
test agent_runtime::tests::dead_root_with_live_monitor_member_still_occupies_one_slot ... ok
test agent_runtime::tests::done_marker_and_dead_pid_members_do_not_occupy ... ok
test agent_runtime::tests::gaps_and_sequential_members_are_summed ... ok
test agent_runtime::tests::malformed_timestamps_do_not_contribute ... ok
test agent_runtime::tests::inherited_monitor_id_without_monitor_role_uses_ordinary_started_rule ... ok
test agent_runtime::tests::open_intervals_end_at_now_and_mark_runtime_active ... ok
test agent_runtime::tests::malformed_terminal_and_reversed_segments_are_rejected ... ok
test agent_runtime::tests::non_agent_workflow_step_record_does_not_occupy ... ok
test agent_runtime::tests::overlapping_members_are_measured_once ... ok
test agent_runtime::tests::plan_feedback_window_is_excised ... ok
test agent_runtime::tests::inherited_gate_id_without_gate_role_uses_ordinary_started_rule ... ok
test agent_runtime::tests::live_parallel_family_members_count_individually ... ok
test agent_runtime::tests::pending_question_on_familys_only_live_shell_frees_its_slot ... ok
test agent_runtime::tests::pending_gate_member_frees_its_runner_slot ... ok
test agent_runtime::tests::monitor_member_with_pid_but_no_run_started_at_occupies_one_slot ... ok
test agent_runtime::tests::occupancy_member_start_ignores_artifact_timestamp_even_for_monitor ... ok
test agent_runtime::tests::slot_yield_needs_a_resolved_question_answer_time ... ok
test agent_runtime::tests::synthesized_terminal_never_supplies_the_runtime_end ... ok
test agent_runtime::tests::pending_question_window_extends_to_now_and_does_not_tick ... ok
test agent_runtime::tests::records_from_two_projects_sharing_a_family_name_count_separately ... ok
test agent_runtime::tests::standalone_agent_occupies_one_slot ... ok
test agent_runtime::tests::settled_monitor_with_live_followup_still_occupies_one_slot ... ok
test agent_runtime::tests::wait_policies_distinguish_plan_review_from_slot_yields ... ok
test agent_runtime::tests::root_plus_live_serial_child_occupies_exactly_one_slot ... ok
test agent_runtime::tests::two_independent_families_occupy_two_slots ... ok
test agent_runtime::tests::settled_gate_member_uses_ordinary_started_rule ... ok
test agent_runtime::tests::unresolved_plan_caps_a_live_member_and_does_not_tick ... ok
test agent_scan::index::tests::abandoned_terminalization_prefers_stopped_at_then_directory_mtime ... ok
test agent_scan::index::tests::index_query_wire_round_trips_active_limit ... ok
test agent_scan::index::tests::prompt_snippet_truncation_stays_on_utf8_char_boundary ... ok
test agent_launch::condition::tests::bash_exit_two_is_condition_error ... ok
test agent_launch::condition::tests::bash_exit_zero_is_eligible ... ok
test agent_launch::condition::tests::bash_exit_one_is_skipped ... ok
test agent_scan::index::tests::replace_unusable_index_file_renames_sidecars ... ok
test agent_scan::index::tests::refresh_stale_rows_signature_query_does_not_select_record_json ... ok
test agent_launch::condition::tests::python_reads_condition_context_and_matches_bash_skip ... ok
test agent_launch::condition::tests::output_is_truncated_and_cwd_missing_is_error ... ok
test agent_scan::index::tests::query_keeps_corrupt_existing_index_strict ... ok
test agent_launch::condition::tests::timeout_kills_process_group ... ok
test agent_scan::index::tests::read_only_open_falls_back_when_index_missing ... ok
test agent_scan::index::tests::alias_history_rejects_empty_aliases ... ok
test agent_scan::index::tests::read_only_open_cannot_write ... ok
test agent_scan::index::tests::done_marker_without_finished_at_or_stopped_at_indexes_null ... ok
test agent_scan::index::tests::status_reports_freelist_and_file_size ... ok
test agent_scan::layout::tests::canonical_ace_run_path_is_day_sharded ... ok
test agent_scan::layout::tests::collect_prefers_sharded_duplicate_timestamp ... ok
test agent_scan::layout::tests::non_ace_run_path_stays_flat ... ok
test agent_scan::layout::tests::parse_accepts_legacy_and_sharded_paths ... ok
test agent_scan::layout::tests::parse_rejects_malformed_shard_paths ... ok
test agent_scan::layout::tests::resolve_legacy_path_to_shard_when_present ... ok
test agent_scan::scanner::tests::scanner_defaults_absent_alias_trail_and_origin ... ok
test agent_scan::scanner::tests::scanner_defaults_absent_monitor_next_model ... ok
test agent_scan::scanner::tests::scanner_round_trips_alias_trail_and_origin ... ok
test agent_scan::scanner::tests::scanner_round_trips_gate_shell_metadata ... ok
test agent_scan::scanner::tests::scanner_round_trips_monitor_next_model ... ok
test agent_scan::index::tests::explicit_done_finished_at_is_not_overridden_by_stopped_at ... ok
test agent_scan::index::tests::alias_history_falls_back_to_legacy_first_hop ... ok
test agent_scan::index::tests::cached_query_returns_rebuilt_records_without_revalidation ... ok
test agent_scan::index::tests::alias_history_status_counts_projection_rows ... ok
test agent_scan::index::tests::recent_completed_rows_remain_visible_when_not_dismissed ... ok
test agent_scan::selector::tests::parser_accepts_nested_and_escaped_paths ... ok
test agent_scan::selector::tests::parser_rejects_invalid_selectors ... ok
test agent_scan::selector::tests::parser_splits_dotted_names_from_the_right ... ok
test agent_scan::index::tests::explicit_workflow_state_hidden_is_still_filtered ... ok
test agent_scan::index::tests::terminal_workflow_state_rows_are_recent_completed_rows ... ok
test agent_scan::index::tests::cached_query_does_not_refresh_stale_marker_rows ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_alias_trail_and_origin ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_every_gate_field ... ok
test agent_scan::wire::tests::agent_meta_wire_without_gate_fields_still_parses ... ok
test agent_scan::wire::tests::agent_meta_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::done_marker_wire_round_trips_every_gate_field ... ok
test agent_scan::wire::tests::done_marker_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::done_marker_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_defaults_absent_alias_trail ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_round_trips_alias_trail_and_origin ... ok
test agent_stats::activity::tests::aggregates_logs_and_project_scoped_gate_bundles ... ok
test agent_stats::activity::tests::maps_both_response_shapes_and_pending_plan_bundles ... ok
test agent_stats::activity::tests::rejects_invalid_range_before_opening_index ... ok
test agent_stats::activity::tests::skips_malformed_bundles_and_ignores_legacy_question_store ... ok
test agent_scan::index::tests::query_self_heals_done_creation_before_completed_filter ... ok
test agent_scan::index::tests::alias_history_preserves_request_order_and_empty_groups ... ok
test agent_scan::index::tests::schema_v19_upgrade_refreshes_record_json_for_model_aliases ... ok
test agent_scan::index::tests::missing_done_finished_at_indexes_from_meta_stopped_at ... ok
test agent_scan::index::tests::only_monitors_filters_to_monitor_family_role ... ok
test agent_scan::index::tests::alias_history_filters_hidden_and_project_keys ... ok
test agent_stats::run::tests::rejects_invalid_ranges_and_bucket_explosions ... ok
test agent_scan::index::tests::anonymous_appears_as_agent_workflow_is_not_hidden ... ok
test agent_scan::index::tests::query_self_heals_running_to_done_transition ... ok
test agent_scan::index::tests::alias_history_truncates_newest_first_and_reports_counts ... ok
test agent_scan::index::tests::wait_completed_records_are_indexed_as_running ... ok
test agent_scan::index::tests::load_agent_artifact_records_returns_full_records_for_dirs_and_aliases ... ok
test agent_scan::index::tests::recent_completed_limit_does_not_bound_active_rows ... ok
test agent_scan::index::tests::rebuild_indexes_scanner_equivalent_records ... ok
test agent_scan::index::tests::query_skips_rescan_when_signatures_match ... ok
test agent_scan::index::tests::rebuild_replaces_corrupt_existing_index ... ok
test agent_scan::index::tests::query_self_heals_appended_feedback_submitted_at ... ok
test agent_scan::index::tests::tier1_active_query_is_bounded_to_newest_incomplete_rows ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_skips_workspace_claim ... ok
test agent_stats::run::tests::runtime_percentiles_interpolate_sorted_durations ... ok
test agent_scan::index::tests::query_self_heals_waiting_deletion_to_running ... ok
test agent_scan::index::tests::alias_history_revalidate_refreshes_candidate_rows ... ok
test agent_stats::runner::tests::inherited_monitor_id_does_not_fill_family_gap ... ok
test agent_stats::runner::tests::host_liveness_requires_current_matching_claim_identity ... ok
test agent_stats::runner::tests::monitor_handoff_gap_does_not_reopen_family_interval ... ok
test agent_stats::runner::tests::open_intervals_require_liveness_and_missing_starts_are_not_invalid ... ok
test agent_stats::runner::tests::overlapping_serial_family_shells_count_as_one_slot ... ok
test agent_stats::runner::tests::simultaneous_boundaries_do_not_create_phantom_occupancy ... ok
test agent_stats::runner::tests::trend_is_strictly_bounded_and_keeps_partial_final_slice ... ok
test agent_stats::wire::tests::older_commit_stats_without_committing_runs_default ... ok
test agent_stats::wire::tests::older_run_stats_payload_without_runners_deserializes ... ok
test agent_stats::wire::tests::older_run_stats_payload_without_xprompts_deserializes ... ok
test agent_stats::wire::tests::older_xprompt_row_without_truncation_counts_defaults ... ok
test artifact_consumption::tests::reader_is_tolerant_of_bad_rows_and_an_absent_file ... ok
test artifact_consumption::tests::restricted_summary_omits_unselected_and_never_consumed_refs ... ok
test agent_stats::wire::tests::older_run_stats_request_uses_xprompt_defaults ... ok
test artifact_consumption::tests::summary_distinguishes_events_from_distinct_agents ... ok
test artifact_file::context::tests::deduplicates_by_id_retaining_first_requested_dependency ... ok
test artifact_file::context::tests::different_projects_and_generations_are_independent_producers ... ok
test artifact_file::context::tests::empty_batch_never_opens_the_index ... ok
test artifact_file::context::tests::excludes_chat_rows_even_when_explicitly_indexed ... ok
test artifact_file::context::tests::handles_multiple_producers_within_one_dependency_in_given_order ... ok
test agent_scan::index::tests::settled_monitor_without_finished_at_stays_in_recent_completed_window ... ok
test artifact_file::context::tests::matches_exact_producer_directory_despite_reused_agent_names ... ok
test artifact_file::context::tests::missing_index_tolerates_nonempty_batch_as_empty_result ... ok
test artifact_file::context::tests::nonempty_batch_against_unreadable_index_is_an_error ... ok
test artifact_file::context::tests::preserves_explicit_flag ... ok
test artifact_file::context::tests::orders_by_dependency_then_producer_then_creation_time_and_id ... ok
test artifact_file::context::tests::tolerates_malformed_index_lines ... ok
test artifact_file::economics::tests::single_day_window_has_finite_rates_and_schema_is_checked ... ok
test artifact_file::context::tests::vcs_backed_rows_have_no_stored_path ... ok
test artifact_file::economics::tests::aggregates_mixed_rows_truncation_redundancy_and_projections ... ok
test artifact_file::retention::tests::invalid_now_and_schema_are_rejected ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_revalidates_new_running_marker ... ok
test artifact_file::retention::tests::retention_now_uses_its_embedded_offset_calendar_date ... ok
test artifact_file::retention::tests::predicates_compose_clamp_generation_floor_and_limit_deterministically ... ok
test artifact_file::retention::tests::each_additional_predicate_filters_generation_candidates ... ok
test artifact_file::retention::tests::protects_explicit_and_referenced_and_separates_byte_free_rows ... ok
test artifact_file::tests::absent_index_is_empty_and_invalid_since_is_an_error ... ok
test artifact_file::retention::tests::zero_keep_without_other_predicates_disables_selection ... ok
test artifact_file::tests::embedded_offset_controls_calendar_date_but_sorting_uses_instant ... ok
test artifact_file::tests::parser_accepts_supported_range_and_skips_bad_rows ... ok
test artifact_file::tests::query_sorts_newest_first_missing_last_and_applies_limit ... ok
test artifact_file::tests::query_applies_every_filter_individually_and_combined ... ok
test artifact_file::tests::unused_filter_runs_before_limit_and_tolerates_missing_ledgers ... ok
test artifact_file::tests::since_uses_plan_search_forms_and_excludes_missing_dates ... ok
test artifact_file::trash::tests::refuses_symlink_escape_and_unsafe_entry_id ... ok
test artifact_file::trash::tests::byte_backed_store_list_restore_and_purge_round_trip ... ok
test artifact_file::trash::tests::byte_free_collision_and_unreadable_listing_are_deterministic ... ok
test agent_scan::index::tests::active_query_excludes_dismissed_identity_after_rebuild ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_skips_fresh_missing_marker_race ... ok
test agent_scan::index::tests::alias_history_prompt_snippets_strip_collapse_and_truncate ... ok
test agent_scan::index::tests::output_variable_history_filters_groups_and_truncates ... ok
test artifact_link::events::tests::alias_chains_resolve_edges_and_cycles_or_conflicts_fail ... ok
test agent_scan::index::tests::bounded_artifact_index_delete_skips_locked_database ... ok
test artifact_link::events::tests::baseline_imports_preserve_counts_and_are_one_shot_by_import_id ... ok
test artifact_link::events::tests::bytes_validation_rejects_floats_and_path_mismatches ... ok
test artifact_link::events::tests::canonical_json_digest_and_path_are_byte_stable ... ok
test artifact_link::events::tests::event_edge_identity_normalizes_directed_and_undirected_relations ... ok
test artifact_link::events::tests::edge_put_supersedes_named_versions_and_uses_lexical_tie_break ... ok
test artifact_link::events::tests::predecessor_ids_known_on_other_edges_are_rejected ... ok
test artifact_link::events::tests::reduction_deduplicates_exact_retries_but_counts_distinct_observations ... ok
test artifact_file::vcs::tests::rejects_cache_path_escape_inputs ... ok
test artifact_link::events::tests::reduction_rejects_operation_id_collisions ... ok
test artifact_link::events::tests::validation_rejects_bad_identifiers_payloads_and_edges ... ok
test artifact_link::events::tests::remove_before_add_removes_only_observed_versions ... ok
test artifact_link::inlet::tests::empty_list_is_entries ... ok
test artifact_link::inlet::tests::mapping_links_value_is_unrecognized ... ok
test artifact_link::inlet::tests::matching_shape_is_entries ... ok
test artifact_link::inlet::tests::missing_key_is_absent ... ok
test artifact_link::events::tests::reduction_is_stable_for_reordered_and_duplicated_deliveries ... ok
test artifact_link::inlet::tests::mkdocs_label_path_is_unrecognized ... ok
test artifact_link::inlet::tests::no_frontmatter_is_absent ... ok
test artifact_link::managed_table::tests::empty_links_table_removes_the_block ... ok
test artifact_link::managed_table::tests::links_render_sorts_and_emits_pointer ... ok
test artifact_link::managed_table::tests::links_skip_host_document_reference_labels ... ok
test artifact_link::managed_table::tests::links_after_plan_header_does_not_trip_header_invalid ... ok
test artifact_link::merge::tests::accepts_one_sided_and_identical_deletes ... ok
test artifact_link::managed_table::tests::links_upsert_is_top_anchored_and_idempotent ... ok
test artifact_link::merge::tests::accepts_one_sided_and_identical_edits ... ok
test artifact_link::merge::tests::rejects_competing_same_key_edits_and_modify_delete ... ok
test artifact_link::merge::tests::merge_is_idempotent ... ok
test artifact_link::merge::tests::unions_distinct_additions_in_deterministic_order_after_base_rows ... ok
test artifact_link::merge::tests::validates_schema_artifact_ref_and_duplicates ... ok
test artifact_link::path::tests::companion_uses_stem_and_disambiguates_on_collision ... ok
test artifact_link::path::tests::bead_page_uses_readme_for_lineage_root ... ok
test agent_scan::index::tests::query_self_heals_hidden_to_visible_before_visible_filter ... ok
test artifact_link::path::tests::document_kind_is_itself ... ok
test artifact_link::path::tests::published_markdown_file_is_itself ... ok
test artifact_link::path::tests::stitch_has_no_markdown_file ... ok
test artifact_link::path::tests::unpublished_file_uses_local_pages_dir ... ok
test artifact_link::publication_retry::tests::deferred_attempt_does_not_consume_failure_backoff ... ok
test artifact_link::publication_retry::tests::due_policy_reports_retry_after_and_aging_warning ... ok
test artifact_link::publication_retry::tests::failed_attempts_exponentially_back_off_at_six_hours ... ok
test artifact_link::publication_retry::tests::pending_registration_preserves_age_across_head_changes ... ok
test artifact_link::relation::tests::builtins_cover_v1_table ... ok
test artifact_link::relation::tests::every_builtin_documents_direction_and_examples ... ok
test artifact_link::relation::tests::implements_settles_the_plan_bead_direction ... ok
test artifact_link::relation::tests::inverse_label_is_from_this_document ... ok
test artifact_link::relation::tests::reserved_slugs_point_at_bead_dep ... ok
test artifact_link::relation::tests::produced_by_and_launched_round_trip ... ok
test artifact_link::row_resolution::tests::parse_link_ref_parts_strips_aliases_sigil_and_fragment ... ok
test artifact_link::relation::tests::unknown_slug_lists_builtins ... ok
test artifact_link::row_resolution::tests::guards_do_not_resolve_virtual_or_malformed_refs ... ok
test artifact_link::row_resolution::tests::resolver_matches_key_probe_equivalence ... ok
test artifact_link::row_resolution::tests::project_hint_precedes_deterministic_fallback ... ok
test artifact_link::wire::tests::canonicalize_strips_sigil_and_rewrites_kind_aliases ... ok
test artifact_link::wire::tests::directed_same_pair_may_carry_several_relations ... ok
test artifact_link::wire::tests::prompt_ref_rewrite_increments_uses_and_keeps_created_at ... ok
test artifact_link::wire::tests::reserved_slugs_are_not_stored ... ok
test artifact_link::wire::tests::validate_rejects_self_links_and_blank_descriptions ... ok
test artifact_link::wire::tests::undirected_related_dedups_either_direction ... ok
test artifact_link::wire::tests::validate_rejects_multiline_and_overlong_descriptions ... ok
test artifact_link_eligibility::policy::tests::a_real_change_makes_its_repo_qualify ... ok
test artifact_link_eligibility::policy::tests::bookkeeping_only_repos_are_ineligible ... ok
test artifact_link_eligibility::policy::tests::empty_repos_are_ineligible ... ok
test artifact_link_eligibility::policy::tests::rejects_blank_run_id ... ok
test artifact_link_eligibility::policy::tests::rejects_unsupported_schema_version ... ok
test artifact_link_eligibility::policy::tests::release_evidence_rejects_a_different_agent_in_the_same_family ... ok
test artifact_link_eligibility::policy::tests::release_evidence_rejects_a_different_run_id ... ok
test artifact_link_eligibility::policy::tests::release_evidence_requires_eligible_decision ... ok
test artifact_link_eligibility::policy::tests::release_evidence_round_trips_and_validates_against_the_same_run ... ok
test artifact_link_eligibility::policy::tests::serde_rejects_unknown_change_role ... ok
test artifact_link_eligibility::policy::tests::serde_rejects_unknown_fields ... ok
test artifact_link_eligibility::policy::tests::serde_round_trips_the_decision_wire ... ok
test artifact_object_store::tests::object_paths_reject_non_full_lowercase_sha256 ... ok
test artifact_object_store::tests::object_relpath_uses_digest_shard ... ok
test artifact_link::row_resolution::tests::resolves_class_a_row_identity_shapes ... ok
test artifact_ref::entry::tests::rejects_empty_stable_id_and_bad_kind ... ok
test artifact_ref::entry::tests::rejects_malformed_revision_digest_and_property_keys ... ok
test artifact_ref::entry::tests::valid_entry_passes ... ok
test artifact_file::vcs::tests::materializes_direct_blob_then_uses_verified_cache ... ok
test artifact_ref::expansion::tests::double_braces_escape_to_literal_braces ... ok
test artifact_ref::expansion::tests::missing_value_is_a_render_error ... ok
test artifact_ref::expansion::tests::unknown_placeholder_and_unbalanced_braces_are_rejected ... ok
test artifact_ref::expansion::tests::substituted_values_are_never_rescanned ... ok
test artifact_ref::expansion::tests::validate_returns_placeholders_in_first_seen_order_without_duplicates ... ok
test artifact_ref::file_roots::tests::file_path_payload_still_round_trips_as_a_file_path_payload ... ok
test artifact_ref::file_roots::tests::absolute_and_home_paths_resolve_to_one_logical_path ... ok
test artifact_ref::file_roots::tests::directories_and_size_overages_are_denied ... ok
test artifact_ref::file_roots::tests::missing_inside_root_is_missing_and_traversal_escape_is_filtered ... ok
test artifact_file::vcs::tests::replaces_wrong_cache_content_after_verifying_git_blob ... ok
test artifact_ref::file_roots::tests::relative_paths_and_zero_roots_are_rejected_without_guessing ... ok
test artifact_ref::file_roots::tests::overlapping_roots_are_ambiguous_and_glob_miss_is_filtered ... ok
test artifact_ref::filter::tests::batch_filter_reports_allowed_and_filtered_in_input_order ... ok
test artifact_ref::filter::tests::explicit_empty_filter_allows_nothing ... ok
test artifact_ref::file_roots::tests::symlink_escape_fifo_and_unreadable_files_are_denied ... ok
test artifact_ref::filter::tests::globstar_matches_root_and_nested_paths_case_sensitively ... ok
test artifact_ref::filter::tests::malformed_patterns_and_unsafe_payloads_error ... ok
test artifact_ref::filter::tests::negative_only_allows_everything_except_vetoes ... ok
test artifact_ref::filter::tests::positives_or_together_and_negations_veto ... ok
test artifact_ref::kinds::tests::catalog_lists_reserved_kinds_offered_in_completion ... ok
test artifact_ref::kinds::tests::catalog_marks_aliases_and_historical_kinds_absent_from_completion ... ok
test artifact_ref::kinds::tests::commit_canonicalizes_to_stitch_without_a_diagnostic ... ok
test artifact_ref::kinds::tests::plans_canonicalizes_to_plan_with_a_diagnostic ... ok
test artifact_ref::kinds::tests::canonical_parse_rewrites_commit_and_plans_but_nothing_else ... ok
test artifact_ref::kinds::tests::unregistered_labels_canonicalize_to_themselves ... ok
test artifact_ref::list::tests::batch_resolve_loads_the_artifact_index_once ... ok
test artifact_ref::list::tests::normalize_deduplicates_in_first_occurrence_order ... ok
test artifact_ref::list::tests::malformed_entry_does_not_abort_valid_neighbors ... ok
test artifact_ref::list::tests::parse_rejects_malformed_sigiled_and_empty_entries_with_position ... ok
test artifact_ref::provider_spec::tests::accepts_two_cell_emoji_icon ... ok
test artifact_ref::kinds::tests::default_parse_is_byte_identical_for_every_historical_kind ... ok
test artifact_ref::list::tests::parse_and_normalize_every_kind_and_fragment ... ok
test artifact_ref::provider_spec::tests::digest_changes_when_icon_changes ... ok
test artifact_ref::provider_spec::tests::rejects_bad_expansion_format ... ok
test artifact_ref::provider_spec::tests::rejects_bad_inventory_globs_and_publication_values ... ok
test artifact_ref::provider_spec::tests::rejects_missing_or_malformed_icon ... ok
test artifact_ref::provider_spec::tests::rejects_reserved_kind_and_bad_identifiers ... ok
test artifact_ref::provider_spec::tests::rejects_undeclared_detail_and_identity_properties ... ok
test artifact_ref::provider_spec::tests::rejects_property_type_enum_and_source_issues ... ok
test artifact_ref::provider_spec::tests::rejects_unsupported_schema_version ... ok
test artifact_ref::ref_files::tests::validation_rejects_bad_identity_fields ... ok
test artifact_ref::ref_files::tests::row_round_trips_and_parse_skips_bad_and_future_lines ... ok
test artifact_ref::ref_files::tests::fold_deduplicates_versions_and_unions_provenance ... ok
test artifact_ref::provider_spec::tests::valid_spec_passes_and_digest_is_stable ... ok
test artifact_ref::repository_resolution::tests::absent_checkout_is_a_retryable_missing_checkout ... ok
test artifact_ref::repository_resolution::tests::caller_attached_checkout_candidate_wins_without_repository_inventory ... ok
test artifact_ref::repository_resolution::tests::correlated_producer_workspace_resolves_without_inventory ... ok
test artifact_ref::repository_resolution::tests::directory_targets_use_the_same_decision_path ... ok
test artifact_ref::repository_resolution::tests::distinct_attached_repositories_are_ambiguous_not_first_hit ... ok
test artifact_ref::repository_resolution::tests::deleted_producer_workspace_falls_back_to_a_live_alternate_checkout ... ok
test artifact_ref::repository_resolution::tests::drifted_path_resolves_through_bounded_suffix_search ... ok
test artifact_ref::repository_resolution::tests::explicit_owner_repository_scopes_the_search_and_skips_others ... ok
test artifact_ref::repository_resolution::tests::no_repositories_configured_is_missing_checkout_not_a_guess ... ok
test agent_scan::index::tests::related_artifact_dirs_follow_retry_and_parent_lineage ... ok
test artifact_ref::repository_resolution::tests::out_of_inventory_source_directory_is_not_relabeled_as_owner_repo ... ok
test artifact_ref::repository_resolution::tests::owner_project_mismatch_does_not_use_viewer_inventory ... ok
test artifact_ref::repository_resolution::tests::owner_repository_mismatch_does_not_use_foreign_source_directory ... ok
test agent_scan::index::tests::hidden_inclusive_full_history_can_inspect_dismissed_rows ... ok
test artifact_ref::repository_resolution::tests::proven_missing_when_every_known_checkout_was_searched ... ok
test agent_scan::index::tests::migration_recomputes_hidden_for_v1_indexes ... ok
test artifact_ref::repository_resolution::tests::source_directory_nested_inside_valid_checkout_with_project_agreement ... ok
test artifact_ref::repository_resolution::tests::resolves_a_source_path_in_its_owning_linked_repository ... ok
test artifact_ref::repository_resolution::tests::owner_path_globs_deny_before_any_checkout_probe ... ok
test artifact_ref::repository_resolution::tests::same_named_directories_in_distinct_repos_are_ambiguous ... ok
test artifact_ref::repository_resolution::tests::stale_attached_checkout_falls_through_to_live_same_repo_inventory ... ok
test artifact_ref::repository_resolution::tests::stale_source_directory_falls_through_to_live_same_repo_inventory ... ok
test artifact_ref::repository_resolution::tests::traversal_payload_is_rejected_before_any_search ... ok
test artifact_ref::repository_resolution::tests::source_directory_resolves_a_one_component_path_beside_the_document ... ok
test artifact_ref::repository_resolution::tests::unavailable_project_context_does_not_use_inventory ... ok
test artifact_ref::repository_resolution::tests::two_ambiguous_linked_repos_report_both_candidates ... ok
test artifact_ref::repository_resolution::tests::suffix_budget_exhaustion_is_a_temporary_error ... ok
test artifact_ref::scanner::tests::fragment_splits_after_the_closing_quote ... ok
test artifact_ref::scanner::tests::quote_artifact_ref_argument_round_trips_through_the_scanner ... ok
test artifact_ref::scanner::tests::quoted_argument_supports_escaped_quote_and_backslash ... ok
test artifact_ref::scanner::tests::quoted_argument_with_spaces_parses_and_round_trips ... ok
test artifact_ref::scanner::tests::quoted_trailing_punctuation_is_not_trimmed ... ok
test artifact_ref::scanner::tests::unterminated_quote_at_true_eof_ends_at_end_of_text ... ok
test artifact_ref::scanner::tests::unterminated_quote_ends_at_the_current_line_never_at_eof ... ok
test artifact_ref::scanner::tests::xprompt_argument_delimiters_are_allowed_left_context ... ok
test artifact_file::vcs::tests::searches_bounded_remote_history_when_recorded_sha_is_gone ... ok
test agent_scan::index::tests::active_limit_prioritizes_waiting_rows_over_newer_stale_rows ... ok
test artifact_ref::tests::agent_resolution_globalizes_and_preserves_historical_names ... ok
test artifact_ref::tests::canonicalization_recognizes_only_canonical_entity_pages ... ok
test artifact_file::vcs::tests::tries_later_checkouts_when_the_first_lacks_the_object ... ok
test artifact_ref::tests::bead_resolution_covers_pages_projects_and_ambiguity ... ok
test artifact_ref::tests::canonicalization_uses_order_and_artifact_index ... ok
test artifact_ref::tests::commit_resolution_still_considers_sidecar_repositories ... ok
test artifact_ref::tests::context_schema_version_is_required_for_context_operations ... ok
test artifact_ref::tests::file_path_payloads_accept_fragments_and_stitch_shorthand_bounds ... ok
test artifact_ref::tests::document_path_globs_filter_resolution_and_canonicalization ... ok
test artifact_ref::tests::filtered_root_cannot_be_bypassed_by_later_duplicate_roots ... ok
test agent_scan::index::tests::list_record_shape_projects_only_heavy_leaves ... ok
test artifact_ref::tests::indexed_file_resolution_accepts_supported_envelope_range ... ok
test artifact_ref::tests::filtered_drift_candidates_are_not_reported ... ok
test artifact_ref::tests::every_kind_and_fragment_round_trips ... ok
test artifact_ref::tests::indexed_vcs_backed_file_resolution_is_pure_and_reports_provenance ... ok
test artifact_ref::tests::namespace_resolution_is_canonical_and_local ... ok
test artifact_ref::tests::parsed_references_carry_the_current_wire_schema ... ok
test artifact_ref::tests::parse_rejects_invalid_shapes_and_illegal_fragments ... ok
test artifact_ref::tests::scanner_enforces_left_context_but_scans_fences ... ok
test artifact_ref::tests::validate_artifact_ref_context_accepts_the_supported_range ... ok
test artifact_ref::tests::scanner_reports_utf8_byte_spans_and_malformed_candidates ... ok
test artifact_ref::uses::tests::rejects_empty_required_fields_and_bad_kind ... ok
test artifact_ref::uses::tests::manifest_parse_tolerates_unknown_fields ... ok
test artifact_ref::uses::tests::manifest_round_trip_skips_bad_and_future_lines ... ok
test artifact_ref::uses::tests::valid_record_passes ... ok
test artifact_ref::tests::path_resolution_covers_order_drift_ambiguity_and_missing ... ok
test axe_chop::diagnostics::tests::reports_absent_and_unavailable_output ... ok
test axe_chop::tests::agent_clan_guard_matches_only_explicit_active_case_sensitive_clans ... ok
test axe_chop::tests::agent_clan_guard_short_circuits_trigger_errors ... ok
test axe_chop::tests::axe_descriptions_split_into_normalized_summary_and_body ... ok
test axe_chop::tests::checkpoint_success_policy_commits_only_after_success ... ok
test axe_chop::tests::agent_runners_guard_counts_only_active_runner_slot_holders ... ok
test axe_chop::tests::chop_report_rejects_control_characters_and_overlong_text ... ok
test axe_chop::tests::chop_report_rejects_unknown_block_kinds_and_tones ... ok
test axe_chop::tests::chop_report_rejects_ragged_rows_disallowed_glyphs_and_invalid_gauges ... ok
test agent_scan::index::tests::query_self_heals_newly_added_run_started_at ... ok
test axe_chop::tests::chop_result_without_report_remains_valid_and_serializes_null ... ok
test artifact_file::vcs::tests::reports_missing_for_unknown_content_or_a_zero_history_bound ... ok
test axe_chop::tests::chop_report_round_trips_every_block_kind ... ok
test artifact_file::vcs::tests::checkout_head_and_historical_path_use_bounded_git ... ok
test axe_chop::tests::compound_durations_are_strict_and_positive ... ok
test axe_chop::tests::chop_report_rejects_excess_blocks_and_rows ... ok
test axe_chop::tests::derived_agent_names_include_sanitized_bounded_run_token ... ok
test axe_chop::tests::derived_agent_names_include_target_and_order ... ok
test axe_chop::tests::derived_agent_names_keep_length_and_trailing_separator_guards ... ok
test axe_chop::tests::derived_agent_names_reject_empty_sanitized_run_token ... ok
test axe_chop::tests::earlier_guard_wins_over_agent_runners ... ok
test agent_scan::index::tests::query_self_heals_pending_question_creation_and_deletion ... ok
test axe_chop::tests::fs_trigger_fails_open_on_token_computation_error_without_persisting ... ok
test axe_chop::tests::fs_trigger_fails_open_when_no_observation_is_provided ... ok
test axe_chop::tests::fs_trigger_fires_on_missing_checkpoint_and_persists_baseline_token ... ok
test axe_chop::tests::fs_trigger_fires_after_max_quiet_elapses_with_unchanged_token ... ok
test axe_chop::tests::fs_trigger_fires_when_token_changes ... ok
test axe_chop::tests::fs_trigger_rejects_empty_paths ... ok
test axe_chop::tests::fs_trigger_skips_when_token_unchanged_and_within_max_quiet ... ok
test axe_chop::tests::guards_short_circuit_triggers ... ok
test axe_chop::tests::git_trigger_returns_checkpoint_observation ... ok
test axe_chop::tests::legacy_changespec_guard_provider_deserializes_as_patch ... ok
test axe_chop::tests::once_per_release_validates_engine_and_document_schemas ... ok
test axe_chop::tests::once_per_release_removes_exact_keys_and_is_idempotent ... ok
test axe_chop::tests::once_per_store_rejects_duplicates_and_evicts_oldest ... ok
test axe_chop::tests::chop_report_rejects_oversize_documents ... ok
test axe_chop::tests::strict_axe_validation_accepts_keyed_and_tagged_agent_clan_guards ... ok
test axe_chop::tests::strict_axe_validation_accepts_fs_trigger_with_bare_and_glob_paths ... ok
test axe_chop::tests::strict_axe_validation_accepts_missing_descriptions_by_default ... ok
test axe_chop::tests::strict_axe_validation_accepts_keyed_and_tagged_agent_runners_guards ... ok
test axe_chop::tests::strict_axe_validation_accepts_nonnegative_or_missing_wait_runners ... ok
test axe_chop::tests::strict_axe_validation_accepts_new_shape ... ok
test agent_scan::index::tests::indexed_clan_context_honors_latest_declarations_and_generations ... ok
test agent_scan::index::tests::query_self_heals_appended_plan_submitted_at ... ok
test axe_chop::tests::strict_axe_validation_emits_only_the_first_description_shape_error ... ok
test axe_chop::tests::strict_axe_validation_counts_description_limits_in_characters ... ok
test axe_chop::tests::strict_axe_validation_gates_description_shape_and_accepts_single_lines ... ok
test axe_chop::tests::strict_axe_validation_rejects_blank_descriptions ... ok
test axe_chop::tests::strict_axe_validation_rejects_blank_fs_paths_and_invalid_watch_spec ... ok
test axe_chop::tests::strict_axe_validation_rejects_fs_trigger_missing_required_fields ... ok
test axe_chop::tests::clan_scoped_proposals_round_trip_without_changing_legacy_proposals ... ok
test axe_chop::tests::strict_axe_validation_rejects_invalid_agent_clan_guards_fail_closed ... ok
test axe_chop::tests::strict_axe_validation_rejects_invalid_agent_runners_guards_fail_closed ... ok
test axe_chop::tests::strict_axe_validation_rejects_non_positive_log_temp_max_age ... ok
test axe_chop::tests::strict_axe_validation_reports_each_description_shape_error_precisely ... ok
test axe_chop::tests::strict_axe_validation_rejects_invalid_wait_runners ... ok
test axe_chop::tests::strict_axe_validation_reports_migrations_duplicates_and_provenance ... ok
test axe_chop::tests::strict_axe_validation_requires_lumberjack_and_chop_descriptions_when_enabled ... ok
test axe_chop::tests::target_expansion_filters_projects_and_separates_overrides ... ok
test axe_chop::tests::result_validation_rejects_forward_wait_and_unknown_fields ... ok
test axe_overrun::tests::action_succeeded_with_script_duration_is_sampled_on_that_value ... ok
test axe_overrun::tests::action_succeeded_without_script_duration_is_ignored ... ok
test axe_chop::tests::target_expansion_uses_stable_hash_without_identity_field ... ok
test axe_overrun::tests::empty_history_is_none_with_null_ratios ... ok
test axe_overrun::tests::exact_equality_counts_as_over ... ok
test axe_overrun::tests::fast_skipped_newest_run_in_front_of_over_success_is_still_over ... ok
test axe_overrun::tests::live_running_run_past_interval_is_over_from_elapsed_time ... ok
test axe_overrun::tests::negative_duration_is_dropped_not_fatal ... ok
test axe_overrun::tests::newest_sampled_run_over_is_over ... ok
test axe_overrun::tests::non_positive_interval_is_an_error ... ok
test axe_overrun::tests::older_overrun_is_locatable_by_run_idx_after_a_healthy_newest_run ... ok
test axe_overrun::tests::only_an_older_run_over_is_intermittent ... ok
test axe_overrun::tests::only_ten_percent_ratio_is_not_over_and_not_intermittent ... ok
test axe_overrun::tests::serde_rejects_unknown_fields_and_invalid_enum_values ... ok
test axe_overrun::tests::structural_validation_returns_path_specific_errors ... ok
test axe_overrun::tests::serialization_pins_public_field_order_and_round_trips ... ok
test axe_overrun::tests::unknown_status_string_is_dropped_not_fatal ... ok
test axe_overrun::tests::unparsable_started_at_is_dropped_for_every_otherwise_sampleable_status ... ok
test axe_status::tests::collection_error_is_a_normal_error_snapshot_with_exit_two ... ok
test axe_status::tests::desired_stopped_with_live_orchestrator_is_degraded ... ok
test axe_status::tests::historical_error_count_does_not_degrade_a_fresh_worker ... ok
test axe_status::tests::lifecycle_matrix_preserves_intent_separately_from_health ... ok
test axe_status::tests::live_lumberjack_without_coherent_orchestrator_is_degraded ... ok
test axe_status::tests::live_orphan_is_retained_and_dead_unconfigured_row_is_filtered ... ok
test axe_status::tests::normalization_is_independent_of_input_order_and_duplicates ... ok
test axe_status::tests::orchestrator_conflicting_live_identities_are_sorted_and_exact ... ok
test axe_status::tests::orchestrator_live_pid_without_lock_has_exact_evidence ... ok
test axe_status::tests::orchestrator_lock_without_live_pid_has_exact_evidence ... ok
test axe_status::tests::lumberjack_state_precedence_and_heartbeat_boundaries_are_pinned ... ok
test axe_overrun::tests::unparsable_started_at_is_dropped_not_fatal ... ok
test axe_status::tests::structural_validation_returns_path_specific_errors ... ok
test axe_status::tests::serde_rejects_unknown_fields_and_invalid_enum_values ... ok
test axe_status::tests::serialization_pins_public_field_order_nulls_lists_and_enum_values ... ok
test bead::cli::tests::close_parser_accepts_force_with_reason_and_resolution ... ok
test bead::cli::tests::colored_type_cell_keeps_alignment_padding_outside_ansi_span ... ok
test bead::cli::tests::close_summary_preserves_requested_ids_and_real_prior_status ... ok
test bead::cli::tests::create_plan_under_in_tree_plans_root_stores_canonical_reference ... ok
test bead::cli::tests::create_plan_path_is_relative_to_store_workspace_from_nested_cwd ... ok
test bead::cli::tests::create_rejects_bare_task_constructor_without_size ... ok
test bead::cli::tests::close_fast_path_accepts_note_and_updates_once ... ok
test bead::cli::tests::design_plan_roots_resolves_the_beads_sidecar_to_its_plans_sibling ... ok
test bead::cli::tests::design_storage_root_resolves_the_beads_sidecar_to_the_workspace ... ok
test bead::cli::tests::create_and_remove_are_handled_with_mutation_summaries ... ok
test bead::cli::tests::claimed_status_is_in_default_list_with_claim_details_and_color ... ok
test axe_chop::diagnostics::tests::byte_bound_keeps_utf8_boundary_and_marks_truncation ... ok
test axe_chop::diagnostics::tests::normalizes_redacts_and_tails_subprocess_output ... ok
test bead::cli::tests::list_compact_colors_shared_type_status_and_id_vocabulary ... ok
test bead::cli::tests::parse_create_type_rejects_retired_flag_form ... ok
test bead::cli::tests::ready_empty_state_explains_epic_preassignment ... ok
test axe_chop::tests::result_validation_accepts_proposals_and_rejects_workflows ... ok
test agent_scan::index::tests::schema_v21_upgrade_backfills_model_alias_projection ... ok
test bead::cli::tests::list_compact_renders_aligned_glyph_only_type_column ... ok
test bead::cli::tests::create_plan_under_sidecar_plans_root_stores_canonical_reference ... ok
test bead::cli::tests::search_compact_color_always_highlights_matches ... ok
test bead::cli::tests::ready_lists_only_unblocked_ready_tasks_with_ready_glyph ... ok
test bead::cli::tests::dependency_remove_is_handled_with_a_batch_mutation_summary ... ok
test bead::cli::tests::remove_handles_multiple_ids_with_unique_output_and_requested_summary ... ok
test bead::cli::tests::search_applies_filters_and_limit ... ok
test bead::cli::tests::search_compact_orders_matches_newest_first ... ok
test bead::cli::tests::search_regex_flag_is_fast_path_only_as_bare_flag ... ok
test bead::cli::tests::remove_missing_later_id_is_an_atomic_fast_path_error ... ok
test bead::cli::tests::search_compact_renders_aligned_glyph_only_type_column ... ok
test bead::cli::tests::search_no_match_is_successful ... ok
test bead::cli::tests::search_regex_invalid_pattern_is_usage_error_across_formats ... ok
test bead::cli::tests::search_compact_renders_name_and_description ... ok
test bead::cli::tests::search_design_matches_canonical_plan_reference ... ok
test bead::cli::tests::create_show_and_ref_verbs_honor_the_reference_contract ... ok
test bead::cli::tests::search_json_renders_stable_uncolored_envelope ... ok
test bead::cli::tests::search_whitespace_query_is_usage_error ... ok
test bead::cli::tests::search_full_reuses_show_rendering_for_single_result ... ok
test bead::cli::tests::show_keeps_one_line_when_a_legacy_path_resolves_to_itself ... ok
test bead::cli::tests::show_reports_a_malformed_reference ... ok
test bead::cli::tests::show_marks_a_reference_resolved_through_month_drift ... ok
test bead::cli::tests::show_reports_an_ambiguous_reference_instead_of_guessing ... ok
test bead::cli::tests::show_resolves_a_legacy_path_against_the_working_directory ... ok
test bead::cli::tests::show_says_plainly_when_a_reference_resolves_nowhere ... ok
test bead::cli::tests::show_renders_reference_above_its_resolved_path ... ok
test axe_chop::tests::clan_summaries_agree_per_raw_clan_before_launch ... ok
test bead::cli::tests::update_fast_path_defers_size_flag_to_python ... ok
test bead::cli::tests::search_regex_zero_width_only_pattern_matches_without_empty_highlights ... ok
test bead::config::tests::load_current_shape ... ok
test bead::cli::tests::stats_prints_ready_and_task_rows ... ok
test bead::config::tests::save_matches_python_pretty_json_shape ... ok
test bead::config::tests::missing_file_returns_supplied_default ... ok
test bead::events::tests::issue_update_event_fields_resolution_round_trips_all_three_encodings ... ok
test bead::events::tests::legacy_note_parser_accepts_crlf_input ... ok
test bead::events::tests::legacy_note_parser_attributes_bare_prose_to_update_event ... ok
test bead::events::tests::concurrently_minted_bead_id_relocates_instead_of_wedging_the_store ... ok
test bead::events::tests::legacy_note_parser_does_not_promote_marker_looking_line_mid_paragraph ... ok
test bead::events::tests::concurrently_minted_child_id_renumbers_to_a_free_sibling ... ok
test bead::events::tests::legacy_note_parser_ignores_empty_and_whitespace_only_blobs ... ok
test bead::events::tests::legacy_note_parser_does_not_promote_unparseable_timestamp_marker ... ok
test bead::events::tests::inbound_link_provenance_projects_bead_as_target ... ok
test bead::events::tests::legacy_note_parser_keeps_prose_before_first_marker_as_one_record ... ok
test bead::events::tests::legacy_note_parser_recovers_pure_appended_blob ... ok
test bead::events::tests::note_append_validation_and_rendering_are_owned_by_the_event ... ok
test bead::events::tests::issue_update_event_fields_round_trip_every_field ... ok
test bead::events::tests::note_edited_rewrites_text_and_stamps_editor ... ok
test bead::cli::tests::update_fast_path_reports_changed_and_unchanged_rows_in_one_commit ... ok
test bead::events::tests::note_removed_retracts_the_record ... ok
test bead::events::tests::merging_without_a_relocation_id_still_reports_the_duplicate ... ok
test bead::events::tests::links_import_round_trip_and_ignore_unknown_historical_payloads ... ok
test bead::events::tests::reduction_collapse_prefers_earlier_created_at_over_id_order ... ok
test bead::events::tests::link_added_provenance_tracks_rewrite_removal_and_readd ... ok
test bead::events::tests::reduction_collapses_duplicate_external_refs_regardless_of_stream_order ... ok
test bead::events::tests::reduction_collapse_does_not_disturb_unrelated_issues ... ok
test bead::events::tests::redundant_close_is_an_exact_no_op ... ok
test bead::events::tests::relocated_events_are_reminted_onto_their_new_stream ... ok
test axe_chop::tests::clan_summary_validation_is_field_specific_and_text_block_safe ... ok
test bead::events::tests::refs_import_as_individual_events_and_replay_idempotently ... ok
test bead::events::tests::relocation_picks_the_same_loser_whichever_side_git_calls_ours ... ok
test bead::history::tests::lost_notes_are_stable_by_issue_id_and_support_one_issue ... ok
test bead::history::tests::lost_notes_ignores_append_only_revision_chains ... ok
test bead::history::tests::external_ref_set_and_clear_are_recorded_in_history ... ok
test bead::history::tests::lost_notes_reports_overwritten_nonempty_revisions ... ok
test bead::history::tests::close_reopen_close_status_timeline_is_complete ... ok
test bead::history::tests::unknown_issue_is_an_error ... ok
test bead::history::tests::merged_order_keeps_appended_predated_event_after_earlier_stream_event ... ok
test bead::history::tests::phase_history_is_read_from_parent_stream ... ok
test bead::history::tests::single_update_and_noop_report_only_real_changes ... ok
test bead::history::tests::notes_history_preserves_each_revision_pair ... ok
test bead::events::tests::three_way_merge_preserves_independent_plus_ones_and_deduplicates_reporter ... ok
test bead::history::tests::removal_ends_the_timeline ... ok
test bead::jsonl::tests::atomic_temp_paths_are_unique_per_process ... ok
test bead::jsonl::tests::atomic_if_changed_skips_identical_bytes ... ok
test bead::jsonl::tests::corrupt_lines_are_skipped ... ok
test bead::jsonl::tests::export_sorts_by_id_and_uses_compact_json ... ok
test bead::jsonl::tests::import_defaults_missing_model_to_empty ... ok
test bead::jsonl::tests::import_defaults_missing_plan_tiers_from_phase_children ... ok
test bead::jsonl::tests::import_preserves_model ... ok
test bead::jsonl::tests::import_rejects_model_control_characters ... ok
test bead::jsonl::tests::import_rejects_duplicate_external_refs ... ok
test bead::jsonl::tests::refs_round_trip_and_empty_refs_do_not_change_jsonl_shape ... ok
test bead::jsonl::tests::unknown_event_operation_names_the_upgrade_remedy ... ok
test bead::jsonl::tests::prune_rejects_live_flag_streams ... ok
test bead::jsonl::tests::write_event_store_changed_rejects_a_changed_ancestor_event ... ok
test bead::jsonl::tests::write_event_store_changed_rejects_a_shortened_ancestor_stream ... ok
test bead::jsonl::tests::write_event_store_changed_appends_to_legacy_stream_without_rewriting_prefix_bytes ... ok
test bead::cli::tests::search_regex_matches_patterns_and_highlights_ranges ... ok
test bead::jsonl::tests::prune_removes_tombstoned_flag_streams_and_rewrites_the_manifest ... ok
test bead::jsonl::tests::write_event_store_changed_writes_selected_streams_and_reloads ... ok
test bead::mutation::tests::absent_resolution_does_not_conflict_with_recorded_canceled_close ... ok
test bead::mutation::tests::agent_claim_mutations_reject_missing_and_blank_requests ... ok
test bead::mutation::tests::append_issue_note_appends_attributed_entries_and_event ... ok
test bead::mutation::tests::a_store_bricked_by_a_close_over_a_snooze_loads_again ... ok
test bead::cli::tests::search_regex_json_marks_regex_mode ... ok
test bead::mutation::tests::append_issue_note_rejects_blank_entry_without_writing ... ok
test bead::mutation::tests::batch_close_preflights_every_request_before_writing ... ok
test bead::mutation::tests::claim_for_agent_launch_rejects_missing_closed_and_blank_requests ... ok
test agent_scan::index::tests::upsert_and_delete_one_artifact_row ... ok
test bead::mutation::tests::append_issue_note_defaults_blank_author_to_store_owner ... ok
test bead::mutation::tests::append_note_preserves_legacy_issue_created_prefix_and_projects_structured_note ... ok
test bead::mutation::tests::an_invalid_derived_state_leaves_the_event_streams_untouched ... ok
test bead::mutation::tests::close_with_note_rejects_blank_entry_without_writing ... ok
test bead::mutation::tests::a_pre_close_history_projection_recovers_its_reason_on_the_next_load ... ok
test bead::mutation::tests::close_records_explicit_resolution_and_reopen_update_clears_it ... ok
test bead::mutation::tests::close_skips_already_closed_issues_without_new_events ... ok
test bead::mutation::tests::claim_for_agent_wait_claims_open_and_is_idempotent_for_same_agent ... ok
test bead::mutation::tests::cancel_task_snooze_returns_the_bead_to_ready ... ok
test bead::mutation::tests::closing_a_snoozed_task_drops_the_record_and_the_store_reloads ... ok
test bead::mutation::tests::conflicting_reason_aborts_before_writing ... ok
test artifact_ref::repository_resolution::tests::matching_revision_is_required_before_a_worktree_path_is_exact ... ok
test bead::mutation::tests::create_and_update_model ... ok
test bead::mutation::tests::close_with_note_appends_to_every_requested_issue_before_close ... ok
test bead::mutation::tests::create_rejects_model_control_characters ... ok
test bead::mutation::tests::create_requires_size_only_for_new_tasks ... ok
test bead::mutation::tests::create_requires_task_type_only_for_new_tasks ... ok
test bead::mutation::tests::conflicting_resolution_aborts_mixed_batch_before_writing ... ok
test bead::mutation::tests::closing_child_epic_closes_completed_parent_phase ... ok
test bead::mutation::tests::create_rejects_duplicate_external_ref_without_writing ... ok
test bead::mutation::tests::claim_for_agent_launch_claims_open_and_reassigns_in_progress_issue ... ok
test axe_chop::tests::clan_scoped_proposals_validate_member_and_directive_shapes ... ok
test bead::mutation::tests::claim_for_agent_wait_declines_other_claims_and_terminal_states_without_writes ... ok
test bead::mutation::tests::concurrent_task_plus_ones_preserve_reporters_and_deduplicate_retries ... ok
test bead::mutation::tests::create_add_and_remove_references_use_individual_events_and_noop_cleanly ... ok
test bead::mutation::tests::deferral_length_label_buckets_and_rounds_half_away_from_zero ... ok
test bead::mutation::tests::concurrent_launch_claims_preserve_sibling_events_and_projection ... ok
test bead::mutation::tests::create_top_level_uses_current_store_max_and_persists_counter ... ok
test bead::mutation::tests::create_uses_explicit_creator_for_issue_and_reference_events ... ok
test bead::mutation::tests::edit_issue_note_rejects_unknown_note_id_without_writing ... ok
test bead::mutation::tests::init_store_writes_a_root_level_store_for_a_dot_dirname ... ok
test bead::mutation::tests::edit_issue_note_rejects_blank_text_without_writing ... ok
test bead::mutation::tests::explicitly_closing_parent_and_child_emits_one_explicit_parent_event ... ok
test bead::mutation::tests::edit_issue_note_rewrites_text_and_preserves_original_authorship ... ok
test bead::mutation::tests::forced_close_plan_sweeps_open_children_before_parent ... ok
test bead::mutation::tests::legacy_jsonl_migration_first_save_writes_every_imported_stream ... ok
test agent_scan::index::tests::late_xprompts_file_refreshes_cached_record ... ok
test bead::mutation::tests::forced_close_plan_sweeps_through_nested_child_epics ... ok
test bead::mutation::tests::forced_close_requires_reason_and_non_done_resolution ... ok
test bead::mutation::tests::mutable_appends_mint_stable_content_hashed_event_ids ... ok
test bead::mutation::tests::mark_ready_rejects_phase_and_idempotent_plan ... ok
test bead::mutation::tests::every_reopen_cause_archives_the_close_reason_it_used_to_destroy ... ok
test bead::mutation::tests::link_operation_ids_make_replay_idempotent_but_keep_distinct_reads ... ok
test bead::mutation::tests::external_ref_create_update_clear_and_batch_conflicts_are_atomic ... ok
test bead::mutation::tests::inbound_direction_link_add_and_remove_round_trip ... ok
test artifact_ref::scanner::tests::document_scan_handles_unsigiled_refs_for_known_kinds ... ok
test bead::mutation::tests::event_backed_child_id_reuse_after_remove_matches_jsonl_semantics ... ok
test bead::mutation::tests::phase_with_blank_parent_creator_falls_back_to_store_owner ... ok
test bead::mutation::tests::mutations_create_canonical_events_and_regenerate_projection ... ok
test bead::mutation::tests::one_mutation_touches_only_the_mutated_stream_file ... ok
test bead::mutation::tests::create_resolves_creator_from_phase_parent_then_store_owner ... ok
test bead::mutation::tests::open_sibling_delegated_work_keeps_parent_phase_open ... ok
test bead::mutation::tests::nested_delegation_closes_only_phase_parents ... ok
test bead::mutation::tests::phase_size_round_trips_through_create_update_events_and_projection ... ok
test bead::mutation::tests::plus_one_below_the_target_leaves_a_snoozed_bead_snoozed ... ok
test artifact_ref::scanner::tests::document_scan_separates_visible_prompt_ref_from_canonical_target ... ok
test bead::mutation::tests::open_issue_no_longer_leaves_stale_close_metadata_in_the_projection ... ok
test bead::mutation::tests::plus_one_at_the_target_wakes_a_snoozed_bead_with_a_preset_note ... ok
test bead::mutation::tests::reference_mutations_reject_malformed_entries_without_writing ... ok
test bead::mutation::tests::out_and_in_direction_links_to_same_target_do_not_collide ... ok
test bead::mutation::tests::remove_issue_note_rejects_unknown_note_id_without_writing ... ok
test bead::mutation::tests::plus_one_never_wakes_a_snoozed_bead_that_set_no_target ... ok
test agent_scan::index::tests::schema_v18_upgrade_adds_xprompts_signature_column ... ok
test bead::mutation::tests::link_mutations_round_trip_and_keep_related_undirected ... ok
test artifact_ref::repository_resolution::tests::mismatching_revision_is_unavailable_even_when_the_path_exists ... ok
test bead::mutation::tests::re_snoozing_appends_a_second_note_naming_the_replaced_wake_time ... ok
test bead::mutation::tests::re_snoozing_replaces_the_record_and_appends_a_second_event ... ok
test bead::mutation::tests::preclaim_epic_work_plan_updates_once_and_returns_rollback ... ok
test bead::mutation::tests::projection_writers_are_byte_stable_for_the_same_store_state ... ok
test bead::mutation::tests::plus_one_close_record_joins_its_evidence_entry_exactly ... ok
test bead::mutation::tests::remove_issues_rejects_an_empty_request ... ok
test bead::mutation::tests::preclaim_epic_work_plan_validation_is_all_or_nothing ... ok
test bead::mutation::tests::release_agent_claim_declines_in_progress_and_closed_without_writes ... ok
test bead::mutation::tests::remove_issue_note_retracts_the_record_and_history_still_replays_it ... ok
test bead::mutation::tests::remove_issues_deduplicates_duplicate_requests_and_events ... ok
test bead::mutation::tests::remove_dependencies_validates_the_whole_batch_before_writing ... ok
test bead::mutation::tests::removing_child_epic_does_not_close_parent_phase ... ok
test bead::mutation::tests::remove_dependencies_rejects_an_unknown_source_without_writing ... ok
test bead::mutation::tests::remove_issues_deduplicates_overlapping_roots_in_both_orders ... ok
test bead::mutation::tests::remove_plan_cascades_through_nested_child_epics ... ok
test bead::mutation::tests::repeat_close_is_write_free_and_classified_as_already_closed ... ok
test bead::mutation::tests::reopening_grandchild_reopens_closed_ancestors_and_clears_resolution ... ok
test bead::mutation::tests::remove_issues_removes_independent_roots_in_argument_order ... ok
test bead::mutation::tests::release_agent_claim_is_owner_guarded_and_round_trips_to_open ... ok
test bead::mutation::tests::repeat_close_with_note_writes_only_the_note ... ok
test bead::mutation::tests::snooze_task_rejects_non_task_beads ... ok
test bead::mutation::tests::remove_issues_missing_later_id_leaves_store_unchanged ... ok
test bead::mutation::tests::snooze_task_records_wake_conditions_and_replays_from_events ... ok
test bead::mutation::tests::snooze_task_rejects_bad_targets_times_and_statuses ... ok
test bead::mutation::tests::task_type_create_rejects_cross_field_and_slug_errors ... ok
test bead::mutation::tests::snooze_task_with_no_reason_or_target_still_names_the_wake_conditions ... ok
test bead::mutation::tests::update_fields_resolution_preserves_omitted_clear_and_set ... ok
test bead::mutation::tests::sase_mk_blast_radius_regression_preserves_unrelated_stream_bytes ... ok
test bead::mutation::tests::unforced_close_with_open_descendant_fails_without_writing ... ok
test bead::mutation::tests::task_plus_one_creator_and_repeat_are_byte_identical_noops ... ok
test bead::mutation::tests::task_type_round_trips_through_create_events_and_projection ... ok
test bead::mutation::tests::task_plus_one_fresh_observation_window_reopens_closed_task_and_clears_assignee ... ok
test bead::mutation::tests::task_plus_one_is_atomic_normalized_and_promotes_closed_task ... ok
test bead::mutation::tests::update_issues_invalid_field_value_leaves_every_target_unmodified ... ok
test bead::mutation::tests::update_issues_collapses_duplicate_ids_to_one_update ... ok
test bead::mutation::tests::task_plus_one_stale_observation_window_records_without_reopening_closed_task ... ok
test bead::mutation::tests::update_issues_unknown_id_leaves_store_untouched ... ok
test bead::mutation::tests::update_issues_mixed_batch_reports_changed_and_unchanged ... ok
test bead::mutation::tests::update_issues_applies_same_fields_to_every_target_in_one_pass ... ok
test bead::mutation::tests::update_status_closed_rejects_open_descendants ... ok
test bead::mutation::tests::update_refuses_the_snoozed_status_shortcut ... ok
test bead::read::tests::claimed_dependency_is_an_active_blocker ... ok
test bead::read::tests::claimed_status_filter_is_parsed_and_counted ... ok
test bead::mutation::tests::update_issues_status_closed_rejects_out_of_batch_descendant ... ok
test bead::read::tests::doctor_ignores_transient_mutation_holder_metadata ... ok
test bead::read::tests::ready_query_returns_only_unblocked_ready_tasks ... ok
test bead::mutation::tests::task_create_and_ready_updates_round_trip_through_events ... ok
test bead::mutation::tests::update_out_of_closed_reopens_closed_ancestor ... ok
test bead::mutation::tests::update_issues_reopens_shared_ancestor_only_once ... ok
test bead::read::tests::doctor_marks_unavailable_reference_context_as_skipped ... ok
test bead::read::tests::resolve_issue_id_accepts_full_ids_and_unique_suffixes ... ok
test bead::mutation::tests::update_issues_closes_parent_and_child_regardless_of_argument_order ... ok
test bead::read::tests::resolve_issue_id_reports_unknown_and_ambiguous_suffixes ... ok
test bead::read::tests::reference_diagnostics_groups_unknown_missing_and_ambiguous_entries ... ok
test bead::read::tests::stats_derive_plus_one_total_from_structured_evidence ... ok
test bead::schema::tests::flag_type_admission_only_fires_on_pre_flag_pre_task_type_schema ... ok
test bead::mutation::tests::update_issue_resolution_omitted_null_and_set_mutate_deliberately ... ok
test bead::mutation::tests::remove_dependencies_records_the_full_removed_edge ... ok
test bead::schema::tests::metadata_migration_adds_only_missing_columns ... ok
test bead::mutation::tests::update_with_matching_fields_is_a_quiet_no_op ... ok
test bead::mutation::tests::update_replaces_task_type_fields_and_replays_from_events ... ok
test bead::schema::tests::migration_detection_matches_python_helpers ... ok
test bead::mutation::tests::repeated_close_episodes_append_oldest_first_with_their_causes ... ok
test bead::mutation::tests::reopening_and_launch_claiming_a_snoozed_task_drop_the_record ... ok
test bead::mutation::tests::reopening_a_bead_that_was_never_closed_archives_nothing ... ok
test bead::mutation::tests::remove_dependencies_batches_and_deduplicates_targets ... ok
test bead::mutation::tests::updating_a_snoozed_bead_off_snoozed_drops_the_record ... ok
test bead::mutation::tests::mutation_and_reducer_agree_on_every_reopen_path ... ok
test artifact_ref::scanner::tests::document_scan_uses_markdown_destination_for_ordinary_links ... ok
test bead::schema::tests::schema_contains_current_constraints ... ok
test bead::search::tests::closed_issues_match_by_default ... ok
test bead::search::tests::field_names_constant_matches_all_collectable_fields ... ok
test bead::search::tests::invalid_regex_is_a_validation_error ... ok
test bead::search::tests::filters_status_type_and_tier_together ... ok
test bead::search::tests::issues_without_close_history_do_not_match_an_archived_reason ... ok
test bead::search::tests::limit_keeps_newest_matches ... ok
test bead::search::tests::literal_search_treats_regex_metacharacters_literally ... ok
test bead::search::tests::matches_an_archived_close_reason ... ok
test bead::mutation::tests::task_plus_one_open_and_active_statuses_preserve_existing_contract ... ok
test bead::search::tests::literal_match_truth_uses_plain_case_folded_containment ... ok
test bead::search::tests::matches_an_archived_resolution ... ok
test bead::search::tests::matches_case_insensitive_unicode_substrings ... ok
test bead::search::tests::no_match_returns_empty_results ... ok
test bead::search::tests::rejects_empty_or_whitespace_query ... ok
test bead::search::tests::regex_search_allows_inline_case_sensitivity ... ok
test bead::search::tests::public_search_loads_store_and_returns_wire_matches ... ok
test bead::search::tests::zero_limit_is_unlimited ... ok
test bead::search::tests::matches_every_searchable_field ... ok
test bead::search::tests::returns_newest_matches_before_older_matches ... ok
test artifact_ref::scanner::tests::document_scan_keeps_generated_links_table_ref_and_hosted_url ... ok
test bead::wire::tests::bug_id_requires_changespec_name ... ok
test bead::wire::tests::close_history_omits_absent_reason_and_resolution ... ok
test bead::wire::tests::close_history_is_allowed_on_every_issue_type ... ok
test bead::wire::tests::claimed_status_round_trips_through_serde ... ok
test bead::search::tests::regex_search_matches_patterns_case_insensitively_by_default ... ok
test bead::search::tests::zero_width_regex_matches_truth_but_not_highlight_ranges ... ok
test bead::wire::tests::close_history_validation_rejects_blank_fields ... ok
test bead::wire::tests::empty_optional_strings_normalize_to_none ... ok
test bead::wire::tests::close_history_round_trips_and_stays_absent_when_empty ... ok
test bead::wire::tests::empty_task_type_normalizes_to_none ... ok
test bead::wire::tests::empty_phase_size_normalizes_to_none_and_invalid_values_fail ... ok
test bead::wire::tests::external_ref_round_trips_when_non_empty ... ok
test bead::search::tests::zero_width_regex_matches_fields ... ok
test bead::wire::tests::legacy_defaults_match_python_jsonl_loader ... ok
test bead::wire::tests::model_rejects_control_characters ... ok
test bead::wire::tests::phase_rejects_plan_only_fields ... ok
test bead::wire::tests::phase_requires_parent ... ok
test bead::wire::tests::ready_status_requires_task_type ... ok
test bead::wire::tests::snooze_metadata_requires_snoozed_status ... ok
test bead::wire::tests::phase_size_round_trips_all_enum_values_and_rejects_plan_usage ... ok
test bead::wire::tests::snoozed_status_requires_a_task_and_a_record ... ok
test bead::wire::tests::snooze_key_is_absent_when_the_bead_is_not_snoozed ... ok
test bead::wire::tests::resolution_round_trips_and_requires_closed_status ... ok
test bead::wire::tests::snooze_record_validates_its_own_fields ... ok
test bead::wire::tests::snoozed_status_round_trips_with_its_record ... ok
test bead::mutation::tests::bead_mutation_lock_contention_times_out ... ok
test bead::wire::tests::task_plus_one_evidence_validates_structure_and_reporter_uniqueness ... ok
test bead::wire::tests::task_type_is_rejected_on_non_task_issues ... ok
test bead::wire::tests::task_type_and_field_keys_must_be_bounded_snake_case ... ok
test bead::wire::tests::task_validation_allows_size_and_ready_but_rejects_plan_fields ... ok
test bead::wire::tests::task_type_fields_require_task_type ... ok
test bead::wire::tests::task_type_round_trips_and_stays_absent_when_empty ... ok
test bead::work::tests::child_epics_are_excluded_from_parent_waves ... ok
test bead::work::tests::claimed_phase_is_still_scheduled ... ok
test bead::work::tests::closed_only_plan_returns_land_only_work_plan ... ok
test bead::work::tests::closed_in_epic_blocker_is_only_a_bead_wait ... ok
test bead::work::tests::delegated_phase_is_excluded_but_remains_a_bead_blocker ... ok
test bead::work::tests::delegated_only_plan_has_no_waves ... ok
test bead::work::tests::closed_or_removed_child_plan_does_not_exclude_phase ... ok
test bead::work::tests::epic_work_plan_copies_phase_and_land_models ... ok
test bead::work::tests::detects_cycles ... ok
test bead::work::tests::land_waits_on_every_launched_phase_in_wave_order ... ok
test bead::work::tests::missing_out_of_epic_blocker_is_satisfied_with_warning ... ok
test bead::work::tests::parent_does_not_change_epic_launch_tag ... ok
test bead::work::tests::rejects_open_out_of_epic_blocker ... ok
test bead::work::tests::total_phase_count_includes_closed_phases ... ok
test bead::work::tests::standalone_epic_uses_epic_launch_tag ... ok
test commit_footer::tests::parses_linked_values_and_reference_destinations ... ok
test commit_footer::tests::ordinary_reference_definitions_and_mid_message_tags_remain_body ... ok
test bead::work::tests::plans_diamond_dag_in_waves ... ok
test commit_footer::tests::new_links_allocate_numeric_ids_without_body_or_footer_collisions ... ok
test commit_footer::tests::adding_tags_preserves_link_and_definition_below_complete_tag_block ... ok
test bead::work::tests::rejects_epic_with_no_phase_children ... ok
test commit_footer::tests::parses_plain_prefixed_and_legacy_tags_with_later_duplicates ... ok
test commit_footer::tests::repeated_updates_are_idempotent_and_preserve_trailing_shape ... ok
test commit_footer::tests::shared_targets_reuse_one_definition_deterministically ... ok
test commit_footer::tests::replacing_or_removing_linked_tags_cleans_only_owned_definitions ... ok
test commit_sha::tests::equivalent_sha_matrix ... ok
test commit_sha::tests::rejects_ambiguous_or_invalid_shas ... ok
test commit_subject::tests::exposes_stable_ordered_defaults ... ok
test commit_subject::tests::exempts_git_generated_and_rebase_subjects ... ok
test commit_subject::tests::honors_custom_allowed_types ... ok
test commit_subject::tests::parses_plain_scoped_breaking_and_spaced_subjects ... ok
test commit_subject::tests::reads_only_the_trimmed_first_line ... ok
test commit_subject::tests::rejects_empty_descriptions_and_subjects ... ok
test commit_subject::tests::rejects_missing_or_malformed_type_separator ... ok
test commit_subject::tests::reports_uppercase_before_unknown_type ... ok
test content_layout::tests::collision_policy_is_exclusive_for_config_and_first_wins_for_xprompts ... ok
test content_layout::tests::memory_references_are_always_the_flat_namespaced_filename ... ok
test content_layout::tests::memory_tier_parses_current_and_legacy_note_types ... ok
test content_layout::tests::memory_sources_are_project_before_home_with_exclusive_read_policy ... ok
test content_layout::tests::memory_tier_serializes_current_names_and_deserializes_legacy_names ... ok
test content_layout::tests::missing_project_root_still_returns_complete_home_contract ... ok
test content_layout::tests::ref_directories_are_canonical ... ok
test content_layout::tests::memory_rules_reject_reserved_names_bad_stems_and_bad_tiers ... ok
test content_layout::tests::skill_placement_issues_name_the_move_in_both_directions ... ok
test content_layout::tests::skill_reference_names_split_provider_name_from_xprompt_reference ... ok
test content_layout::tests::skill_sources_are_ordered_first_wins_with_no_legacy_paths ... ok
test content_layout::tests::xprompt_priority_covers_canonical_legacy_config_plugin_and_package ... ok
test content_layout::tests::skill_directories_are_canonical_in_every_scope ... ok
test content_layout::tests::project_and_home_paths_keep_runtime_and_generated_content_separate ... ok
test editor::at_reference::tests::bare_menu_groups_builtins_then_sorted_kinds_and_visible_paths ... ok
test editor::at_reference::tests::detects_path_shaped_kind_queries ... ok
test editor::at_reference::tests::dotfile_visibility_tracks_the_trailing_partial ... ok
test agent_scan::index::tests::schema_v24_upgrade_backfills_done_outcome_projection ... ok
test editor::at_reference::tests::gated_menu_without_matching_paths_does_not_offer_an_empty_reveal ... ok
test editor::at_reference::tests::fuzzy_kind_matches_do_not_gate_file_rows ... ok
test editor::at_reference::tests::fuzzy_kind_menu_keeps_builtin_ties_and_reports_runs ... ok
test editor::at_reference::tests::indexed_payload_menu_matches_the_wire_inventory_path ... ok
test editor::at_reference::tests::kind_and_file_groups_filter_independently ... ok
test editor::at_reference::tests::malformed_scope_degrades_to_an_unscoped_row ... ok
test editor::at_reference::tests::path_menu_fuzzy_matches_only_the_trailing_partial ... ok
test editor::at_reference::tests::payload_menu_includes_title_only_matches ... ok
test editor::at_reference::tests::payload_menu_is_path_first_and_ranks_both_match_fields ... ok
test editor::at_reference::tests::payload_menu_preserves_empty_query_provider_order ... ok
test editor::at_reference::tests::payload_wire_defaults_new_metadata_when_deserializing_old_rows ... ok
test artifact_ref::scanner::tests::document_scan_keeps_urls_whole_without_inner_file_links ... ok
test editor::at_reference::tests::payload_rank_breaks_quality_ties_but_unranked_rows_keep_text_order ... ok
test editor::at_reference::tests::shared_extension_requires_an_all_prefix_leading_group ... ok
test editor::at_reference::tests::caps_each_group_but_records_pre_cap_counts ... ok
test editor::at_reference::tests::qualified_match_highlights_each_field_and_drops_straddling_runs ... ok
test editor::at_reference::tests::scoped_payload_matches_repo_and_title_as_one_qualified_target ... ok
test editor::at_reference::tests::rejects_prose_invalid_characters_and_literal_zones ... ok
test editor::at_reference::tests::shared_extension_uses_only_the_leading_non_empty_group ... ok
test editor::completion::tests::agent_candidates_carry_documentation_only_when_present ... ok
test editor::at_reference::tests::payload_caps_report_matches_and_caller_truncation ... ok
test editor::at_reference::tests::detects_kind_and_payload_at_every_cursor_position ... ok
test editor::completion::tests::agent_and_indexed_file_payloads_match_mid_name_fragments ... ok
test editor::completion::tests::agent_candidates_are_kind_aware_ordered_and_compatible ... ok
test editor::completion::tests::artifact_kind_candidates_list_builtins_in_documented_order ... ok
test editor::completion::tests::artifact_replacement_ranges_are_utf16_safe_and_at_paths_stay_references ... ok
test editor::completion::tests::builds_catalog_completions_with_marker_filters ... ok
test editor::completion::tests::builds_argument_name_completions ... ok
test editor::completion::tests::builds_snippet_completions_by_case_insensitive_prefix ... ok
test editor::completion::tests::builds_bead_payload_candidates_from_published_pages ... ok
test editor::completion::tests::builds_chat_and_indexed_file_payloads_but_not_remote_kinds ... ok
test editor::completion::tests::builds_agent_payload_candidates_from_published_pages ... ok
test editor::completion::tests::builds_dynamic_kind_and_payload_candidates ... ok
test editor::completion::tests::commit_age_label_applies_the_utc_offset_before_the_date_falls_back ... ok
test editor::completion::tests::classifies_artifact_kind_and_payload_at_every_cursor_position ... ok
test editor::completion::tests::commit_age_labels_match_prompt_bar_thresholds ... ok
test editor::completion::tests::classifies_vcs_repo_then_vcs_ref_before_xprompt_argument_hints ... ok
test editor::completion::tests::classifies_primary_completion_modes ... ok
test editor::completion::tests::classifies_vcs_project_trigger ... ok
test editor::completion::tests::classifies_vcs_repo_then_vcs_ref_then_xprompt_args ... ok
test editor::completion::tests::closed_placeholder_does_not_steal_following_context ... ok
test editor::completion::tests::bof_trigger_merges_into_single_primary_edit ... ok
test editor::completion::tests::commit_inventory_reports_the_merged_row_cap ... ok
test editor::completion::tests::agent_prefix_query_survives_a_corpus_of_fuzzy_matches ... ok
test editor::completion::tests::commit_log_failures_report_the_underlying_os_error ... ok
test bead::schema::tests::plus_one_evidence_migration_defaults_legacy_rows_to_empty_json ... ok
test editor::completion::tests::commit_merge_ties_break_by_repository_then_sha ... ok
test editor::completion::tests::commit_timeout_override_accepts_only_positive_finite_seconds ... ok
test editor::completion::tests::commit_timeout_reads_the_documented_environment_override ... ok
test editor::completion::tests::detects_narrow_argument_contexts ... ok
test editor::completion::tests::detects_vcs_ref_colon_spans ... ok
test editor::completion::tests::detects_vcs_ref_paren_hitl ... ok
test editor::completion::tests::detects_vcs_repo_colon_spans ... ok
test editor::completion::tests::detects_vcs_repo_paren_hitl_and_nested_namespaces ... ok
test editor::completion::tests::directive_keyword_completion_stays_out_of_positional_and_value_positions ... ok
test editor::completion::tests::directive_keyword_completion_targets_only_the_post_comma_fragment ... ok
test editor::completion::tests::effort_and_auto_directive_arguments_classify_with_candidates ... ok
test editor::completion::tests::final_directive_completes_add_and_remove_instance_selectors ... ok
test editor::completion::tests::final_directive_documents_provider_dependencies_and_retry_policy ... ok
test editor::completion::tests::final_directive_omits_required_from_remove_and_clear_when_invalid ... ok
test bead::schema::tests::resolution_migration_preserves_legacy_rows_without_backfill ... ok
test editor::completion::tests::commit_log_distinguishes_every_unusable_repository_outcome ... ok
test bead::schema::tests::external_ref_migration_adds_nullable_partial_unique_index ... ok
test editor::completion::tests::final_directive_orders_required_default_optional_then_clear ... ok
test editor::completion::tests::commit_inventory_is_empty_for_sidecar_only_context ... ok
test editor::completion::tests::memory_completes_only_through_the_memory_namespace ... ok
test editor::completion::tests::final_directive_replaces_only_the_active_parenthesized_clause ... ok
test editor::completion::tests::model_at_suffix_completes_effort_vocabulary ... ok
test editor::completion::tests::payload_inventory_applies_document_root_path_globs ... ok
test editor::completion::tests::placeholder_context_precedes_other_explicit_completion_modes ... ok
test editor::completion::tests::repeatable_agent_context_replaces_earlier_element_and_filters_selected ... ok
test editor::completion::tests::repeatable_positionals_keep_the_tail_input_and_active_element_range ... ok
test editor::completion::tests::snippet_context_does_not_steal_higher_priority_tokens ... ok
test editor::completion::tests::vcs_prepend_offset_skips_horizontal_whitespace_only ... ok
test editor::completion::tests::trailing_trigger_emits_primary_plus_additional_edit ... ok
test agent_scan::index::tests::windowed_query_applies_safe_candidate_filter ... ok
test editor::completion::tests::vcs_project_candidates_accept_legacy_changespec_kind ... ok
test editor::completion::tests::vcs_project_candidates_filter_for_bare_plus_query ... ok
test editor::completion::tests::vcs_project_candidates_filter_preserves_catalog_order ... ok
test editor::completion::tests::vcs_project_candidates_include_patch_context ... ok
test editor::completion::tests::payload_enumeration_is_bounded_and_deduplicated ... ok
test editor::completion::tests::vcs_ref_accept_preserves_visible_space_before_document_final_newline ... ok
test editor::completion::tests::vcs_project_candidates_match_aliases ... ok
test editor::completion::tests::vcs_ref_builder_groups_rows_and_replaces_root_ref ... ok
test editor::completion::tests::vcs_ref_golden_vectors ... ok
test editor::completion::tests::vcs_ref_trigger_negatives ... ok
test editor::completion::tests::vcs_repo_builder_replaces_only_the_ref_value ... ok
test editor::completion::tests::vcs_repo_golden_vectors ... ok
test editor::completion::tests::vcs_repo_trigger_negatives ... ok
test editor::completion::tests::vcs_ref_builder_filters_by_query_and_alias ... ok
test editor::completion::tests::wait_candidates_merge_keywords_and_exclude_selected_values ... ok
test editor::completion::tests::payload_inventory_reaches_past_the_editor_display_cap ... ok
test editor::definition::tests::navigates_from_a_memory_reference_to_the_memory_note ... ok
test editor::completion::tests::wait_context_narrows_to_active_clause_and_tracks_selected_values ... ok
test agent_scan::index::tests::hidden_terminal_retention_prunes_dependents_and_is_idempotent ... ok
test editor::definition::tests::preserves_catalog_definition_range ... ok
test editor::definition::tests::resolves_inline_and_standalone_xprompt_definitions ... ok
test editor::definition::tests::resolves_namespaced_shorthand_and_slash_skill_definitions ... ok
test editor::definition::tests::returns_none_for_missing_entries_or_source_targets ... ok
test editor::definition::tests::validates_local_file_definition_paths_conservatively ... ok
test editor::completion::tests::commit_inventory_preserves_subject_and_multiline_body ... ok
test agent_scan::index::tests::windowed_query_decodes_only_selected_candidates ... ok
test editor::completion::tests::commit_inventory_enforces_the_per_repository_scan_limit ... ok
test editor::diagnostics::tests::artifact_diagnostics_report_malformed_and_unresolved_known_kinds ... ok
test editor::diagnostics::tests::artifact_diagnostics_report_unresolved_bead_pages ... ok
test editor::diagnostics::tests::artifact_diagnostics_resolve_document_chat_and_file_locally ... ok
test editor::diagnostics::tests::artifact_diagnostics_shape_check_commit_and_bug_without_resolution ... ok
test agent_scan::index::tests::bounded_query_retains_dismissed_clan_declaration_as_context ... ok
test editor::diagnostics::tests::artifact_diagnostics_skip_literal_ranges_and_unknown_kinds ... ok
test editor::completion::tests::vcs_project_edits_never_overlap ... ok
test bead::schema::tests::task_type_migration_adds_columns_index_and_check ... ok
test editor::diagnostics::tests::keywords_do_not_restore_dynamic_memory_matching ... ok
test editor::diagnostics::tests::accepts_valid_argument_forms_and_bool_spellings ... ok
test editor::diagnostics::tests::queue_directive_diagnostics_are_retired ... ok
test editor::diagnostics::tests::accepts_current_document_local_xprompts_and_validates_args ... ok
test editor::diagnostics::tests::incomplete_forms_do_not_emit_required_arg_noise ... ok
test editor::diagnostics::tests::reports_flow_style_frontmatter_input_type_diagnostic ... ok
test editor::diagnostics::tests::accepts_valid_input_aliases_and_defaults ... ok
test editor::diagnostics::tests::repeatable_tail_accepts_and_validates_every_element ... ok
test editor::diagnostics::tests::recognizes_current_directives_but_rejects_removed_spellings ... ok
test editor::diagnostics::tests::accepts_frontmatter_local_xprompts ... ok
test editor::diagnostics::tests::accepts_known_frontmatter_input_type_aliases ... ok
test editor::diagnostics::tests::reports_flow_style_input_default_on_offending_scalar ... ok
test editor::diagnostics::tests::reports_frontmatter_yaml_and_shape_diagnostics ... ok
test editor::diagnostics::tests::reports_invalid_snippet_tags_keywords_and_skill_metadata ... ok
test editor::diagnostics::tests::accepts_input_descriptions_and_reports_invalid_shapes ... ok
test agent_stats::activity::tests::counts_gate_even_when_index_row_is_hidden_abandoned ... ok
test editor::diagnostics::tests::reports_input_shape_name_duplicate_identifier_and_unknown_fields ... ok
test editor::diagnostics::tests::reports_initial_diagnostics ... ok
test editor::diagnostics::tests::reports_shortform_frontmatter_input_type_diagnostic ... ok
test editor::directive::tests::alt_metadata_advertises_brace_shorthand ... ok
test editor::diagnostics::tests::reports_unknown_top_level_and_invalid_name ... ok
test editor::diagnostics::tests::slash_skills_resolve_by_provider_name_not_xprompt_reference ... ok
test editor::directive::tests::auto_metadata_describes_gate_owned_resolution_and_offers_compatibility_suggestions ... ok
test editor::diagnostics::tests::reports_invalid_input_defaults ... ok
test editor::directive::tests::bead_ranking_matches_wait_modal_order_and_filters ... ok
test editor::directive::tests::clan_metadata_matches_the_editor_contract ... ok
test editor::directive::tests::comma_adjacent_space_keeps_the_wait_list_body ... ok
test editor::diagnostics::tests::reports_xprompt_argument_contract_diagnostics ... ok
test editor::directive::tests::directive_completion_t_prefix_is_empty ... ok
test editor::directive::tests::cursor_in_prose_past_a_directive_has_no_context ... ok
test editor::diagnostics::tests::reports_longform_frontmatter_input_type_diagnostic ... ok
test editor::directive::tests::contract_covers_the_audited_directive_matrix ... ok
test editor::directive::tests::final_directive_is_public_in_name_completion ... ok
test editor::directive::tests::id_and_clan_keyword_values_and_conflicts_classify ... ok
test editor::directive::tests::id_metadata_and_completion_match_the_editor_contract ... ok
test editor::directive::tests::incomplete_and_malformed_calls_still_classify ... ok
test editor::directive::tests::clause_candidates_cover_roles_conflicts_and_self_references ... ok
test editor::directive::tests::keyword_candidates_suppress_selected_and_conflicting_names ... ok
test editor::directive::tests::queue_argument_candidates_use_runtime_keywords ... ok
test editor::directive::tests::effort_argument_candidates_are_the_canonical_vocabulary ... ok
test editor::directive::tests::effort_is_a_recognized_directive_with_e_alias ... ok
test editor::directive::tests::quoted_wait_value_keeps_its_inner_space ... ok
test editor::directive::tests::quoted_and_text_block_commas_do_not_split_clauses ... ok
test editor::directive::tests::removed_auto_approve_aliases_do_not_resolve_or_complete ... ok
test editor::directive::tests::unclosed_paren_body_stops_at_prose ... ok
test editor::directive::tests::unterminated_wait_colon_body_stops_at_prose ... ok
test agent_stats::run::tests::aggregates_swarm_xprompt_kind_through_stats_wire ... ok
test editor::directive::tests::wait_argument_candidates_use_runtime_keywords ... ok
test editor::directive::tests::utf16_positions_classify_the_active_wait_clause ... ok
test editor::directive::tests::resolves_documented_aliases ... ok
test editor::directive::tests::wait_bead_value_is_a_keyword_value_clause ... ok
test editor::directive::tests::removed_identity_directives_do_not_resolve_or_complete ... ok
test editor::frontmatter::tests::hover_documents_log_skill_use_field ... ok
test editor::file::tests::orders_directories_first_and_filters_dotfiles ... ok
test editor::frontmatter::tests::input_type_schema_matches_parser_spellings ... ok
test editor::frontmatter::tests::field_schema_is_ordered_documented_and_parity_scoped ... ok
test editor::directive::tests::wait_paren_keywords_are_not_offered_in_colon_form ... ok
test editor::file::tests::preserves_at_prefix_and_marks_symlinked_directories ... ok
test editor::frontmatter::tests::validate_accepts_bare_body_without_delimiters ... ok
test editor::frontmatter::tests::validate_accepts_log_skill_use_boolean ... ok
test editor::frontmatter::tests::validate_accepts_known_good_block ... ok
test editor::frontmatter::tests::validate_accepts_enum_choices_shortform_and_longform ... ok
test editor::frontmatter::tests::validate_checks_enum_default_membership ... ok
test editor::frontmatter::tests::validate_field_handles_block_values ... ok
test editor::frontmatter::tests::validate_flags_duplicate_choice_values ... ok
test editor::frontmatter::tests::validate_field_isolates_a_single_property ... ok
test editor::frontmatter::tests::validate_flags_enum_without_choices ... ok
test editor::frontmatter::tests::validate_flags_known_bad_input_type ... ok
test editor::frontmatter::tests::validate_flags_non_boolean_log_skill_use ... ok
test agent_scan::index::tests::alias_history_projection_replaces_and_deletes_rows ... ok
test editor::diagnostics::tests::typed_launch_diagnostics_follow_flag_and_scanner_results ... ok
test editor::fuzzy::tests::basename_retry_beats_a_cross_directory_alignment ... ok
test editor::fuzzy::tests::classifies_all_match_tiers ... ok
test editor::fuzzy::tests::empty_query_matches_and_missing_subsequence_does_not ... ok
test editor::fuzzy::tests::reports_character_ranges_for_non_ascii_text ... ok
test editor::fuzzy::tests::rewards_separator_and_camel_case_boundaries ... ok
test editor::fuzzy::tests::tightens_site_to_the_contiguous_segment ... ok
test editor::fuzzy::tests::comparator_is_deterministic_under_shuffled_input ... ok
test editor::hover::tests::builds_frontmatter_field_hover ... ok
test editor::hover::tests::frontmatter_hover_ignores_body_and_non_field_positions ... ok
test editor::frontmatter::tests::validate_flags_choices_on_non_enum_type ... ok
test editor::frontmatter::tests::validates_repeatable_input_metadata_and_final_position ... ok
test editor::hover::tests::directive_argument_hover_uses_current_identity_and_clan_metadata ... ok
test editor::hover::tests::hovers_an_xprompt_memory_with_its_kind_and_tier ... ok
test editor::hover::tests::builds_xprompt_and_argument_hover ... ok
test editor::model_alias_shortcut::tests::detects_model_shortcut_context_without_alias_wrapper_fallback ... ok
test editor::model_alias_shortcut::tests::filter_explicit_model_shortcut_entries_keeps_models_only ... ok
test editor::model_alias_shortcut::tests::detects_start_space_and_logical_line_boundaries ... ok
test editor::model_alias_shortcut::tests::accepts_safe_model_punctuation_and_nested_provider_values ... ok
test editor::model_alias_shortcut::tests::filter_model_alias_shortcut_entries_restricts_to_alias_kinds_in_catalog_order ... ok
test editor::hover::tests::hovers_a_skill_through_both_of_its_names ... ok
test editor::model_alias_shortcut::tests::rejects_literal_model_star_tokens ... ok
test editor::model_alias_shortcut::tests::rejects_embedded_escaped_tabs_and_completed_emphasis ... ok
test editor::model_alias_shortcut::tests::preserves_or_adds_whitespace_after_expansion ... ok
test editor::model_alias_shortcut::tests::plans_full_token_replacement_from_mid_token_caret ... ok
test editor::model_alias_shortcut::tests::planned_caret_always_equals_end_of_applied_edit ... ok
test editor::model_alias_shortcut::tests::plans_explicit_model_replacement_and_validates_selection ... ok
test editor::model_alias_shortcut::tests::rejects_unsafe_shortcut_values_before_emitting_model_directive ... ok
test editor::model_alias_shortcut::tests::utf16_positions_survive_unicode_and_crlf ... ok
test editor::placeholder::tests::appends_common_candidates_after_prompt_candidates_in_caller_order ... ok
test editor::placeholder::tests::an_empty_common_slice_leaves_document_only_output_unchanged ... ok
test editor::placeholder::tests::completion_edits_leave_the_cursor_after_a_closing_bracket ... ok
test editor::placeholder::tests::completion_candidates_rank_literal_spans_after_live_spans ... ok
test editor::placeholder::tests::completion_list_details_reflect_the_candidate_source ... ok
test editor::placeholder::tests::dedups_common_candidates_against_the_prompt_and_each_other ... ok
test editor::placeholder::tests::detects_context_with_and_without_a_closing_bracket ... ok
test editor::placeholder::tests::candidates_serialize_with_a_lowercase_source_tag ... ok
test editor::model_alias_shortcut::tests::validates_selected_alias_against_current_filtered_aliases ... ok
test editor::completion::tests::vcs_project_golden_vectors ... ok
test editor::placeholder::tests::excludes_the_span_under_the_cursor ... ok
test editor::placeholder::tests::live_candidate_dedups_literal_and_common_occurrences_at_live_position ... ok
test editor::placeholder::tests::filters_prefix_case_insensitively_and_handles_utf16_ranges ... ok
test editor::model_alias_shortcut::tests::rejects_literal_regions_and_frontmatter ... ok
test editor::placeholder::tests::slugs_unicode_names_and_resolves_collisions_in_input_order ... ok
test editor::placeholder::tests::builds_deduplicated_document_order_candidates ... ok
test editor::placeholder::tests::substitutes_only_mapped_raw_spans_without_rescanning_values ... ok
test editor::placeholder::tests::summarizes_exact_raw_fields_with_bounded_context ... ok
test editor::placeholder::tests::extracts_strict_single_line_spans_including_code ... ok
test editor::placeholder::tests::filters_common_candidates_with_the_same_prefix_rule ... ok
test editor::placeholder::tests::rejects_context_after_an_intervening_closing_bracket ... ok
test editor::token::tests::extracts_mid_token_ranges ... ok
test editor::token::tests::recognizes_canonical_and_legacy_memory_markdown_source_paths ... ok
test editor::token::tests::recognizes_prompt_widget_snippet_trigger_tokens ... ok
test editor::token::tests::detects_vcs_project_trigger_tokens ... ok
test editor::xprompt_args::tests::marks_open_forms_without_parsing_required_args ... ok
test editor::token::tests::maps_lsp_utf16_positions_defensively ... ok
test editor::token::tests::vcs_project_trigger_requires_bof_or_literal_space ... ok
test editor::xprompt_args::tests::parses_parenthesized_named_and_positional_args ... ok
test editor::xprompt_args::tests::preserves_commas_and_equals_inside_quotes_and_text_blocks ... ok
test editor::xprompt_args::tests::preserves_empty_elements_for_contract_validation ... ok
test editor::token::tests::extracts_expected_tokens ... ok
test editor::xprompt_args::tests::plus_decodes_only_on_bare_colon_arguments ... ok
test editor::xprompt_args::tests::research_swarm_inner_marker_stays_one_argument ... ok
test effort::tests::invalid_candidates_are_skipped ... ok
test effort::tests::leaves_unknown_or_internal_at_intact ... ok
test editor::xprompt_args::tests::text_block_compatibility_shapes_keep_parsing ... ok
test effort::tests::resolves_effective_effort_precedence_and_source ... ok
test editor::xprompt_args::tests::shared_corpus_matches_python_parse_args ... ok
test effort::tests::splits_trailing_known_effort ... ok
test editor::xprompt_args::tests::text_block_closes_at_terminator_not_first_marker ... ok
test editor::xprompt_args::tests::parses_colon_plus_hitl_and_namespaced_forms ... ok
test effort::tests::validates_canonical_vocabulary ... ok
test effort_override::tests::invalid_inputs_are_rejected ... ok
test effort_override::tests::clear_is_idempotent ... ok
test external_pr::classify::tests::blank_marker_is_ambiguous ... ok
test external_pr::classify::tests::maps_statuses_and_archive_destination ... ok
test external_pr::classify::tests::owned_url_skips_and_preserves_origin ... ok
test external_pr::classify::tests::refresh_fires_for_closed_unmerged_pr ... ok
test external_pr::classify::tests::refresh_fires_when_open_external_patch_status_drifts ... ok
test effort_override::tests::malformed_stale_and_missing_field_state_self_cleans ... ok
test external_pr::classify::tests::refresh_fires_for_merged_pr_and_moves_to_archive ... ok
test effort_override::tests::exact_and_no_expiry_records_obey_boundary_expiry ... ok
test external_pr::classify::tests::unmarked_pr_adopts_external_with_slug ... ok
test external_pr::classify::tests::unchanged_external_patch_skips ... ok
test external_pr::classify::tests::sase_owned_patch_never_refreshes_despite_status_drift ... ok
test external_pr::url::tests::canonicalizes_github_url_variants ... ok
test external_pr::classify::tests::unknown_origin_patch_never_refreshes_despite_status_drift ... ok
test external_pr::url::tests::rejects_unparseable_urls ... ok
test external_pr::url::tests::canonicalizes_gitlab_merge_request_urls ... ok
test feature_flag_state::tests::failed_atomic_write_cleans_temp_and_leaves_destination ... ok
test effort_override::tests::every_canonical_level_round_trips_and_replaces ... ok
test external_pr::classify::tests::marker_orphan_adopts_marker_name ... ok
test external_pr::classify::tests::marker_repairs_reserved_stub ... ok
test feature_flag_state::tests::failed_set_leaves_previous_state_and_no_temp_litter ... ok
test feature_flag_state::tests::both_booleans_round_trip_in_stable_order ... ok
test feature_flag_state::tests::invalid_utf8_and_size_limit_are_non_destructive ... ok
test bead::schema::tests::fresh_schema_accepts_claimed_status ... ok
test feature_flag_state::tests::reconcile_empty_registry_removes_every_valid_entry ... ok
test feature_flag_state::tests::missing_state_is_an_empty_snapshot ... ok
test feature_flag_state::tests::reconcile_rejects_invalid_registered_keys_before_touching_state ... ok
test feature_flag_state::tests::reconcile_missing_and_clean_state_are_idempotent ... ok
test feature_flag_state::tests::set_rejects_invalid_keys_without_creating_state ... ok
test feature_flag_state::tests::malformed_wrong_version_type_and_key_are_non_destructive ... ok
test feature_flag_state::tests::successful_write_leaves_no_temp_litter ... ok
test feature_flag_state::tests::reconcile_removes_unknown_valid_keys_only ... ok
test bead::mutation::tests::concurrent_update_and_claim_preserve_both_events_and_projection ... ok
test feature_flag_state::tests::unknown_valid_keys_are_preserved_across_writes ... ok
test feature_flag_state::tests::same_value_set_is_idempotent_and_skips_rewrite ... ok
test fenced_code::tests::boxed_displayed_inner_fence_is_one_block ... ok
test fenced_code::tests::crlf_opening_and_closing_fences_scan ... ok
test fenced_code::tests::digest_normalizes_crlf ... ok
test feature_flag_state::tests::reconcile_unusable_files_are_non_destructive ... ok
test fenced_code::tests::if_inside_ordinary_fence_is_not_owned ... ok
test fenced_code::tests::owned_if_fence_is_opaque_and_captures_code_value ... ok
test fenced_code::tests::tilde_and_indented_info_string_offsets_match_python ... ok
test fenced_code::tests::python_info_string_and_empty_source_and_unclosed ... ok
test fenced_code::tests::unknown_language_and_missing_fence_are_diagnostics ... ok
test fenced_code::tests::unlabelled_fence_is_bash ... ok
test finalizer::outcome::tests::refused_status_requires_reason ... ok
test fenced_code::tests::unclosed_fence_runs_to_eof ... ok
test finalizer::digest::tests::canonical_digest_sorts_nested_object_keys ... ok
test finalizer::outcome::tests::serde_rejects_unknown_statuses ... ok
test finalizer::outcome::tests::all_skipped_aggregates_success_and_all_failed_aggregates_failed ... ok
test finalizer::outcome::tests::attempt_numbers_must_be_unique_increasing_and_terminal ... ok
test finalizer::outcome::tests::deferral_payload_requires_deferred_status ... ok
test finalizer::outcome::tests::aggregate_failure_precedence_is_stable ... ok
test finalizer::outcome::tests::deferred_aggregate_is_a_warning_not_a_failure ... ok
test finalizer::outcome::tests::deferred_ranks_below_pending_and_refused_but_above_success ... ok
test finalizer::outcome::tests::deferred_status_requires_deferral_payload ... ok
test finalizer::selection::tests::cycles_and_missing_dependencies_are_diagnostics ... ok
test feature_flag_state::tests::competing_reconciliations_remove_a_stale_key_once ... ok
test finalizer::selection::tests::required_instances_are_selected_and_cannot_be_removed ... ok
test finalizer::selection::tests::authenticate_finalizer_plan_rejects_independent_expected_digest ... ok
test finalizer::selection::tests::validates_slug_and_size_limits ... ok
test finalizer::selection::tests::selector_replay_handles_add_remove_and_clear ... ok
test finalizer::selection::tests::stable_topological_order_preserves_selector_order_among_ready_nodes ... ok
test finalizer::selection::tests::validate_finalizer_plan_rejects_duplicate_or_shifted_indices ... ok
test finalizer::submission::tests::deferral_paths_must_be_nonempty_and_bounded ... ok
test feature_flag_state::tests::concurrent_reconcile_and_registered_set_do_not_lose_updates ... ok
test finalizer::wire::tests::fail_stays_the_serde_default_refusal_policy ... ok
test finalizer::wire::tests::unknown_deferral_reason_is_rejected ... ok
test finalizer::wire::tests::defer_refusal_policy_round_trips_through_serde ... ok
test finalizer::selection::tests::validate_finalizer_plan_rejects_forged_or_omitted_digest ... ok
test feature_flag_state::tests::concurrent_writers_preserve_distinct_keys ... ok
test finalizer::selection::tests::validate_finalizer_plan_accepts_resolved_plans ... ok
test finalizer::submission::tests::validates_complete_submission_and_digest_identity ... ok
test fleet_attention::tests::inventory_validation_rejects_unbounded_limits_and_bad_cursor ... ok
test fleet_attention::tests::non_actionable_notifications_are_skipped ... ok
test fleet_attention::tests::inventory_returns_pending_uncorrelated_requests_without_catalog_rows ... ok
test finalizer::selection::tests::validate_finalizer_plan_rejects_mutated_entries_without_new_digest ... ok
test fleet_attention::tests::notice_dedupe_suppresses_reconnect_and_announces_new_revision ... ok
test fleet_attention::tests::fingerprint_is_stable_and_sensitive_to_changes ... ok
test finalizer::submission::tests::rejects_missing_duplicate_and_unexpected_payloads ... ok
test fleet_attention::tests::notice_ledger_prunes_stale_entries_outside_retention_window ... ok
test fleet_attention::tests::inventory_revision_is_stable_across_reconnect ... ok
test fleet_attention::tests::path_like_option_id_is_rejected ... ok
test fleet_attention::tests::precondition_allows_matching_pending_entry ... ok
test fleet_attention::tests::precondition_already_settled_reports_settling_host ... ok
test fleet_attention::tests::precondition_capability_missing ... ok
test fleet_attention::tests::precondition_invalid_option ... ok
test fleet_attention::tests::inventory_pages_pending_entries_and_filters_settled_entries ... ok
test fleet_attention::tests::precondition_unknown_request_when_missing ... ok
test fleet_attention::tests::precondition_stale_revision ... ok
test fleet_attention::tests::projection_correlates_gate_by_origin_agent ... ok
test fleet_attention::tests::projection_correlates_question_by_sender ... ok
test fleet_attention::tests::replay_accepts_unseen_key ... ok
test finalizer::submission::tests::rejects_stale_identity_fields ... ok
test fleet_attention::tests::replay_conflicts_on_changed_payload ... ok
test fleet_attention::tests::projection_is_deterministic_and_sorted ... ok
test fleet_attention::tests::replay_rejects_expired_or_tombstoned_key ... ok
test fleet_attention::tests::replay_returns_original_receipt_for_same_payload ... ok
test fleet_contract::tests::batch_lookup_preserves_requested_order_and_bounds_ids ... ok
test fleet_attention::tests::secretish_title_is_rejected ... ok
test fleet_contract::tests::connection_plan_validation_rejects_insecure_or_secret_bearing_data ... ok
test fleet_contract::tests::cursor_replay_classifies_resync_boundaries ... ok
test fleet_contract::tests::content_and_project_read_requests_are_bounded ... ok
test fleet_attention::tests::uncorrelated_request_is_still_returned ... ok
test fleet_contract::tests::catalog_query_is_bounded_and_pages_deterministically ... ok
test fleet_contract::tests::count_rejects_equal_revision_competing_current_instances ... ok
test fleet_contract::tests::follow_tombstones_suppress_dispatch_recreation_and_activation ... ok
test fleet_contract::tests::follow_reconciliation_promotes_singleton_to_family_identity ... ok
test agent_stats::run::tests::missing_archive_spec_is_not_malformed ... ok
test fleet_contract::tests::count_contract_is_order_independent_and_deduplicates_current_instances ... ok
test fleet_contract::tests::invalidations_validate_cursor_and_revision_identity ... ok
test fleet_contract::tests::locator_keys_are_stable_and_names_do_not_become_identity ... ok
test fleet_contract::tests::federation_invalid_host_cursor_requests_host_resync_but_keeps_rows ... ok
test fleet_contract::tests::focus_and_fleet_counts_stay_separate_and_propagate_unknown_hosts ... ok
test fleet_contract::tests::identity_store_uses_private_modes ... ok
test fleet_contract::tests::federation_catalog_normalization_preserves_authoritative_counts_freshness_and_cursors ... ok
test fleet_contract::tests::federation_malformed_host_degrades_without_losing_healthy_hosts ... ok
test fleet_contract::tests::installation_identity_creation_read_rotation_and_migration_are_fenced ... ok
test fleet_contract::tests::fleet_launch_intent_and_replay_are_portable_and_target_pinned ... ok
test fleet_follow_promotion::tests::empty_observations_or_records_yield_no_promotions ... ok
test fleet_contract::tests::time_helpers_keep_owner_runtime_and_viewer_freshness_separate ... ok
test fleet_contract::tests::operation_fingerprint_and_replay_decisions_are_scoped ... ok
test fleet_contract::tests::federation_followed_batch_counts_only_resolved_requested_entries ... ok
test fleet_contract::tests::projection_rejects_inconsistent_owner_facts_and_handles ... ok
test fleet_follow_promotion::tests::duplicate_same_family_observations_are_not_ambiguous ... ok
test fleet_follow_promotion::tests::non_tui_consumer_promotions_are_accepted_by_follow_reconciliation ... ok
test fleet_contract::tests::malformed_oversized_and_future_identity_files_are_left_unchanged ... ok
test fleet_follow_promotion::tests::promotes_explicit_singleton_when_exactly_one_family_matches ... ok
test fleet_follow_promotion::tests::rejects_malformed_records_and_observations ... ok
test fleet_follow_promotion::tests::rejects_unsupported_schema_version ... ok
test fleet_follow_promotion::tests::requires_same_origin_project_and_agent ... ok
test fleet_contract::tests::projection_outputs_safe_summary_and_detail_without_local_fields ... ok
test fleet_follow_promotion::tests::skips_family_records_and_dispatch_records ... ok
test fleet_follow_promotion::tests::skips_pending_explicit_singletons ... ok
test fleet_follow_promotion::tests::skips_when_observations_match_multiple_families ... ok
test fleet_follow_promotion::tests::skips_redundant_source_and_ignores_singleton_observations ... ok
test fleet_mutation::tests::fork_without_prompt_is_rejected ... ok
test fleet_follow_promotion::tests::unfollow_tombstones_win_when_derived_promotions_are_reconciled ... ok
test fleet_mutation::tests::bulk_partition_groups_by_origin_deterministically ... ok
test fleet_mutation::tests::precondition_allows_matching_live_row ... ok
test fleet_mutation::tests::precondition_already_terminal_for_stop ... ok
test fleet_mutation::tests::path_like_reason_is_rejected ... ok
test fleet_mutation::tests::precondition_capability_missing ... ok
test fleet_mutation::tests::precondition_stale_revision ... ok
test fleet_mutation::tests::precondition_instance_mismatch_for_superseded_run ... ok
test fleet_mutation::tests::mutation_fingerprint_changes_when_intent_changes ... ok
test fleet_mutation::tests::mutation_fingerprint_is_stable_for_identical_intents ... ok
test fleet_mutation::tests::precondition_unknown_row_when_missing_or_logical_mismatch ... ok
test git_query::parsers::tests::branch_name_detached_head_returns_none ... ok
test fleet_mutation::tests::stop_and_retry_reject_fork_prompt ... ok
test git_query::parsers::tests::branch_name_empty_stdout_returns_none ... ok
test git_query::parsers::tests::branch_name_simple_value ... ok
test fleet_mutation::tests::replay_conflicts_on_changed_payload ... ok
test git_query::parsers::tests::branch_name_whitespace_only_returns_none ... ok
test fleet_mutation::tests::replay_returns_original_receipt_for_same_payload ... ok
test git_query::parsers::tests::branch_name_strips_surrounding_whitespace ... ok
test fleet_mutation::tests::replay_rejects_expired_or_tombstoned_key ... ok
test fleet_mutation::tests::request_fingerprint_mismatch_is_rejected ... ok
test git_query::parsers::tests::conflicted_files_empty_stdout_returns_empty ... ok
test git_query::parsers::tests::conflicted_files_only_blank_lines_returns_empty ... ok
test git_query::parsers::tests::conflicted_files_preserves_path_order ... ok
test git_query::parsers::tests::conflicted_files_strips_blank_lines ... ok
test git_query::parsers::tests::local_changes_clean_tree_returns_none ... ok
test git_query::parsers::tests::local_changes_dirty_tree_returns_stripped_text ... ok
test git_query::parsers::tests::local_changes_whitespace_only_returns_none ... ok
test git_query::parsers::tests::name_status_copy_with_score_carries_paired_paths ... ok
test git_query::parsers::tests::name_status_empty_stream_returns_empty ... ok
test git_query::parsers::tests::name_status_mixed_simple_and_rename_in_one_stream ... ok
test git_query::parsers::tests::name_status_rename_with_score_carries_paired_paths ... ok
test git_query::parsers::tests::name_status_simple_status_letters ... ok
test git_query::parsers::tests::name_status_skips_empty_status_tokens ... ok
test fleet_mutation::tests::replay_accepts_unseen_key ... ok
test git_query::parsers::tests::name_status_trailing_nul_is_ignored ... ok
test git_query::parsers::tests::name_status_truncated_rename_falls_back_to_single_path ... ok
test fleet_contract::tests::concurrent_identity_creators_converge_on_one_record ... ok
test git_query::parsers::tests::name_status_truncated_status_only_drops_entry ... ok
test git_query::parsers::tests::workspace_name_falls_back_to_root_when_remote_blank ... ok
test git_query::parsers::tests::workspace_name_falls_back_to_root_when_remote_none ... ok
test git_query::parsers::tests::workspace_name_https_remote_with_dot_git ... ok
test git_query::parsers::tests::workspace_name_https_remote_without_dot_git ... ok
test git_query::parsers::tests::workspace_name_path_like_remote ... ok
test git_query::parsers::tests::workspace_name_remote_dot_git_only_returns_none ... ok
test git_query::parsers::tests::workspace_name_remote_takes_priority_over_root ... ok
test git_query::parsers::tests::workspace_name_returns_none_when_both_inputs_empty ... ok
test git_query::parsers::tests::workspace_name_ssh_remote_with_dot_git ... ok
test glossary::tests::builds_effective_aliases_with_derived_plurals ... ok
test glossary::tests::entry_path_falls_back_when_source_key_path_is_empty ... ok
test glossary::tests::builds_effective_aliases_with_term_first ... ok
test glossary::tests::glossary_source_wire_accepts_v1_payload_names ... ok
test glossary::tests::glossary_source_wire_emits_v2_payload_names ... ok
test glossary::tests::filters_display_aliases_to_non_derivable_configured_aliases ... ok
test glossary::tests::pluralizes_phrases_with_conservative_ascii_rules ... ok
test glossary::tests::skips_derived_plural_claimed_by_authored_alias_without_diagnostic ... ok
test bead::schema::tests::fresh_schema_enforces_task_and_ready_constraints ... ok
test editor::completion::tests::commit_inventory_skips_unusable_checkouts_and_bug_stays_empty ... ok
test glossary::tests::validation_diagnostics_stay_authored_for_alias_edge_cases ... ok
test glossary::tests::three_word_term_wraps_across_three_lines ... ok
test host_bridge::tests::command_helper_bridge_invokes_editor_finalizer_catalog ... ok
test host_bridge::tests::command_helper_bridge_invokes_editor_snippet_catalog ... ok
test bead::schema::tests::issue_type_migration_preserves_and_accepts_claimed_status ... ok
test glossary::tests::scans_wrapped_phrase_with_trimmed_segments ... ok
test host_bridge::tests::finalizer_catalog_wire_accepts_legacy_and_extended_entry_json ... ok
test host_bridge::tests::static_helper_bridge_returns_finalizer_catalog_response ... ok
test host_bridge::tests::static_helper_bridge_returns_vcs_repo_catalog_response ... ok
test machine_hood::tests::machine_hood_of_classifies_known_machines ... ok
test machine_hood::tests::machine_hood_of_returns_none_for_unknown_or_partial ... ok
test host_bridge::tests::xprompt_catalog_entry_wire_accepts_old_and_new_definition_path_json ... ok
test host_bridge::tests::snippet_catalog_wire_accepts_minimal_entry_json ... ok
test machine_hood::tests::qualify_and_strip_round_trip ... ok
test machine_hood::tests::qualify_does_not_confuse_prefix_of_another_machine ... ok
test machine_hood::tests::qualify_is_idempotent ... ok
test machine_hood::tests::qualify_preserves_family_names ... ok
test machine_hood::tests::strip_is_idempotent ... ok
test machine_hood::tests::strip_leaves_unqualified_and_foreign_names ... ok
test machine_hood::tests::strip_never_produces_empty_remainder ... ok
test glossary::tests::single_line_match_has_one_span_equal_segment ... ok
test machine_hood::tests::strip_removes_leading_hood ... ok
test machine_hood::tests::validate_accepts_lowercase_and_underscores ... ok
test machine_hood::tests::validate_rejects_empty_uppercase_digits_and_dots ... ok
test glossary::tests::lookup_uses_utf16_editor_positions ... ok
test glossary::tests::wrapped_phrase_does_not_cross_block_boundaries ... ok
test glossary::tests::lookup_on_continuation_word_returns_wrapped_span ... ok
test machine_setup::tests::discovery_reports_non_mapping_peers_and_peer_payload ... ok
test machine_setup::tests::discovery_excludes_self_by_identity_overlap_and_self_flag ... ok
test machine_setup::tests::discovery_applies_https_endpoint_overrides ... ok
test machine_setup::tests::discovery_rejects_invalid_endpoint_override ... ok
test machine_setup::tests::discovery_parses_status_excludes_self_and_normalizes_dns ... ok
test machine_hood::tests::qualify_prepends_when_missing ... ok
test machine_setup::tests::health_classifies_compatible_fleet_advertisement ... ok
test host_bridge::tests::command_helper_bridge_invokes_editor_vcs_repo_catalog ... ok
test glossary::tests::scan_skips_fenced_and_inline_code_literals ... ok
test machine_setup::tests::health_distinguishes_unrelated_healthy_service_from_legacy_sase ... ok
test machine_setup::tests::health_classifies_legacy_sase_without_fleet_as_unknown ... ok
test machine_setup::tests::health_classifies_non_sase_payload_as_unrelated ... ok
test machine_setup::tests::health_rejects_unsupported_schema_version ... ok
test machine_setup::tests::health_rejects_malformed_protocol_version_types ... ok
test glossary::tests::literal_zone_filter_skips_candidates_but_keeps_prose_match ... ok
test machine_setup::tests::discovery_handles_missing_and_extra_peer_fields ... ok
test machine_setup::tests::reconcile_rejects_unsupported_schema_version ... ok
test managed_origin::tests::canonical_remote_unavailable_fails ... ok
test host_bridge::tests::static_helper_bridge_returns_snippet_catalog_response ... ok
test managed_origin::tests::missing_identity_fails ... ok
test managed_origin::tests::primary_origin_resolving_to_primary_fails ... ok
test host_bridge::tests::static_helper_bridge_returns_structured_catalog_response ... ok
test glossary::tests::wrapped_phrase_accepts_crlf_without_segment_carriage_returns ... ok
test bead::schema::tests::fresh_schema_enforces_task_type_check_and_accepts_task_rows ... ok
test bead::schema::tests::fresh_schema_accepts_bookend_phase_sizes ... ok
test bead::schema::tests::refs_migration_preserves_existing_rows_and_defaults_empty ... ok
test machine_setup::tests::reconcile_does_not_let_untrusted_hint_overwrite_enrolled_pin ... ok
test machine_setup::tests::health_incompatible_when_protocol_constant_is_absent ... ok
test glossary::tests::wrapped_longer_match_wins_over_shorter_at_same_start ... ok
test migration::journal::tests::replay_refuses_backward_journal_transition ... ok
test machine_setup::tests::reconcile_skips_matching_identities_and_routes_pin_change_to_repair ... ok
test managed_origin::tests::stale_origin_is_rewritten_to_canonical_remote ... ok
test managed_origin::tests::stale_explicit_push_url_is_rewritten ... ok
test managed_origin::tests::unrelated_local_bare_remote_is_preserved ... ok
test markdown_link_refs::tests::allocate_fills_gaps_between_existing_definitions ... ok
test markdown_link_refs::tests::allocate_reserves_a_dangling_numeric_use_with_no_definition ... ok
test markdown_link_refs::tests::allocate_reuses_matching_destination_before_picking_a_new_number ... ok
test markdown_link_refs::tests::append_definitions_in_numeric_order_and_skips_matching_ones ... ok
test markdown_link_refs::tests::append_is_idempotent_and_preserves_trailing_newline_shape ... ok
test markdown_link_refs::tests::scan_skips_duplicate_bracket_pairs_used_as_link_text ... ok
test markdown_link_refs::tests::scan_collects_definitions_first_wins_and_uses_all_three_forms ... ok
test markdown_link_refs::tests::scan_ignores_footnotes_inline_links_definitions_and_literal_zones ... ok
test migration::digest::tests::tree_digest_changes_when_file_content_changes ... ok
test glossary::tests::scans_derived_plural_for_term_without_configured_aliases ... ok
test migration::journal::tests::replay_advances_to_resume_point ... ok
test migration::digest::tests::fingerprint_is_stable_for_object_key_order ... ok
test migration::journal::tests::replay_refuses_digest_movement ... ok
test migration::procs::tests::reconcile_matches_task_id_to_canonical_proc_id ... ok
test migration::residue::tests::classifier_refuses_live_references ... ok
test migration::manifest::tests::expected_source_digests_include_operation_entries ... ok
test model_completion::tests::old_catalog_rows_deserialize_with_additive_defaults ... ok
test model_completion::tests::filters_values_aliases_and_provider_scopes_in_catalog_order ... ok
test migration::manifest::tests::manifest_preserves_unknown_extension_fields ... ok
test model_completion::tests::scoped_candidates_preserve_filter_text ... ok
test migration::tests::bounded_lock_wraps_store_lock ... ok
test model_route::tests::maps_every_phase_size_to_the_public_alias ... ok
test migration::procs::tests::reconcile_reports_missing_and_conflicting_rows ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_hides_abandoned_record ... ok
test migration::residue::tests::classifier_archives_only_inert_residue_with_counterpart ... ok
test model_route::tests::rejects_invalid_and_retired_size_names ... ok
test model_route::tests::rejects_invalid_counts_thresholds_and_targets ... ok
test model_route::tests::selects_explicit_epic_land_model_over_threshold ... ok
test model_route::tests::empty_or_blank_explicit_model_falls_through_to_config ... ok
test model_route::tests::uses_big_target_at_and_above_threshold ... ok
test model_route::tests::wire_json_uses_config_field_source_names ... ok
test model_route::tests::zero_phase_count_is_valid_and_selects_the_normal_target ... ok
test notifications::mobile::tests::gate_action_request_option_inputs_round_trips ... ok
test notifications::mobile::tests::gate_action_string_mapping_is_complete ... ok
test notifications::mobile::tests::prefix_resolution_makes_collisions_explicit ... ok
test notifications::mobile::tests::planner_errors_are_deterministic ... ok
test notifications::mobile::tests::priority_and_error_classifiers_are_disjoint ... ok
test notifications::mobile::tests::gate_envelope_version_acceptance_is_bounded ... ok
test notifications::mobile::tests::question_planner_supports_index_label_id_and_custom_answers ... ok
test notifications::mobile::tests::custom_gate_notification_contract_snapshot_is_stable ... ok
test notifications::mobile::tests::epic_notification_contract_snapshot_is_stable ... ok
test notifications::mobile::tests::launch_approval_detail_exposes_preview_identity ... ok
test notifications::mobile::tests::every_non_question_gate_projects_the_same_branch_wire ... ok
test notifications::mobile::tests::action_result_contract_snapshot_is_stable ... ok
test notifications::pending_actions::tests::custom_gate_without_bundle_path_has_missing_target_state ... ok
test notifications::mobile::tests::mobile_notification_contract_snapshot_is_stable ... ok
test notifications::tabs::tests::a_non_panel_row_does_not_donate_a_panel_icon ... ok
test notifications::tabs::tests::a_panel_and_tag_collision_sorts_as_a_panel_either_way ... ok
test notifications::pending_actions::tests::epic_approval_without_response_dir_has_missing_target_state ... ok
test notifications::tabs::tests::a_resurfaced_row_donates_its_color_over_a_newer_sent_row ... ok
test notifications::tabs::tests::a_resurfaced_row_donates_its_icon_over_a_newer_sent_row ... ok
test notifications::pending_actions::tests::cleanup_stale_pending_actions_removes_only_expired_entries ... ok
test notifications::tabs::tests::a_snoozed_row_leaves_its_panel_tab ... ok
test notifications::mobile::tests::schema_version_3_envelope_with_declared_inputs_yields_branches ... ok
test notifications::tabs::tests::a_row_donates_its_icon_only_to_its_declared_panel_tab ... ok
test notifications::pending_actions::tests::custom_gate_uses_only_neutral_terminal_files ... ok
test notifications::tabs::tests::a_tab_wears_the_newest_declared_color_and_ignores_junk ... ok
test notifications::pending_actions::tests::launch_approval_is_a_pending_action_kind ... ok
test notifications::pending_actions::tests::epic_approval_is_typed_and_resolves_through_pending_store ... ok
test notifications::pending_actions::tests::pending_store_merges_legacy_telegram_shape ... ok
test notifications::pending_actions::tests::pending_state_detects_stale_and_external_plan_response ... ok
test parser::tests::empty_input_yields_no_specs ... ok
test parser::tests::empty_value_lines_become_none_or_empty_per_python_rules ... ok
test notifications::tabs::tests::an_absent_color_stays_absent_on_the_wire ... ok
test notifications::tabs::tests::a_tab_wears_the_newest_declared_icon_and_ignores_junk ... ok
test notifications::tabs::tests::a_two_tag_row_lands_in_exactly_one_tab ... ok
test notifications::tabs::tests::counts_and_tabs_agree_and_skip_read_or_silent_rows ... ok
test notifications::tabs::tests::an_absent_icon_stays_absent_on_the_wire ... ok
test notifications::tabs::tests::declared_panel_outranks_hitl_errors_and_tags ... ok
test notifications::tabs::tests::hitl_then_errors_then_first_tag_then_general ... ok
test notifications::tabs::tests::labels_title_case_tag_words ... ok
test notifications::tabs::tests::reserved_and_malformed_panels_fall_through ... ok
test notifications::tabs::tests::oldest_activity_and_next_wake_are_minimums ... ok
test notifications::tabs::tests::snoozed_precedes_muted_for_a_muted_row_with_a_wake_time ... ok
test notifications::pending_actions::tests::pending_store_registers_and_resolves_prefixes ... ok
test notifications::tabs::tests::tab_order_matches_the_panel ... ok
test parser::tests::description_preserves_internal_blank_lines_then_trims ... ok
test parser::tests::legacy_changespec_header_detection_requires_whitespace_then_word ... ok
test parser::tests::legacy_changespec_header_separates_specs_without_blank_lines ... ok
test parser::tests::missing_or_invalid_project_name_metadata_stays_absent ... ok
test parser::tests::indented_blank_run_in_description_does_not_end_spec ... ok
test parser::tests::drops_incomplete_specs_missing_name_or_status ... ok
test parser::tests::missing_refs_section_defaults_to_empty ... ok
test parser::tests::multi_line_description_strips_two_space_continuation ... ok
test parser::tests::invalid_utf8_returns_parse_error_wire ... ok
test parser::tests::new_name_inside_a_spec_starts_a_new_spec ... ok
test parser::tests::parent_cl_pr_bug_scalars_round_trip ... ok
test parser::tests::parses_headered_spec_with_inline_description ... ok
test parser::tests::patch_header_detection_accepts_canonical_and_legacy_headers ... ok
test parser::tests::pr_origin_scalars_round_trip_and_absence_defaults_unknown ... ok
test parser::tests::project_basename_strips_extension_and_archive_suffix ... ok
test parser::tests::two_blank_lines_separate_specs ... ok
test parser::tests::parses_direct_name_spec_without_header ... ok
test pending_commit_checkpoint::tests::foreign_pending_checkpoint_fails ... ok
test parser::tests::project_name_metadata_is_stamped_on_every_patch ... ok
test pending_commit_checkpoint::tests::legacy_with_independent_proof_resumes ... ok
test parser::tests::rust_end_line_is_real_not_placeholder ... ok
test pending_commit_checkpoint::tests::legacy_without_proof_fails ... ok
test pending_commit_checkpoint::tests::missing_checkpoint_is_none ... ok
test parser::tests::span_excludes_trailing_blank_separator ... ok
test glossary::tests::scans_case_insensitively_with_longest_non_overlapping_matches ... ok
test pending_commit_checkpoint::tests::foreign_agent_fails ... ok
test parser::tests::refs_parse_in_canonical_position_and_preserve_raw_invalid_text ... ok
test parser::tests::refs_parse_at_end_of_spec ... ok
test pending_commit_checkpoint::tests::foreign_run_fails ... ok
test pending_commit_checkpoint::tests::same_subject_different_body_fails ... ok
test pending_commit_checkpoint::tests::missing_current_identity_fails ... ok
test pending_commit_checkpoint::tests::pending_after_hook_resumes ... ok
test pending_commit_checkpoint::tests::subject_mismatch_fails ... ok
test pending_commit_checkpoint::tests::unpushed_without_sha_fails ... ok
test pending_commit_checkpoint::tests::pending_dispatch_without_sha_still_resumes ... ok
test pending_commit_checkpoint::tests::complete_checkpoint_is_none ... ok
test perf_logs::aggregate::tests::absent_and_empty_sources_are_covered_without_failure ... ok
test perf_logs::aggregate::tests::record_cap_marks_source_truncated ... ok
test plan::artifact_link::tests::bead_section_supports_linked_unlinked_and_prettier_wrapped_labels ... ok
test plan::artifact_link::tests::discontiguous_header_groups_before_body_content_are_invalid ... ok
test perf_logs::aggregate::tests::percentile_edges_use_nearest_rank_rounding ... ok
test plan::artifact_link::tests::empty_list_section_is_omitted ... ok
test plan::artifact_link::tests::artifacts_is_list_shaped_and_orders_between_agents_and_commits ... ok
test perf_logs::aggregate::tests::malformed_timestamp_and_partial_trailing_lines_are_reported ... ok
test plan::artifact_link::tests::bead_upsert_keeps_bead_frontmatter ... ok
test plan::artifact_link::tests::extra_leading_blank_line_is_recognized_as_noncanonical_layout ... ok
test perf_logs::aggregate::tests::byte_cap_truncates_tail_without_counting_leading_fragment ... ok
test plan::artifact_link::tests::escapes_labels_and_trailing_text ... ok
test plan::artifact_link::tests::fenced_header_example_is_not_a_live_document_header ... ok
test plan::artifact_link::tests::back_compat_single_legacy_and_mixed_cases ... ok
test perf_logs::aggregate::tests::aggregates_mixed_timestamp_formats_and_window ... ok
test plan::artifact_link::tests::artifacts_is_compatible_with_either_counterpart_section ... ok
test plan::artifact_link::tests::known_header_labels_after_body_content_are_ordinary_bullets ... ok
test plan::artifact_link::tests::ordinary_bold_and_nested_body_bullets_are_not_header_sections ... ok
test plan::artifact_link::tests::multi_section_round_trip_uses_fixed_order ... ok
test plan::artifact_link::tests::rejects_malformed_duplicate_unknown_and_unterminated_documents ... ok
test plan::artifact_link::tests::parses_prettier_wrapped_commit_and_preserves_unchanged_bytes ... ok
test plan::artifact_link::tests::plan_and_prompt_sections_accept_absolute_cross_repo_targets ... ok
test plan::artifact_link::tests::legacy_upsert_preserves_frontmatter_body_and_other_sections ... ok
test plan::artifact_link::tests::parent_upsert_removes_only_legacy_top_level_parent ... ok
test plan::artifact_link::tests::list_cap_is_visible_and_round_trips_logically ... ok
test plan::artifact_link::tests::remove_section_keeps_the_rest_and_canonical_layout ... ok
test plan::artifact_link::tests::title_before_header_means_the_bullet_is_body_content ... ok
test plan::read::tests::empty_kind_filter_selects_no_repo_plans ... ok
test plan::read::tests::derives_title_from_h1_then_humanized_name ... ok
test plan::read::tests::discovers_every_repo_kind_with_labels_and_relpaths ... ok
test plan::read::tests::explicit_empty_corpora_disable_the_legacy_repo_scan ... ok
test plan::read::tests::accepts_rfc3339_and_date_only_create_time ... ok
test plan::read::tests::falls_back_to_mtime_when_create_time_absent ... ok
test plan::read::tests::canonical_plans_are_tier_classified_with_tale_fallback ... ok
test plan::read::tests::explicit_document_corpora_replace_legacy_scan_and_keep_own_relpaths ... ok
test plan::read::tests::explicit_document_corpora_include_one_bundle_level_shallow_first ... ok
test plan::read::tests::explicit_plans_corpus_honors_tier_and_other_labels_ignore_it ... ok
test plan::read::tests::filters_repo_corpus_by_kind ... ok
test plan::read::tests::explicit_document_corpora_skip_prompt_specs_dotdirs_and_deeper_files ... ok
test plan::read::tests::missing_roots_yield_no_plans_without_error ... ok
test plan::read::tests::discovers_local_flat_and_sharded_layout ... ok
test plan::read::tests::sorts_files_within_a_shard ... ok
test plan::read::tests::kind_filter_does_not_constrain_local_plans ... ok
test plan::read::tests::mixed_transition_projects_label_only_when_paths_agree ... ok
test plan::read::tests::prompt_directory_projects_plan_bullet_label ... ok
test plan::read::tests::projects_canonical_prompt_link_label_without_polluting_plan_content ... ok
test plan::read::tests::repo_plans_precede_local_plans ... ok
test plan::read::tests::ignores_non_markdown_files ... ok
test plan::read::tests::parses_frontmatter_fields_and_normalizes_created_at ... ok
test plan::refs::tests::alias_prefix_reparses_as_canonical ... ok
test plan::refs::tests::canonicalize_uses_first_matching_root ... ok
test plan::refs::tests::every_legacy_form_resolves_to_the_same_file ... ok
test plan::refs::tests::exact_resolution_uses_first_root ... ok
test plan::refs::tests::validation_messages_remain_stable_after_helper_extraction ... ok
test plan::search::tests::applies_limit_after_ranking ... ok
test plan::refs::tests::missing_keeps_ordered_best_candidates ... ok
test agent_scan::index::tests::terminalize_repairs_visible_abandoned_rows ... ok
test plan::search::tests::counterpart_label_remains_searchable_as_frontmatter_metadata ... ok
test plan::refs::tests::typed_reference_round_trips ... ok
test plan::search::tests::blank_query_is_treated_as_browse ... ok
test plan::refs::tests::multiple_month_drift_matches_are_ambiguous ... ok
test plan::search::tests::date_range_filters_inclusively_on_day_bounds ... ok
test plan::search::tests::excludes_plans_without_dates_when_date_filter_active ... ok
test plan::read::tests::tolerates_malformed_and_absent_frontmatter ... ok
test plan::refs::tests::unregistered_schemes_and_paths_remain_legacy ... ok
test plan::refs::tests::unique_month_drift_resolves ... ok
test plan::refs::tests::typed_reference_rejects_unsafe_payloads_and_unknown_kinds ... ok
test feature_flag_state::tests::lock_timeout_names_the_holder ... ok
test plan::read::tests::tier_frontmatter_classifies_canonical_plans_and_filters_post_parse ... ok
test plan::search::tests::browse_mode_returns_all_plans_sorted_by_recency ... ok
test plan::search::tests::field_names_constant_matches_searchable_fields ... ok
test plan::search::tests::explicit_sort_modes_override_defaults ... ok
test plan::search::tests::filters_status_source_and_date_together ... ok
test plan::search::tests::no_match_returns_empty_results ... ok
test plan::search::tests::matches_case_insensitive_unicode_substrings ... ok
test plan::search::tests::matches_every_searchable_field ... ok
test plan::search::tests::parses_relative_and_partial_date_bounds ... ok
test plan::search::tests::ranks_title_above_frontmatter_above_body ... ok
test plan::search::tests::recency_breaks_relevance_ties ... ok
test plan::search::tests::relative_months_clamp_to_month_length ... ok
test feature_flag_state::tests::reconcile_lock_timeout_and_write_failure_report_failed_outcomes ... ok
test plan::search::tests::public_search_filters_across_explicit_corpus_labels ... ok
test plan::search::tests::rejects_unknown_sort_mode ... ok
test plan::search::tests::rejects_invalid_date_bound ... ok
test plan::search::tests::source_filter_scopes_results ... ok
test plan::search::tests::status_filter_is_case_insensitive ... ok
test plan::search::tests::status_value_is_reported_as_status_not_frontmatter ... ok
test agent_scan::index::tests::windowed_query_preserves_active_rows_and_selects_completed_budget ... ok
test plan::search::tests::public_search_kind_filter_narrows_repo_only ... ok
test plan::search::tests::zero_limit_is_unlimited ... ok
test plan::search::tests::repo_outranks_local_on_equal_relevance ... ok
test plan::search::tests::public_search_reads_ranks_and_prioritizes_repo ... ok
test plan::validate::tests::a_malformed_header_block_does_not_hide_frontmatter_diagnostics ... ok
test plan::validate::tests::common_field_rules_report_together_with_locations ... ok
test plan::validate::tests::a_well_formed_or_absent_header_block_raises_nothing ... ok
test plan::validate::tests::epic_missing_collection_and_phase_scalar_rules_report ... ok
test plan::validate::tests::epic_top_level_rules_all_report ... ok
test plan::validate::tests::legacy_changespec_frontmatter_key_validates_as_patch ... ok
test plan::validate::tests::links_frontmatter_is_accepted_as_a_transient_authoring_inlet ... ok
test plan::validate::tests::missing_phase_description_warns_without_changing_the_plan ... ok
test plan::validate::tests::missing_wrong_type_and_invalid_tier_are_distinct ... ok
test plan::validate::tests::both_tiers_require_a_non_empty_string_title ... ok
test plan::validate::tests::other_header_block_defects_are_located_errors ... ok
test plan::validate::tests::phase_shape_keys_and_required_fields_report ... ok
test plan::validate::tests::schema_is_ordered_and_contains_exact_phase_guidance ... ok
test plan::validate::tests::managed_plan_proposer_is_optional_normalized_and_type_checked ... ok
test plan::validate::tests::phase_ids_and_dependency_graph_rules_report_in_one_pass ... ok
test plan::validate::tests::tale_epic_fields_are_inert_warnings ... ok
test plan::validate::tests::phase_optional_fields_validate_types_and_model_syntax ... ok
test plan::validate::tests::parent_bead_is_optional_epic_only_and_type_checked ... ok
test plan::validate::tests::trailing_text_in_a_link_section_is_a_located_error ... ok
test plan::validate::tests::managed_plan_links_are_optional_on_both_tiers_and_type_checked ... ok
test plan::validate::tests::structural_diagnostics_cover_each_rule ... ok
test plan::validate::tests::unsupported_caller_tier_is_a_usage_error ... ok
test plan::validate::tests::valid_epic_returns_all_normalized_fields ... ok
test plan::validate::tests::valid_tale_returns_normalized_plan_and_accepts_system_fields ... ok
test plan::validate::tests::tale_size_is_required_strict_and_normalized ... ok
test procs::store::tests::reserve_replays_identical_shell_request_and_rejects_conflicts ... ok
test plan::validate::tests::phase_size_is_strict_for_authoring_and_legacy_safe_for_launch ... ok
test procs::store::tests::detached_kind_round_trips_and_unknown_kinds_are_rejected ... ok
test procs::store::tests::legacy_commandless_tui_rows_remain_readable ... ok
test procs::store::tests::legacy_task_id_rows_are_accepted_and_rewritten_with_proc_id ... ok
test procs::store::tests::append_and_read_round_trip_is_newest_first_and_normalizes_tags ... ok
test project_spec::tests::lifecycle_read_accepts_canonical_disabled_state ... ok
test project_spec::tests::lifecycle_read_accepts_canonical_sibling_state ... ok
test project_spec::tests::lifecycle_read_normalizes_legacy_enabled_and_disabled_states ... ok
test project_spec::tests::lifecycle_read_warns_and_defaults_invalid_state ... ok
test project_spec::tests::lifecycle_read_warns_on_duplicate_state ... ok
test project_spec::tests::lifecycle_update_accepts_sibling_target_state ... ok
test project_spec::tests::lifecycle_update_inserts_before_first_name ... ok
test project_spec::tests::lifecycle_update_inserts_before_running_and_preserves_crlf ... ok
test project_spec::tests::lifecycle_project_records_include_aliases_and_collision_warnings ... ok
test project_spec::tests::lifecycle_project_records_classify_true_projects_and_vcs_kind ... ok
test editor::completion::tests::commit_inventory_merges_repositories_by_recency_and_assigns_rank ... ok
test procs::store::tests::unknown_fields_are_tolerated_and_malformed_rows_are_dropped_on_rewrite ... ok
test procs::store::tests::terminal_transition_guards_and_repeat_writes_preserve_final_fields ... ok
test procs::store::tests::running_rows_survive_retention ... ok
test procs::store::tests::proc_shell_lifecycle_requires_settlement_and_single_supervisor_finish ... ok
test procs::store::tests::updating_an_existing_row_to_the_detached_kind_validates ... ok
test procs::store::tests::xprompt_proc_meta_preserves_label_provenance ... ok
test procs::store::tests::retention_keeps_newest_terminal_rows_at_and_beyond_limit ... ok
test project_spec::tests::archive_detection_accepts_canonical_and_legacy_extensions ... ok
test project_spec::tests::lifecycle_update_rejects_invalid_target_state ... ok
test project_spec::tests::lifecycle_read_defaults_missing_state_to_enabled ... ok
test project_spec::tests::lifecycle_update_replaces_existing_state_line ... ok
test project_spec::tests::lifecycle_update_normalizes_legacy_target_states ... ok
test project_spec::tests::project_aliases_read_defaults_missing_aliases_to_empty ... ok
test project_spec::tests::project_aliases_read_sorts_dedupes_and_warns ... ok
test project_spec::tests::project_aliases_update_inserts_before_first_name ... ok
test project_spec::tests::project_aliases_update_inserts_before_running_and_preserves_crlf ... ok
test project_spec::tests::project_aliases_update_rejects_invalid_or_duplicate_aliases ... ok
test project_spec::tests::project_aliases_update_removes_existing_aliases ... ok
test project_spec::tests::project_aliases_update_replaces_existing_aliases_sorted ... ok
test project_spec::tests::project_name_read_warns_on_invalid_and_duplicate_names ... ok
test project_spec::tests::project_name_read_accepts_missing_and_present_name ... ok
test project_spec::tests::project_name_update_inserts_replaces_and_removes_name ... ok
test project_spec::tests::project_name_update_preserves_crlf_and_rejects_invalid_name ... ok
test project_spec::tests::project_spec_basename_accepts_active_and_archive_extensions ... ok
test project_spec::tests::project_spec_filenames_are_canonical_sase ... ok
test project_spec::tests::project_spec_path_conversions_emit_canonical_extension ... ok
test project_spec::tests::lifecycle_project_records_filter_and_sort_projects ... ok
test prompt_artifact::tests::manifest_parse_tolerates_unknown_fields ... ok
test prompt_archive::tests::invalid_headers_are_per_file_parse_errors ... ok
test prompt_archive::tests::month_selector_limits_discovery_without_validating_name ... ok
test prompt_artifact::tests::pool_names_cover_paths_unicode_extensions_and_length ... ok
test prompt_archive::tests::inventories_sorted_prompt_markdown_files ... ok
test parser::tests::parse_patch_project_bytes_emits_canonical_patch_wire ... ok
test parser::tests::save_pending_entries_flushes_at_field_boundary ... ok
test prompt_artifact::tests::manifest_round_trip_skips_bad_and_future_lines ... ok
test parser::tests::legacy_commits_section_still_parses_as_stitches ... ok
test prompt_literals::tests::merges_overlapping_and_adjacent_masks_once ... ok
test prompt_artifact::tests::rewrite_does_not_allocate_for_absent_tokens ... ok
test prompt_artifact::tests::rewrite_is_idempotent_and_reports_only_linked_records ... ok
test prompt_artifact::tests::rewrite_uses_expanded_reference_when_authored_token_is_absent ... ok
test prompt_artifact::tests::rewrite_shares_labels_for_one_destination ... ok
test prompt_artifact::tests::rewrite_reserves_existing_definitions_and_numeric_uses ... ok
test prompt_artifact::tests::sanitized_collisions_are_disambiguated ... ok
test prompt_literals::tests::ignores_unmatched_and_multiline_runs ... ok
test prompt_artifact::tests::rewrite_skips_literal_zones_and_existing_markdown_links ... ok
test prompt_literals::tests::keeps_crlf_lines_independent ... ok
test prompt_artifact::tests::selection_keeps_newest_rows_in_first_reference_order ... ok
test prompt_literals::tests::matches_equal_runs_while_allowing_shorter_nested_runs ... ok
test agent_scan::index::tests::output_variable_projection_backfills_replaces_and_deletes_rows ... ok
test prompt_artifact::tests::rewrite_reuses_matching_existing_definition ... ok
test procs::store::tests::retention_reports_only_store_owned_logs_for_deletion ... ok
test prompt_literals::tests::reports_utf8_byte_offsets ... ok
test provider_disable::tests::canonical_active_file_is_not_rewritten ... ok
test provider_disable::tests::invalid_inputs_are_rejected ... ok
test provider_disable::tests::mode_parse_accepts_exact_wire_strings ... ok
test prompt_literals::tests::recognizes_punctuation_and_word_adjacent_spans ... ok
test provider_priority::tests::classifier_normalizes_expired_supplied_context ... ok
test provider_disable::tests::malformed_envelope_deletes_state ... ok
test provider_disable::tests::try_set_returns_existing_record_without_mutating_it ... ok
test provider_disable::tests::clear_one_and_missing_clear_are_idempotent ... ok
test provider_priority::tests::invalid_values_are_rejected_without_writing ... ok
test provider_disable::tests::try_set_replaces_an_expired_record ... ok
test provider_disable::tests::unknown_v2_mode_is_pruned_without_deleting_valid_siblings ... ok
test provider_disable::tests::v1_expired_record_is_pruned_during_migration ... ok
test provider_disable::tests::exact_boundary_expiry_and_until_cleared_persistence ... ok
test provider_disable::tests::v1_file_migrates_in_place_to_hard_v2 ... ok
test provider_disable::tests::replacing_one_provider_preserves_siblings ... ok
test provider_priority::tests::ineligible_target_preserves_existing_priority_and_disable_file ... ok
test provider_disable::tests::malformed_and_expired_entries_are_pruned_independently ... ok
test provider_priority::tests::io_failures_are_reported ... ok
test provider_priority::tests::priority_provider_soft_or_hard_disable_keeps_both_causes ... ok
test provider_priority::tests::precedence_table_classifies_priority_overlay ... ok
test provider_priority::tests::read_only_context_builder_filters_expired_state ... ok
test provider_usage::tests::collection_problem_attention_keeps_empty_problem_and_silent_unknown_arms ... ok
test provider_usage::tests::collector_health_classifies_failure_boundaries_and_saturation ... ok
test provider_priority::tests::replacement_and_clear_require_complete_expected_record ... ok
test provider_priority::tests::relative_exact_and_indefinite_windows_round_trip ... ok
test provider_usage::tests::authoritative_empty_ok_is_allowed ... ok
test provider_usage::tests::not_applicable_clears_numeric_conclusions ... ok
test provider_usage::tests::empty_snapshot_is_empty_health ... ok
test provider_usage::tests::rejected_outranks_very_low ... ok
test provider_priority::tests::malformed_priority_degrades_with_diagnostic_and_valid_disables_survive ... ok
test provider_usage::tests::rejects_unknown_schema_negative_used_and_future_timestamps ... ok
test provider_usage::tests::missing_quantities_are_null_not_zero ... ok
test provider_usage::tests::usage_attention_rank_order_places_collection_problem_above_low ... ok
test provider_usage::tests::freshness_bands_use_two_and_four_cadences ... ok
test provider_usage::tests::rejects_duplicate_keys_empty_ok_and_impossible_periods ... ok
test provider_usage::tests::reset_at_now_has_passed ... ok
test provider_usage::tests::rejects_duplicate_providers_and_invalid_thresholds ... ok
test provider_usage::tests::public_json_rejects_unknown_observation_fields ... ok
test provider_disable::tests::v2_round_trip_get_set_try_set_and_clear_for_each_mode ... ok
test provider_usage::tests::mixed_ages_use_only_fresh_windows_in_the_numeric_summary ... ok
test provider_usage::tests::deterministic_ties_break_on_provider_and_window_key ... ok
test provider_usage::tests::reset_expiry_drops_numeric_summary_without_synthesizing_100 ... ok
test provider_usage::tests::shared_plus_model_specific_limits_do_not_replace_each_other ... ok
test provider_usage::tests::usage_refresh_due_respects_cadence_backoff_and_explicit ... ok
test provider_usage::tests::strips_controls_and_redacts_secret_diagnostics ... ok
test provider_usage::tests::collection_problem_attention_requires_consistent_failure_with_cached_data ... ok
test provider_usage::tests::unauthenticated_is_a_collection_problem ... ok
test provider_usage::tests::usage_refresh_backoff_grows_and_caps ... ok
test agent_stats::run::tests::runner_question_wait_uses_matching_gate_response_time ... ok
test provider_usage::tests::usage_refresh_failure_streak_tracks_first_failure_and_clears_on_success ... ok
test provider_usage::tests::vendor_drift_reason_code_is_accepted_and_unknown_codes_still_reject ... ok
test provider_usage::tests::usage_refresh_reservations_join_release_and_expire ... ok
test provider_usage::tests::unknown_scope_makes_model_conclusion_partial ... ok
test provider_usage::tests::usage_refresh_mark_due_is_once_per_reason_and_survives_future_due ... ok
test query::profile::tests::from_wire_rejects_digest_mismatch ... ok
test provider_usage::tests::usage_store_preserves_windows_after_failed_newer_attempt ... ok
test provider_usage::tests::window_applicability_is_declared_not_inferred ... ok
test query::profile::tests::from_wire_rejects_unknown_predicate ... ok
test query::searchable::tests::artifact_references_are_searchable ... ok
test query::searchable::tests::project_dir_name_basic ... ok
test provider_usage::tests::usage_store_advances_generation_and_rejects_stale_writers ... ok
test provider_usage::tests::usage_store_reports_bad_provider_records_without_repairing_on_read ... ok
test agent_stats::run::tests::runner_recovers_synthesized_hidden_lanes_without_trusting_the_stamp ... ok
test provider_usage::tests::usage_store_merges_partial_updates_and_fences_tombstones ... ok
test query::profile::tests::patch_profile_digest_matches_python_compiler ... ok
test provider_usage::tests::usage_refresh_admission_joins_defers_and_recovers_after_expiry ... ok
test provider_usage::tests::usage_store_decodes_old_schedules_and_isolates_future_schedule_fields ... ok
test provider_usage::tests::usage_store_projects_current_generation_collector_health_only ... ok
test agent_stats::run::tests::user_hidden_skipped_counts_only_runner_eligible_rows ... ok
test query::tests::canonical_any_special_implicit_and ... ok
test query::tests::ast_round_trips_through_json ... ok
test provider_disable::tests::concurrent_entries_are_returned_in_provider_order ... ok
test query::tests::canonical_not_around_and_gets_parens ... ok
test provider_usage::tests::usage_store_uses_private_file_permissions_and_ignores_temp_siblings ... ok
test query::tests::boolean_precedence_works_on_generic_rows ... ok
test query::tests::canonical_and_inside_or_gets_parens ... ok
test query::tests::canonical_property_filter_shorthands ... ok
test query::tests::canonical_simple_string ... ok
test query::tests::canonical_status_property ... ok
test query::tests::canonical_error_suffix_running_markers ... ok
test query::tests::boolean_profile_accepts_widened_values_and_normalizes_typed_literals ... ok
test query::tests::canonical_case_sensitive_string ... ok
test query::tests::canonical_escape_string_value ... ok
test query::tests::canonical_implicit_and ... ok
test query::tests::canonical_not_string ... ok
test provider_usage::tests::used_percent_fixture_preserves_raw_precision_and_overage ... ok
test query::tests::canonical_or_inside_and_gets_parens ... ok
test query::tests::canonical_widened_boolean_value_shapes_round_trip ... ok
test query::tests::flat_bare_boolean_flags_canonicalize_to_long_form ... ok
test query::tests::canonical_or ... ok
test query::tests::digest_mismatch_is_rejected_before_evaluation ... ok
test query::tests::flat_bare_boolean_flags_evaluate_like_key_true ... ok
test agent_stats::run::tests::runner_query_requires_matching_live_workspace_claim ... ok
test query::tests::host_bound_key_tables_match_python_registry ... ok
test query::tests::flat_negation_and_comma_rules ... ok
test query::tests::invalid_profile_is_structured_error ... ok
test query::tests::parse_any_special_expands_to_or ... ok
test query::tests::flat_predicates_evaluate_absent_facts_as_false ... ok
test query::tests::flat_partially_quoted_boolean_key_canonicalizes_as_quoted_text ... ok
test query::tests::flat_duration_bound_values_normalize_canonically ... ok
test query::tests::flat_canonical_groups_fields_then_predicates_then_text ... ok
test query::tests::generic_corpus_reuses_indexes_across_evaluations ... ok
test query::tests::generic_rows_honor_searchable_fields_and_predicates ... ok
test query::tests::flat_bare_boolean_flags_keep_existing_field_guards ... ok
test query::tests::parse_bare_word ... ok
test query::tests::parse_case_sensitive_string ... ok
test query::tests::parse_double_not_collapses_to_two_nots ... ok
test query::tests::parse_error_missing_operand ... ok
test query::tests::parse_error_suffix_and_string ... ok
test query::tests::flat_date_and_duration_bound_keys_compare_by_host_direction ... ok
test query::tests::parse_error_empty_query ... ok
test query::tests::parse_error_unmatched_paren ... ok
test query::tests::parse_implicit_and ... ok
test query::tests::parse_implicit_and_with_parens ... ok
test query::tests::parse_not_running_agent_shorthand ... ok
test query::tests::flat_repeated_values_are_any_match_and_exclusions_negate ... ok
test query::tests::parse_not_running_process_shorthand ... ok
test query::tests::flat_validates_enum_bool_and_int_literals ... ok
test query::tests::flat_tokenizer_rejects_boolean_syntax ... ok
test query::tests::parse_or_loosest ... ok
test query::tests::flat_profile_parses_closed_host_predicates_without_boolean_syntax ... ok
test query::tests::parse_not_tightest ... ok
test query::tests::parser_error_wire_kind_is_parser ... ok
test query::tests::flat_quoted_boolean_key_remains_free_text ... ok
test query::tests::patch_wrappers_match_explicit_patch_profile ... ok
test query::tests::parse_property_match ... ok
test query::tests::tokenize_any_special_only_standalone ... ok
test query::tests::tokenize_at_not_standalone_is_error ... ok
test query::tests::parse_standalone_exclamation_is_error_suffix ... ok
test query::tests::stitches_sidecar_bare_token_is_a_boolean_flag ... ok
test agent_stats::run::tests::runner_occupancy_merges_serial_family_and_counts_parallel ... ok
test query::tests::tokenize_bare_word_with_numbers ... ok
test query::tests::token_round_trips_through_json ... ok
test query::tests::tokenize_case_sensitive_string ... ok
test query::tests::sha_field_matches_a_prefix_of_the_stored_value ... ok
test query::tests::tokenize_dollar_not_standalone_is_error ... ok
test query::tests::tokenize_property_shorthands ... ok
test query::tests::tokenize_double_exclamation_not_standalone_is_two_nots ... ok
test query::tests::tokenize_quoted_with_escapes ... ok
test query::tests::tokenize_double_exclamation_standalone_is_not_error_suffix ... ok
test query::tests::tokenize_invalid_escape ... ok
test query::tests::tokenize_not_at_with_space ... ok
test query::tests::tokenize_not_dollar_with_space ... ok
test query::tests::tokenize_not_keyword_with_error_suffix ... ok
test query::tests::tokenize_origin_property ... ok
test query::tests::tokenize_paren_and_keywords ... ok
test query::tests::tokenize_property_quoted_value ... ok
test query::tests::tokenize_rejects_disabled_predicate_and_any_special ... ok
test query::tests::tokenize_rejects_undeclared_property_and_keeps_span ... ok
test agent_stats::run::tests::committing_agents_counts_distinct_names_not_runs ... ok
test parser::tests::full_section_parity_emits_structured_entries ... ok
test query::tests::tokenize_invalid_property_key ... ok
test query::tests::tokenize_status_shorthands ... ok
test query::tests::tokenize_standalone_at_and_bang ... ok
test query::tests::tokenize_status_shorthand_invalid ... ok
test query::tests::tokenize_unterminated_string ... ok
test query::tests::tokenize_status_shorthand_uppercase ... ok
test query::tests::tokenizer_error_wire_kind_is_tokenizer ... ok
test query::tests::tokenize_triple_specials ... ok
test queue_directive::tests::equivalent_spellings_compose_disjoint_fields ... ok
test queue_directive::tests::legacy_flag_helpers_always_enable_queue ... ok
test queue_directive::tests::explicit_zero_is_distinct_from_omitted ... ok
test queue_directive::tests::parenthesized_positional_and_aliases_round_trip ... ok
test queue_directive::tests::rejects_duplicates_even_when_values_match ... ok
test queue_directive::tests::preserves_source_spans_on_errors ... ok
test queue_directive::tests::rejects_malformed_parentheses_extra_positionals_and_wait_keys ... ok
test queue_directive::tests::rejects_empty_and_plus_forms_without_previous_agent_meaning ... ok
test query::tests::tokenize_uses_profile_fields_and_sigils ... ok
test referenced_by::tests::duplicate_block_collapses_to_one ... ok
test referenced_by::tests::unterminated_start_marker_extends_to_eof ... ok
test queue_directive::tests::rejects_invalid_and_overflow_integers ... ok
test referenced_by::tests::strip_normalizes_trailing_whitespace_for_stable_digests ... ok
test referenced_by::tests::upsert_places_block_at_bottom_and_is_idempotent ... ok
test referenced_by::tests::stray_end_marker_with_no_start_is_left_alone ... ok
test referenced_by::tests::render_caps_at_fifty_rows_and_reports_omitted ... ok
test runner_limit_override::tests::invalid_inputs_are_rejected ... ok
test referenced_by::tests::render_sorts_rows_and_numbers_links_through_the_shared_allocator ... ok
test sections::tests::commits_body_lines_use_six_space_indent_and_dot_for_blank ... ok
test sections::tests::commits_drawers_attach_to_current_entry ... ok
test runner_limit_override::tests::persisted_json_is_complete_and_clear_is_idempotent ... ok
test runner_limit_override::tests::exact_and_no_expiry_records_obey_boundary_expiry ... ok
test sections::tests::comments_basic_and_with_error_suffix ... ok
test sections::tests::deltas_glyph_to_change_type_mapping ... ok
test sections::tests::commits_line_starts_new_entry_and_strips_trailing_suffix ... ok
test runner_limit_override::tests::positive_limits_round_trip_and_replace ... ok
test sections::tests::commits_proposal_letter_carries_through ... ok
test referenced_by::tests::strip_leaves_a_document_with_no_block_untouched ... ok
test sections::tests::commits_running_agent_and_rejected_proposal_suffixes ... ok
test runner_limit_override::tests::malformed_stale_and_invalid_state_self_cleans ... ok
test referenced_by::tests::upsert_with_empty_table_removes_the_block ... ok
test editor::completion::tests::payload_inventory_discloses_the_scan_bound ... ok
test referenced_by::tests::render_parse_round_trips ... ok
test procs::store::tests::concurrent_writers_do_not_lose_rows ... ok
test sections::tests::deltas_requires_exactly_two_leading_spaces ... ok
test sections::tests::hooks_new_command_flushes_previous_hook ... ok
test sections::tests::hooks_command_then_status_line ... ok
test snippet_catalog::tests::composes_capitalized_aliases_and_preserves_remaining_case ... ok
test snippet_catalog::tests::colon_form_records_positional_argument ... ok
test snippet_catalog::tests::explicit_capitalized_trigger_wins_alias_collision ... ok
test sections::tests::mentors_legacy_profiles_without_counts_split_on_whitespace ... ok
test snippet_catalog::tests::analyzes_nested_positional_quoted_and_duplicate_calls ... ok
test snippet_catalog::tests::aliases_use_composed_templates_and_references_can_target_aliases ... ok
test sections::tests::mentors_entry_ref_suffix_marks_type_entry_ref ... ok
test snippet_catalog::tests::invalid_trigger_does_not_change_expansion ... ok
test snippet_catalog::tests::inbound_ordering_is_deterministic_and_unique ... ok
test snippet_catalog::tests::missing_target_and_boundary_rules ... ok
test snippet_catalog::tests::direct_and_indirect_cycles ... ok
test sections::tests::stitches_line_uses_same_entry_parser ... ok
test sections::tests::timestamps_hybrid_bracketed_yymmdd_parses ... ok
test snippet_catalog::tests::alias_pair_is_an_indirect_cycle_on_explicit_identities ... ok
test sections::tests::mentors_draft_marker_is_stripped ... ok
test sections::tests::timestamps_new_format_parses ... ok
test sections::tests::timestamps_legacy_bracketed_format_still_parses ... ok
test snippet_catalog::tests::alias_self_cycle_lands_on_explicit_identity ... ok
test sections::tests::mentors_entry_with_count_then_status ... ok
test sections::tests::mentors_running_status_without_timestamp_parses_as_none ... ok
test agent_stats::run::tests::runner_fixed_and_all_time_empty_ranges_have_distinct_contracts ... ok
test snippet_catalog::tests::validate_snippet_trigger_rejects_empty_and_punctuation ... ok
test snippet_session::session_tests::advance_and_retreat_on_an_inactive_session_are_no_ops ... ok
test snippet_session::session_tests::apply_edit_deletes_offsets_falling_before_the_first_stop ... ok
test snippet_catalog::tests::composes_unicode_aliases_and_handles_unchanged_leading_scalars ... ok
test snippet_session::session_tests::apply_edit_normalizes_unordered_edit_bounds ... ok
test snippet_session::session_tests::apply_edit_on_an_inactive_session_is_a_no_op ... ok
test sections::tests::hooks_running_agent_suffix_split_from_summary ... ok
test snippet_catalog::tests::unicode_template_spans_use_byte_offsets ... ok
test snippet_session::session_tests::apply_session_event_advance_retreat_apply_edit_and_clear_round_trip ... ok
test snippet_session::session_tests::apply_edit_remaps_stops_before_at_inside_and_after_the_edit ... ok
test snippet_session::session_tests::apply_session_event_expand_reports_the_new_cursor_offset ... ok
test snippet_session::session_tests::apply_session_event_drives_the_reported_bug_scenario_end_to_end ... ok
test snippet_session::session_tests::clear_ends_an_active_session ... ok
test snippet_session::session_tests::apply_session_event_plan_is_stateless_and_echoes_state_unchanged ... ok
test snippet_session::session_tests::deleting_a_whole_nested_expansion_drops_it_without_corrupting_the_enclosing_session ... ok
test snippet_session::session_tests::depth_cap_drops_outermost_session_on_overflow ... ok
test snippet_session::session_tests::event_kind_tags_match_the_documented_snake_case_names ... ok
test snippet_session::session_tests::event_result_serializes_with_the_documented_field_order ... ok
test snippet_session::session_tests::expand_outside_active_span_resets_instead_of_nesting ... ok
test snippet_session::session_tests::expanding_a_no_stop_plan_outside_any_session_clears_state ... ok
test snippet_session::session_tests::nesting_a_plan_with_no_stops_leaves_the_enclosing_session_untouched ... ok
test snippet_session::session_tests::nesting_at_a_stop_resumes_outer_session_after_inner_exhausts ... ok
test snippet_session::session_tests::retreat_at_start_and_advance_past_end_report_no_target ... ok
test snippet_session::session_tests::two_levels_of_nesting_resume_enclosing_sessions_in_order ... ok
test snippet_session::session_tests::state_serializes_with_the_documented_field_order ... ok
test snippet_session::tests::continuation_line_indentation_can_be_disabled ... ok
test snippet_session::tests::continuation_lines_are_indented_and_offsets_shift ... ok
test snippet_session::tests::escaped_dollars_are_literal_and_not_tabstops ... ok
test snippet_session::tests::missing_zero_appends_implicit_final_stop ... ok
test snippet_session::tests::multi_digit_tabstops_sort_by_number ... ok
test snippet_session::tests::offsets_are_character_offsets_not_byte_offsets ... ok
test snippet_session::tests::repeated_tabstop_numbers_only_create_one_stop ... ok
test snippet_session::tests::templates_without_markers_have_no_stops ... ok
test source_language::tests::diff_sniff_is_stdin_only ... ok
test source_language::tests::filename_wins_over_shebang_and_diff_prefix ... ok
test snippet_catalog::tests::snippet_reference_golden_vectors ... ok
test source_language::tests::extensionless_shebangs_cover_python_and_shell_dialects ... ok
test source_language::tests::justfile_is_plain_and_not_make ... ok
test source_language::tests::hints_json_roundtrip_and_schema_errors ... ok
test source_language::tests::logical_filename_uses_source_then_vcs_then_resolved ... ok
test source_language::tests::mapping_table_covers_declared_families ... ok
test source_language::tests::request_and_result_json_roundtrip ... ok
test source_language::tests::shebang_is_skipped_for_suffixed_unknown_files ... ok
test source_language::tests::stdin_diff_sniff_positive_and_negative_samples ... ok
test source_language::tests::suffix_matching_is_case_insensitive_and_basenames_are_exact ... ok
test source_language::tests::trusted_categories_override_filename_and_skip_sniffing ... ok
test source_language::tests::unknown_and_empty_names_are_not_supported_text ... ok
test source_language::tests::windows_and_unix_paths_use_basename ... ok
test status::field_updates::tests::apply_status_update_idempotent_when_status_already_matches ... ok
test status::field_updates::tests::apply_status_update_no_matching_patch_is_noop ... ok
test status::field_updates::tests::apply_status_update_preserves_unrelated_lines ... ok
test status::field_updates::tests::apply_status_update_replaces_only_target_status ... ok
test status::field_updates::tests::read_status_matches_first_patch ... ok
test status::field_updates::tests::read_status_matches_second_patch ... ok
test status::field_updates::tests::read_status_preserves_workspace_suffix ... ok
test status::field_updates::tests::read_status_returns_none_when_missing ... ok
test status::name::tests::next_suffix_reserves_legacy_double_underscore_slot ... ok
test status::name::tests::next_suffix_skips_existing ... ok
test status::name::tests::next_suffix_starts_at_one ... ok
test source_language::tests::prefix_inspection_is_bounded_to_8_kib ... ok
test provider_priority::tests::concurrent_priority_changes_and_auto_disables_are_serialized ... ok
test agent_stats::run::tests::runner_monitor_handoff_is_query_window_invariant ... ok
test status::planner::tests::schema_version_mismatch_returns_error ... ok
test status::name::tests::has_suffix_recognises_single_and_double_underscore ... ok
test provider_disable::tests::first_writer_wins_under_contention_without_extending_or_losing_siblings ... ok
test agent_scan::index::tests::windowed_query_selects_completed_budget_when_active_exceeds_limit ... ok
test status::constants::tests::legacy_ready_to_mail_suffix_stripped ... ok
test status::planner::tests::archived_terminal_no_further_transitions ... ok
test status::planner::tests::archive_action_none_within_archive_class ... ok
test status::constants::tests::valid_transitions_allow_known_pairs ... ok
test status::constants::tests::workspace_suffix_stripped_from_status ... ok
test status::constants::tests::workspace_suffix_does_not_block_validation ... ok
test status::constants::tests::unknown_statuses_rejected ... ok
test status::planner::tests::parent_wip_blocks_child_to_mailed ... ok
test status::planner::tests::invalid_transition_validate_true_rejects ... ok
test status::planner::tests::archive_action_to_archive_on_submitted ... ok
test status::planner::tests::archive_action_none_within_main_class ... ok
test status::planner::tests::ready_to_draft_picks_lowest_free_suffix ... ok
test status::planner::tests::invalid_transition_error_format_matches_python ... ok
test status::planner::tests::legacy_ready_to_mail_suffix_stripped_for_validation ... ok
test status::planner::tests::submitted_terminal_no_further_transitions ... ok
test status::planner::tests::invalid_transition_validate_false_allows ... ok
test status::planner::tests::parent_constraint_skipped_for_reverted_branch ... ok
test status::planner::tests::unknown_status_rejected_under_validation ... ok
test status::planner::tests::parent_ready_does_not_block_mailed ... ok
test status::planner::tests::archive_action_from_archive_under_no_validate ... ok
test status::constants::tests::unmodified_status_passes_through ... ok
test status::planner::tests::wip_to_draft_no_suffix_no_mentor ... ok
test status::constants::tests::terminal_statuses_have_no_outgoing_transitions ... ok
test status::planner::tests::ready_to_draft_appends_suffix_and_sets_mentor ... ok
test status::planner::tests::ready_to_draft_blocked_by_invalid_children ... ok
test status::planner::tests::draft_to_ready_no_suffix_clears_mentors_only ... ok
test status::planner::tests::reverted_terminal_no_further_transitions ... ok
test status::planner::tests::wip_to_ready_blocked_by_sibling_unreverted_children ... ok
test status::wire::tests::json_shape_keeps_optional_fields_as_null ... ok
test status::planner::tests::workspace_suffix_normalised_for_validation ... ok
test status::wire::tests::plan_round_trips_through_json ... ok
test status::wire::tests::request_round_trips_through_json ... ok
test status::wire::tests::schema_mismatch_returns_error ... ok
test suffix::tests::legacy_tilde_colon_is_plain ... ok
test store_lock::tests::timeout_parser_accepts_positive_floats_and_rejects_bad_values ... ok
test suffix::tests::none_input_returns_none_pair ... ok
test suffix::tests::metahook_promotes_error_to_metahook_complete ... ok
test suffix::tests::long_prefixes_take_priority_over_short ... ok
test suffix::tests::standalone_markers_have_empty_value ... ok
test suffix::tests::unknown_prefix_returns_value_unchanged ... ok
test suffix::tests::entry_ref_recognizes_digit_optional_letter ... ok
test task_type::snapshot::tests::parse_rejects_invalid_json ... ok
test task_type::spec::tests::field_types_are_the_scalar_subset_of_property_types ... ok
test task_type::spec::tests::digest_is_stable_across_omitted_and_explicit_defaults ... ok
test task_type::spec::tests::rejects_missing_label_summary_and_when_to_use_caps ... ok
test task_type::spec::tests::rejects_reserved_and_malformed_slugs ... ok
test task_type::spec::tests::omitted_create_refusal_does_not_change_digest ... ok
test task_type::spec::tests::rejects_unsupported_schema_version ... ok
test status::planner::tests::draft_to_ready_with_suffix_strips_and_clears_mentors ... ok
test status::planner::tests::wip_to_ready_with_suffix_strips ... ok
test task_type::spec::tests::reserved_slugs_are_the_three_issue_types_and_four_filter_sentinels ... ok
test task_type::values::tests::invalid_spec_is_a_hard_error ... ok
test task_type::render::tests::missing_placeholder_value_is_an_error ... ok
test task_type::spec::tests::rejects_unknown_default_size ... ok
test task_type::render::tests::does_not_rescan_substituted_values ... ok
test task_type::spec::tests::accepts_single_cell_glyph_and_hex_accent ... ok
test task_type::spec::tests::accepts_flag_as_a_claimable_task_type_slug ... ok
test task_type::render::tests::renders_placeholders_verbatim ... ok
test task_type::spec::tests::accepts_spec_with_no_body_template ... ok
test task_type::render::tests::empty_without_template ... ok
test task_type::spec::tests::rejects_empty_or_unknown_roles ... ok
test task_type::spec::tests::create_refusal_changes_digest_and_rejects_empty_or_overlong ... ok
test bead::schema::tests::task_ready_migration_preserves_rows_and_dependencies ... ok
test task_type::spec::tests::rejects_malformed_glyph_and_accent ... ok
test task_type::values::tests::rejects_padded_or_non_decimal_integers_and_short_dates ... ok
test editor::completion::tests::commit_inventory_keeps_non_sidecar_repository_kinds ... ok
test task_type::spec::tests::valid_spec_passes_and_digest_is_stable ... ok
test task_type::values::tests::empty_required_string_is_missing ... ok
test task_type::spec::tests::rejects_empty_enum_values_and_invalid_regex ... ok
test text_tail::tests::applies_line_budget_before_character_budget ... ok
test text_tail::tests::keeps_short_text_unchanged ... ok
test text_tail::tests::trims_selected_tail_by_unicode_character_count ... ok
test task_type::spec::tests::rejects_unsupported_field_types_outside_scalar_subset ... ok
test vcs_log::classify::tests::ahead_wins_when_sets_overlap ... ok
test text_tail::tests::zero_character_budget_returns_empty_tail_after_line_selection ... ok
test text_tail::tests::zero_line_budget_returns_empty_tail ... ok
test vcs_log::aggregate::tests::empty_input_returns_empty ... ok
test vcs_log::aggregate::tests::aggregated_row_serializes_flat ... ok
test vcs_log::aggregate::tests::equal_timestamp_tie_break_is_repo_then_full_id ... ok
test vcs_log::aggregate::tests::interleaves_repos_by_timestamp_desc ... ok
test task_type::spec::tests::rejects_validator_keys_on_the_wrong_field_type ... ok
test vcs_log::aggregate::tests::limit_zero_returns_empty ... ok
test vcs_log::aggregate::tests::preserves_commit_presence ... ok
test vcs_log::aggregate::tests::truncates_to_limit ... ok
test vcs_log::classify::tests::classifies_synced_ahead_and_behind ... ok
test task_type::spec::tests::rejects_duplicate_and_bad_field_names ... ok
test vcs_log::commit_type::tests::auto_type_alias_deduplicates_to_automatic ... ok
test vcs_log::commit_type::tests::automatic_commit_includes_concrete_terminal_type ... ok
test vcs_log::commit_type::tests::commit_wrapper_uses_subject_body_and_parent_count ... ok
test vcs_log::commit_type::tests::ignores_non_terminal_tag_shaped_text ... ok
test vcs_log::commit_type::tests::includes_merge_and_patch_labels_after_concrete_type ... ok
test task_type::spec::tests::rejects_template_placeholders_that_are_undeclared_or_data_only ... ok
test task_type::values::tests::reports_missing_unknown_and_invalid_together ... ok
test vcs_log::commit_type::tests::legacy_stitch_inference_still_uses_stitch_provenance ... ok
test vcs_log::commit_type::tests::legacy_patch_key_and_empty_patch_values_are_handled ... ok
test vcs_log::merge_summary::tests::merge_prefix_without_known_shape_returns_none ... ok
test vcs_log::commit_type::tests::stitch_type_deduplicates_provenance_and_concrete_type ... ok
test vcs_log::merge_summary::tests::parses_remote_branch_summary ... ok
test vcs_log::commit_type::tests::manual_commit_has_only_manual_type ... ok
test vcs_log::merge_summary::tests::parses_remote_branch_summary_with_target ... ok
test vcs_log::merge_summary::tests::partial_pull_request_shape_returns_none ... ok
test vcs_log::merge_summary::tests::pull_request_empty_body_has_no_headline ... ok
test task_type::values::tests::valid_values_return_no_errors ... ok
test vcs_log::merge_summary::tests::parses_branch_summary ... ok
test vcs_log::merge_summary::tests::parses_github_pull_request_summary ... ok
test vcs_log::merge_summary::tests::parses_branch_summary_with_target ... ok
test vcs_log::origin::tests::classifies_plain_commit_as_manual ... ok
test vcs_log::origin::tests::ignores_tag_shaped_body_text ... ok
test vcs_log::origin::tests::non_stitch_type_classifies_as_auto ... ok
test vcs_log::origin::tests::type_stitch_classifies_as_stitch ... ok
test vcs_log::parsers::tests::git_appends_newline_between_records_is_stripped ... ok
test vcs_log::origin::tests::legacy_agent_bead_or_plan_classifies_as_stitch ... ok
test vcs_log::origin::tests::legacy_type_spelling_classifies_as_stitch ... ok
test vcs_log::parsers::tests::legacy_seven_field_commit_has_no_parents ... ok
test vcs_log::parsers::tests::body_containing_unit_separator_stays_in_body ... ok
test vcs_log::parsers::tests::multiline_body_is_preserved_verbatim ... ok
test vcs_log::merge_summary::tests::unrecognized_subject_returns_none ... ok
test vcs_log::parsers::tests::multiple_commits_preserve_order ... ok
test vcs_log::parsers::tests::empty_stream_returns_empty ... ok
test vcs_log::parsers::tests::commit_with_stitch_type_gets_stitch_origin ... ok
test vcs_log::parsers::tests::record_with_too_few_fields_is_dropped ... ok
test vcs_log::parsers::tests::record_with_unparseable_timestamp_is_dropped ... ok
test vcs_log::parsers::tests::octopus_merge_parses_all_parent_ids ... ok
test vcs_log::parsers::tests::root_commit_empty_parent_field_has_no_parents ... ok
test vcs_log::parsers::tests::trailing_record_separator_yields_no_blank_commit ... ok
test wire::tests::delta_wire_uses_long_form ... ok
test task_type::values::tests::reports_string_max_length_and_allows_optional_fields_to_be_absent ... ok
test wire::tests::empty_lists_serialize_as_arrays_not_null ... ok
test task_type::snapshot::tests::rejects_digest_mismatch_and_duplicate_slugs ... ok
test vcs_log::parsers::tests::single_commit_parses_all_fields ... ok
test wire::tests::none_fields_serialize_as_json_null ... ok
test wire::tests::legacy_changespec_wire_deserializes_canonical_patch_shape ... ok
test wire::tests::legacy_cl_or_pr_key_deserializes_as_pr_url ... ok
test wire::tests::patch_wire_deserializes_legacy_changespec_shape ... ok
test workspace_lease::tests::authorize_rejects_primary_and_reserved_numbers ... ok
test workspace_lease::tests::empty_operation_uses_the_step_name_alone ... ok
test wire::tests::legacy_wire_field_order_matches_python ... ok
test workspace_lease::tests::failure_message_names_step_and_forbids_primary_fallback ... ok
test workspace_lease::tests::pool_bounds_match_unified_claim_range ... ok
test workspace_lease::tests::primary_error_names_legacy_spelling ... ok
test wire::tests::parse_error_wire_shape ... ok
test workspace_lease::tests::validate_policy_requires_kind_identity_and_leasable_workspace ... ok
test task_type::values::tests::validates_enum_integer_and_date ... ok
test wire::tests::patch_wire_serializes_canonical_stitch_keys ... ok
test xprompt_catalog::tests::catalog_payloads_without_memory_fields_still_deserialize ... ok
test wire::tests::source_span_round_trips ... ok
test wire::tests::populated_patch_round_trips ... ok
test xprompt_catalog::tests::computes_known_project_local_config_definition_range ... ok
test xprompt_catalog::tests::home_skills_use_the_skill_namespace_and_project_qualified_form ... ok
test xprompt_catalog::tests::invalid_memory_notes_become_diagnostics_instead_of_silent_gaps ... ok
test xprompt_catalog::tests::explicit_project_selection_picks_that_projects_memory_only ... ok
test xprompt_catalog::tests::ordinary_definitions_cannot_claim_the_reserved_memory_namespace ... ok
test xprompt_catalog::tests::canonical_project_sources_win_with_legacy_read_compatibility ... ok
test xprompt_catalog::tests::config_workflows_are_ignored_but_file_backed_project_workflows_load ... ok
test task_type::snapshot::tests::round_trips_and_sorts_by_slug ... ok
test task_type::snapshot::tests::round_trips_optional_create_refusal_and_omits_it_when_absent ... ok
test xprompt_catalog::tests::loads_plugin_file_and_config_catalog_sources ... ok
test agent_scan::selector::tests::multiple_selectors_preserve_order_and_dedup ... ok
test xprompt_catalog::tests::known_projects_use_display_names_aliases_and_gp_fallback ... ok
test workspace_lease::tests::normalize_maps_legacy_primary_only ... ok
test xprompt_catalog::tests::project_config_collision_reports_split_state ... ok
test xprompt_catalog::tests::packaged_skill_frame_template_is_not_a_skill_source ... ok
test agent_stats::run::tests::runner_query_filters_stale_and_never_started_records ... ok
test xprompt_catalog::tests::packaged_skills_load_from_nested_xprompts_skills_only ... ok
test xprompt_catalog::tests::memory_notes_load_as_namespaced_no_argument_xprompt_memories ... ok
test agent_stats::run::tests::aggregates_window_outcomes_metadata_and_runtime ... ok
test xprompt_text_block::tests::closes_at_end_of_region ... ok
test xprompt_catalog::tests::yaml_child_key_range_finds_immediate_quoted_children ... ok
test xprompt_catalog::tests::pseudo_sources_do_not_get_definition_paths ... ok
test xprompt_text_block::tests::closes_before_comma_of_next_argument ... ok
test xprompt_text_block::tests::closes_before_paren_brace_or_pipe ... ok
test xprompt_catalog::tests::project_memory_shadows_home_memory_of_the_same_stem ... ok
test xprompt_text_block::tests::overlapping_closer_before_paren ... ok
test xprompt_text_block::tests::rejects_non_opener ... ok
test xprompt_text_block::tests::skips_inner_marker_before_comma_terminator ... ok
test xprompt_text_block::tests::shared_corpus_loads ... ok
test xprompt_text_block::tests::unterminated_block_returns_none ... ok
test xprompt_catalog::tests::split_canonical_and_legacy_memory_state_is_a_collision_error ... ok
test xprompt_catalog::tests::project_catalog_uses_canonical_namespace_and_filter_refs ... ok
test xprompt_catalog::tests::rejects_misplaced_skill_definitions_in_both_directions ... ok
test xprompt_catalog::tests::parity_fixture_covers_supported_catalog_sources ... ok
test agent_stats::run::tests::runner_occupancy_handles_overlap_carry_in_waits_and_boundaries ... ok
test bead::schema::tests::snoozed_status_migration_admits_snoozed_tasks_and_keeps_close_history ... ok
test xprompt_catalog::tests::parses_markdown_frontmatter_local_xprompts_without_global_entry ... ok
test bead::schema::tests::relax_migration_preserves_claimed_rows_and_related_data ... ok
test xprompt_catalog::tests::loads_native_snippet_catalog_with_user_overrides ... ok
test agent_stats::run::tests::runner_eligibility_honors_family_workflow_visibility_and_project ... ok
test xprompt_catalog::tests::native_snippet_catalog_resolves_references_after_user_merge ... ok
test xprompt_catalog::tests::converts_native_xprompt_snippet_templates ... ok
test agent_scan::selector::tests::exact_key_wildcard_uses_newest_artifact_only ... ok
test bead::schema::tests::drop_flag_type_migration_removes_flag_rows_and_column ... ok
test agent_stats::run::tests::aggregates_ranked_xprompt_usage_and_focused_breakdowns ... ok
test agent_scan::selector::tests::hood_and_global_selectors_collapse_repeated_runs ... ok
test telemetry::store::tests::wal_initialization_lock_wait_is_bounded ... ok
test xprompt_catalog::tests::loads_markdown_and_workflow_with_canonical_insertions ... ok
test agent_stats::run::tests::runner_inherited_monitor_id_and_artifact_stamp_do_not_move_start_back ... ok
test xprompt_catalog::tests::memory_entries_render_as_memory_with_a_navigable_definition ... ok
test xprompt_catalog::tests::projects_repeatable_agent_input_metadata ... ok
test telemetry::store::tests::histogram_quantile_interpolates_cumulative_buckets ... ok
test telemetry::store::tests::corrupt_store_is_quarantined_and_recreated ... ok
test xprompt_catalog::tests::filters_step_inputs_and_formats_defaults ... ok
test agent_scan::selector::tests::unscoped_key_wildcard_and_unnamed_rows ... ok
test procs::store::tests::held_exclusive_lock_bounds_reader_and_writer_waits ... ok
test telemetry::store::tests::gauge_instant_query_uses_latest_live_value_per_source ... ok
test agent_stats::run::tests::runner_diagnostics_separate_malformed_rows_and_invalid_intervals ... ok
test agent_scan::selector::tests::unscoped_and_exact_selectors_use_newest_artifact ... ok
test agent_stats::run::tests::attributes_project_and_patch_work_with_filters_and_statuses ... ok
test telemetry::store::tests::counter_deltas_aggregate_and_group ... ok
test agent_stats::run::tests::runner_peak_can_exceed_ten_and_long_trend_stays_bounded ... ok
test agent_scan::selector::tests::hidden_project_limit_and_ambiguity ... ok
test agent_scan::selector::tests::nested_paths_and_failures_are_precise ... ok
test store_lock::tests::timeout_names_holder_and_does_not_materially_overshoot_deadline ... ok
test telemetry::store::tests::retention_folds_through_both_rollup_tiers_before_deletion ... ok
test prompt_stash::store::tests::held_exclusive_lock_bounds_reader_and_writer_waits ... ok
test xprompt_catalog::tests::parses_xprompt_workflow_and_input_descriptions ... ok
test telemetry::store::tests::exact_label_cleanup_previews_and_deletes_every_tier ... ok
test agent_scan::index::tests::vacuum_reclaims_freelist_pages_and_preserves_rows ... ok
test editor::completion::tests::commit_inventory_skips_sidecars_before_reporting_the_row_cap ... ok
test effort_override::tests::lock_wait_is_bounded ... ok
test editor::completion::tests::commit_log_reports_an_expired_budget_instead_of_empty_output ... ok
test telemetry::store::tests::concurrent_writers_preserve_every_delta ... ok
test provider_priority::tests::lock_wait_is_bounded ... ok
test runner_limit_override::tests::lock_wait_is_bounded ... ok
test agent_scan::index::tests::stale_dismissed_suffixes_do_not_consume_active_limit ... ok
test provider_disable::tests::try_set_rejects_invalid_inputs_and_times_out_on_lock ... ok
test provider_disable::tests::lock_wait_is_bounded ... ok
test store_lock::tests::waiter_acquires_after_more_than_the_old_two_second_bound ... ok
test agent_scan::index::tests::hidden_terminal_retention_bounds_rebuild_and_preserves_anchors ... ok

test result: ok. 2360 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 3.43s

     Running tests/agent_scan_parity.rs (/mnt/poseidon/cargo-target/debug/deps/agent_scan_parity-d466beab4086fea6)

running 45 tests
test absent_and_invalid_xprompts_are_soft_scan_errors ... ok
test explicit_agent_clan_preserves_sequential_family_fields ... ok
test missing_root_returns_empty_snapshot ... ok
test launch_xprompts_preserves_swarm_kind ... ok
test launch_xprompts_project_to_deduplicated_deterministic_records ... ok
test imported_source_owner_survives_live_scan ... ok
test exact_dir_scan_returns_only_requested_valid_unique_dirs ... ok
test exact_dir_scan_honors_project_and_workflow_filters ... ok
test bounded_newest_first_limits_completed_without_hiding_incomplete ... ok
test bounded_not_before_applies_to_completed_rows_only ... ok
test scalar_agent_meta_timestamps_are_normalized_to_lists ... ok
test scanner_keeps_parent_epic_and_authored_plan_references_separate ... ok
test disable_prompt_step_markers ... ok
test done_record_parses_done_marker ... ok
test disable_raw_prompt_snippet ... ok
test scanner_accepts_mixed_legacy_and_day_sharded_ace_run_dirs ... ok
test failed_record_carries_error_and_traceback ... ok
test home_running_record_has_running_marker ... ok
test options_round_trip_through_snapshot ... ok
test mentor_dir_is_walked ... ok
test pending_question_marker_is_surfaced_when_present ... ok
test only_workflow_dirs_filters_records ... ok
test selective_marker_options_skip_payloads_but_keep_done_presence ... ok
test max_prompt_snippet_bytes_truncates ... ok
test records_are_sorted_deterministically ... ok
test malformed_agent_meta_is_skipped ... ok
test pending_question_marker_is_absent_when_file_missing ... ok
test running_record_carries_agent_meta ... ok
test running_record_carries_wait_completed_at ... ok
test retried_records_link_via_lineage_fields ... ok
test repeat_stopped_record_parses_repeat_stop_fields ... ok
test scan_returns_one_record_per_artifact_dir ... ok
test running_record_prefers_canonical_agent_meta_tribe ... ok
test stats_count_decode_errors ... ok
test waiting_marker_decode_error_does_not_crash ... ok
test workflow_root_record_has_state_and_steps ... ok
test waiting_marker_carries_runner_slot_fields ... ok
test snapshot_serializes_to_json ... ok
test artifact_index_metadata_helpers_round_trip ... ok
test running_record_carries_bounded_json_output_variables ... ok
test artifact_index_status_counts_artifact_and_dismissed_rows ... ok
test plan_committed_survives_live_scan_and_indexed_reads ... ok
test running_record_carries_linked_repos_through_scan_and_index ... ok
test agent_family_parallel_survives_live_scan_and_indexed_reads ... ok
test workflow_state_hidden_is_parsed_and_indexed ... ok

test result: ok. 45 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.05s

     Running tests/artifact_ref_commit_budget.rs (/mnt/poseidon/cargo-target/debug/deps/artifact_ref_commit_budget-cdd6d9c29f507779)

running 1 test
test commit_inventory_budget_override_controls_whether_rows_survive ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.28s

     Running tests/bead_event_parity.rs (/mnt/poseidon/cargo-target/debug/deps/bead_event_parity-419317221eb7ebc3)

running 33 tests
test close_event_stamps_an_issue_updated_to_closed_without_a_timestamp ... ok
test cross_stream_dependencies_resolve_after_all_creates ... ok
test dependency_remove_payload_rejects_a_source_mismatch ... ok
test dependency_add_remove_add_replays_to_present ... ok
test byte_identical_concurrent_note_append_merges_once ... ok
test concurrent_note_appends_merge_without_losing_text ... ok
test dependency_remove_replay_tolerates_a_target_removed_first ... ok
test concurrent_close_projection_is_independent_of_branch_order ... ok
test event_validation_rejects_operation_payload_mismatch ... ok
test every_transition_out_of_closed_starts_a_new_close_interval ... ok
test dependency_remove_replay_is_tolerant_and_projection_round_trips ... ok
test merge_event_stream_accepts_interleaved_additions_and_preserves_ids ... ok
test merge_event_stream_keeps_exact_duplicate_append_once ... ok
test legacy_empty_timestamps_still_import_to_valid_events ... ok
test merge_event_stream_rejects_deleted_or_rewritten_base_events ... ok
test merge_event_stream_orders_non_base_union_deterministically ... ok
test note_appended_composes_after_a_legacy_note_snapshot ... ok
test event_import_preserves_legacy_defaults_and_corrupt_jsonl_tolerance ... ok
test jsonl_import_to_events_reduces_to_byte_compatible_projection ... ok
test event_import_mints_reproducible_content_hashed_ids ... ok
test reduce_applies_merged_stream_events_in_recorded_order ... ok
test merge_event_stream_supports_sequential_rebase_replay ... ok
test note_appended_matches_legacy_note_rendering_and_composes ... ok
test reducer_handles_current_mutation_operation_variants ... ok
test redundant_close_keeps_the_first_close_projection ... ok
test same_timestamp_dependency_add_replays_before_remove_across_streams ... ok
test reducer_removes_plan_children_and_dependency_edges_on_cascade_remove ... ok
test merge_event_stream_unions_concurrent_appends_deterministically ... ok
test merge_event_stream_union_is_associative_and_idempotent ... ok
test task_plus_one_replay_honors_observation_window_freshness ... ok
test serialized_event_store_fixture_matches_import_and_reduces ... ok
test reduce_survives_many_merged_streams_with_non_monotonic_timestamps ... ok
test write_event_store_leaves_an_unrelated_streams_bytes_unchanged_across_a_mutation ... ok

test result: ok. 33 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/bead_read_parity.rs (/mnt/poseidon/cargo-target/debug/deps/bead_read_parity-db36fc2d548e0a08)

running 15 tests
test doctor_notes_explicitly_unavailable_plan_roots ... ok
test doctor_reports_orphan_nested_plan_records ... ok
test event_manifest_repair_refuses_invalid_canonical_streams ... ok
test doctor_reports_invalid_event_store_without_legacy_fallback ... ok
test issue_detail_preserves_unresolved_relationship_slots ... ok
test event_manifest_repair_refuses_unsupported_event_schema ... ok
test issue_detail_legacy_snapshot_keeps_import_compatible_fallback ... ok
test doctor_reports_orphans_in_stale_legacy_projection ... ok
test event_manifest_repair_recounts_missing_or_stale_metadata_idempotently ... ok
test doctor_reports_projection_fields_and_redundant_close_census ... ok
test event_store_wins_over_stale_legacy_projection ... ok
test event_store_supports_read_queries_without_legacy_projection ... ok
test doctor_groups_plan_reference_diagnostics_without_changing_compatibility ... ok
test read_queries_match_python_contract_ordering ... ok
test issue_detail_link_neighborhood_preserves_event_provenance ... ok

test result: ok. 15 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.02s

     Running tests/bead_storage_parity.rs (/mnt/poseidon/cargo-target/debug/deps/bead_storage_parity-29becc1d21a157c4)

running 8 tests
test corrupt_and_empty_fixtures_match_python_tolerance ... ok
test current_schema_fixture_loads_hierarchy_dependencies_and_metadata ... ok
test export_current_fixture_is_byte_compatible ... ok
test import_from_file_uses_same_parser ... ok
test import_missing_file_returns_empty_outcome ... ok
test load_config_fixture_matches_python_shape ... ok
test task_and_ready_values_round_trip_with_python_wire_spelling ... ok
test legacy_jsonl_fixtures_get_python_defaults ... ok

test result: ok. 8 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/config_parity.rs (/mnt/poseidon/cargo-target/debug/deps/config_parity-fe92c96eca149ab4)

running 20 tests
test axe_composition_overlays_wait_runners_with_exact_provenance ... ok
test axe_description_requirements_validate_only_the_merged_config ... ok
test deep_merge_lists_replace_vs_concatenate ... ok
test axe_composition_reports_attributed_legacy_and_identity_diagnostics ... ok
test axe_composition_retains_legacy_defaults_and_exact_key_provenance ... ok
test field_model_flattens_nested_and_classifies ... ok
test plan_edit_exact_key_path_preserves_dotted_mapping_keys ... ok
test inventory_diagnoses_glossary_outside_local_layer ... ok
test axe_mutation_promotes_target_legacy_list_without_dropping_entries ... ok
test plan_edit_rejects_missing_empty_and_contradictory_paths ... ok
test merge_layers_matches_python_deep_merge_golden ... ok
test plan_edit_unknown_target_errors ... ok
test plan_edit_set_builds_write_plan_and_preview ... ok
test axe_entry_mutation_propagates_description_shape_to_diagnostics ... ok
test plan_edit_unset_removes_key_and_warns_on_readonly_target ... ok
test axe_entry_mutation_propagates_required_descriptions_to_preview ... ok
test axe_inventory_marks_generated_instances_as_base_owned ... ok
test axe_sparse_mutation_keeps_inherited_fields_and_matches_candidate_composition ... ok
test inventory_reports_effective_value_and_provenance ... ok
test validate_detects_violations ... ok

test result: ok. 20 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/git_query_parity.rs (/mnt/poseidon/cargo-target/debug/deps/git_query_parity-51f09d47aa3aa3ef)

running 33 tests
test derive_workspace_name_falls_back_to_root_path_when_remote_blank ... ok
test derive_workspace_name_falls_back_to_root_path_when_remote_none ... ok
test derive_workspace_name_https_remote_with_dot_git_suffix ... ok
test derive_workspace_name_https_remote_without_dot_git_suffix ... ok
test derive_workspace_name_path_like_remote ... ok
test derive_workspace_name_remote_dot_git_only_returns_none ... ok
test derive_workspace_name_remote_takes_priority_over_root ... ok
test derive_workspace_name_returns_none_when_both_inputs_empty ... ok
test derive_workspace_name_ssh_remote_with_dot_git_suffix ... ok
test git_name_status_entry_wire_round_trips_through_json ... ok
test git_name_status_entry_wire_serializes_to_python_shape ... ok
test git_query_wire_schema_version_is_one ... ok
test parse_branch_name_detached_head_returns_none ... ok
test parse_branch_name_empty_stdout_returns_none ... ok
test parse_branch_name_simple_value ... ok
test parse_branch_name_strips_surrounding_whitespace ... ok
test parse_branch_name_whitespace_only_returns_none ... ok
test parse_conflicted_files_empty_stdout_returns_empty_list ... ok
test parse_conflicted_files_only_blank_lines_returns_empty ... ok
test parse_conflicted_files_preserves_path_order ... ok
test parse_conflicted_files_strips_blank_lines ... ok
test parse_local_changes_clean_tree_returns_none ... ok
test parse_local_changes_dirty_tree_returns_stripped_text ... ok
test parse_local_changes_whitespace_only_returns_none ... ok
test parse_name_status_copy_with_score_carries_paired_paths ... ok
test parse_name_status_empty_stream_returns_empty_list ... ok
test parse_name_status_mixed_simple_and_rename_in_one_stream ... ok
test parse_name_status_rename_with_score_carries_paired_paths ... ok
test parse_name_status_simple_status_letters ... ok
test parse_name_status_skips_empty_status_tokens ... ok
test parse_name_status_trailing_nul_is_ignored ... ok
test parse_name_status_truncated_rename_falls_back_to_single_path ... ok
test parse_name_status_truncated_status_only_drops_entry ... ok

test result: ok. 33 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/golden_corpus_parity.rs (/mnt/poseidon/cargo-target/debug/deps/golden_corpus_parity-8a3f4721f4628972)

running 3 tests
test archive_corpus_matches_python_golden_after_end_line_normalization ... ok
test rust_real_end_line_is_strictly_greater_than_python_placeholder ... ok
test project_corpus_matches_python_golden_after_end_line_normalization ... ok

test result: ok. 3 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running tests/notification_store_parity.rs (/mnt/poseidon/cargo-target/debug/deps/notification_store_parity-1bdee9f8d671e365)

running 57 tests
test notification_activity_cursor_uses_resurface_time_and_id_tiebreaker ... ok
test notification_append_counts_returns_metadata_without_rows ... ok
test notification_append_and_rewrite_round_trip_jsonl ... ok
test notification_append_counts_produces_byte_identical_jsonl ... ok
test notification_bulk_unmute_cancels_snoozes_and_reports_counts ... ok
test notification_counts_match_python_priority_rules ... ok
test notification_dismiss_agent_completions_no_op_when_already_dismissed ... ok
test notification_batch_dismiss_and_rewrite_all_update_the_store ... ok
test notification_bulk_mute_deduplicates_ids_and_reports_counts ... ok
test notification_bulk_snooze_uses_one_deadline_and_reports_counts ... ok
test notification_dismiss_matching_agents_covers_custom_gates ... ok
test notification_dismiss_matching_agents_matches_question_child_identity ... ok
test notification_dismiss_agent_completions_matching_agents_is_completion_only ... ok
test notification_json_shape_uses_expected_wire_keys ... ok
test notification_loads_legacy_defaults_and_skips_bad_rows ... ok
test notification_current_read_recovers_legacy_state_and_preserves_cancellations ... ok
test notification_missing_file_returns_empty_snapshot ... ok
test notification_dismiss_matching_agents_covers_user_agent_view_error_report ... ok
test notification_icon_round_trips_through_append_load_and_rewrite ... ok
test notification_expire_snoozes_handles_aware_and_naive_timestamps ... ok
test notification_plus_one_fields_default_and_skip_on_legacy_rows ... ok
test notification_mark_tab_read_uses_general_tab_for_untagged_rows ... ok
test notification_dismiss_agent_completions_matches_user_agent_jump_and_error ... ok
test notification_plus_one_appends_by_id_and_preserves_cursor ... ok
test notification_plus_one_no_match_and_invalid_requests ... ok
test notification_dismissal_cancels_snooze_without_resurfacing ... ok
test notification_dismiss_matching_agents_covers_notification_action_shapes ... ok
test notification_dismiss_matching_agents_matches_question_root_identity ... ok
test notification_mute_and_snooze_follow_python_semantics ... ok
test notification_phase1_contract_fixture_loads_with_expected_counts ... ok
test notification_mark_tab_read_marks_only_unread_target_tab ... ok
test notification_rewrite_counts_returns_metadata_without_rows ... ok
test notification_plus_one_by_key_picks_newest_including_dismissed ... ok
test notification_rewrite_counts_preserves_unseen_rows ... ok
test notification_rewrite_reaps_only_targeted_stale_temp_siblings ... ok
test notification_plus_one_round_trip_and_legacy_jsonl_omits_empty_fields ... ok
test notification_rewrite_counts_produces_byte_identical_jsonl ... ok
test notification_rewrite_all_preserves_unseen_rows ... ok
test notification_upsert_rejects_dedup_key_without_plus_one_note ... ok
test notification_rewrite_preserves_unseen_rows ... ok
test notification_upsert_creates_then_plus_ones_by_dedup_key ... ok
test notification_upsert_supersede_no_match_is_silent ... ok
test notification_plus_one_note_is_capped_at_max_chars ... ok
test notification_tags_round_trip_through_append_load_and_rewrite ... ok
test notification_state_update_counts_skips_returned_snapshot ... ok
test notification_upsert_without_dedup_key_matches_append_bytes ... ok
test notification_upsert_does_not_supersede_when_plus_oning ... ok
test notification_upsert_matches_dismissed_and_snoozed_rows ... ok
test notification_snooze_validation_is_atomic_and_skips_ineligible_targets ... ok
test notification_state_updates_mutate_only_intended_rows ... ok
test notification_snooze_normalizes_offsets_and_projects_earliest_deadline ... ok
test notification_upsert_supersedes_matching_rows_only_on_create ... ok
test notification_plus_one_caps_entries_and_counts_drops ... ok
test notification_concurrent_append_and_expiry_converge_on_one_transition ... ok
test notification_append_plus_upsert_concurrency_preserves_valid_rows ... ok
test notification_append_plus_rewrite_counts_concurrency_preserves_valid_rows ... ok
test notification_append_plus_rewrite_concurrency_preserves_valid_rows ... ok

test result: ok. 57 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.34s

     Running tests/plan_validate_parity.rs (/mnt/poseidon/cargo-target/debug/deps/plan_validate_parity-4d8ddddfd656e5e8)

running 1 test
test plan_validate_matches_python_facade_fixture ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/prompt_stash_store_parity.rs (/mnt/poseidon/cargo-target/debug/deps/prompt_stash_store_parity-663e941d5170ceb6)

running 12 tests
test prompt_stash_cursor_serializes_under_nested_key ... ok
test prompt_stash_json_shape_uses_expected_wire_keys ... ok
test prompt_stash_missing_file_returns_empty_snapshot ... ok
test prompt_stash_legacy_row_defaults_cursor_to_none ... ok
test prompt_stash_append_and_read_round_trip ... ok
test prompt_stash_pop_unknown_ids_is_a_no_op ... ok
test prompt_stash_skips_blank_and_malformed_rows ... ok
test prompt_stash_rewrite_merges_and_preserves_unseen_rows ... ok
test prompt_stash_cursor_survives_append_read_pop_pin_rewrite ... ok
test prompt_stash_pop_removes_only_requested_ids ... ok
test prompt_stash_set_pinned_sets_and_clears_matching_ids ... ok
test prompt_stash_append_plus_pop_concurrency_preserves_valid_rows ... ok

test result: ok. 12 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.21s

     Running tests/python_wire_parity.rs (/mnt/poseidon/cargo-target/debug/deps/python_wire_parity-da5589e9f1861493)

running 10 tests
test agent_meta_clan_field_order_matches_python_wire ... ok
test agent_meta_wait_priority_matches_python_wire_defaulting ... ok
test agent_meta_parent_epic_plan_reference_round_trips ... ok
test bead_task_and_ready_enum_values_match_python_wire_values ... ok
test cleanup_target_parallel_membership_matches_python_wire_defaulting ... ok
test legacy_task_snapshot_deserializes_and_reserializes_as_proc_shape ... ok
test agent_meta_parallel_membership_matches_python_wire_defaulting ... ok
test python_fixture_deserializes_into_rust_type ... ok
test proc_snapshot_json_uses_canonical_proc_keys ... ok
test rust_json_equals_python_fixture ... ok

test result: ok. 10 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/query_evaluator_parity.rs (/mnt/poseidon/cargo-target/debug/deps/query_evaluator_parity-0f03251c7e517e8b)

running 17 tests
test ancestor_walk_avoids_cycles ... ok
test configured_project_name_replaces_directory_key_in_all_query_paths ... ok
test project_query_falls_back_to_directory_key_without_valid_metadata ... ok
test persistent_corpus_reuses_derived_data_across_repeated_evaluations ... ok
test substring_semantics_not_regex ... ok
test persistent_corpus_keeps_ancestor_memo_query_specific ... ok
test batch_evaluation_is_idempotent ... ok
test persistent_corpus_matches_golden_matrix_samples ... ok
test evaluation_matrix_escapes_are_literal ... ok
test batch_and_oneshot_agree ... ok
test evaluation_matrix_property_shorthands ... ok
test evaluation_matrix_quoted_strings ... ok
test evaluation_matrix_boolean_ops ... ok
test evaluation_matrix_status_shorthands ... ok
test evaluation_matrix_error_running_shorthands ... ok
test evaluation_matrix_property_filters ... ok
test explicit_patch_profile_matches_compatibility_golden_matrix ... ok

test result: ok. 17 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.07s

     Running tests/vcs_log_parity.rs (/mnt/poseidon/cargo-target/debug/deps/vcs_log_parity-486544f5735d3aa7)

running 27 tests
test aggregate_empty_returns_empty ... ok
test aggregate_interleaves_by_timestamp_desc ... ok
test aggregate_truncates_to_limit ... ok
test aggregate_tie_break_repo_then_full_id ... ok
test aggregated_commit_wire_round_trips_through_json ... ok
test aggregated_commit_wire_serializes_flat ... ok
test classify_commit_origin_distinguishes_auto_and_legacy_stitch ... ok
test classify_commit_presence_marks_synced_local_and_remote ... ok
test classify_commit_origin_uses_terminal_type_footer ... ok
test classify_commit_types_adds_provenance_concrete_merge_and_patch_labels ... ok
test classify_commit_types_for_commit_uses_parent_ids_for_merge_detection ... ok
test classify_commit_types_supports_legacy_spellings_and_unknown_values ... ok
test classify_commit_types_uses_terminal_footer_and_deduplicates_stitch ... ok
test parse_drops_record_with_bad_timestamp ... ok
test parse_drops_record_with_too_few_fields ... ok
test parse_empty_stream_returns_empty_list ... ok
test parse_legacy_single_commit_defaults_parent_ids ... ok
test parse_multiline_body_preserved ... ok
test parse_octopus_commit_parent_ids ... ok
test parse_root_commit_empty_parent_field ... ok
test parse_single_commit_all_fields ... ok
test parse_stitch_type_footer_sets_stitch_origin ... ok
test parse_strips_newline_git_inserts_between_records ... ok
test parse_trailing_record_separator_yields_no_blank ... ok
test vcs_commit_wire_defaults_presence_to_unknown ... ok
test vcs_log_wire_schema_version_is_four ... ok
test vcs_commit_wire_serializes_to_python_shape ... ok

test result: ok. 27 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running unittests src/lib.rs (/mnt/poseidon/cargo-target/debug/deps/sase_core_rs-1de2d1fefe3bf369)
/mnt/poseidon/cargo-target/debug/deps/sase_core_rs-1de2d1fefe3bf369: error while loading shared libraries: libpython3.14.so.1.0: cannot open shared object file: No such file or directory
error: test failed, to rerun pass `-p sase_core_py --lib`

Caused by:
  process didn't exit successfully: `/mnt/poseidon/cargo-target/debug/deps/sase_core_rs-1de2d1fefe3bf369` (exit status: 127)
note: test exited abnormally; to see the full output pass --no-capture to the harness.
error: recipe `check` failed on line 4 with exit code 127
SASE_YW3_CORE_CHECK_STATUS=127
[validate_sase_core_rs] cannot import sase_core_rs: cannot import name 'sase_core_rs' from partially initialized module 'sase_core_rs' (most likely due to a circular import) (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_core_py/python/sase_core_rs/__init__.py)
[setup] Rebuilding stale or missing sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core before Python dependency resolution.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[sase-core-wheel-cache] miss: no exact cached wheel
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
    Blocking waiting for file lock on build directory
   Compiling pyo3-build-config v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
   Compiling pyo3-macros v0.22.6
   Compiling sase_core_py v0.32.60 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 4m 51s
📦 Built wheel for abi3 Python ≥ 3.12 to /tmp/.tmpHWoqAU/sase_core_rs-0.32.60-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.32.60
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
    Blocking waiting for file lock on build directory
   Compiling pyo3-build-config v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
   Compiling pyo3-macros v0.22.6
   Compiling sase_core_py v0.32.60 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 13m 12s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-wheels/.build-m07vgny1/sase_core_rs-0.32.60-cp312-abi3-manylinux_2_39_x86_64.whl
/home/bryan/.sase/cache/sase-core-wheels/941dbeda306c35f5073e5f9e9a64af5d4d72d5e2131096da32cb19486715634d/sase_core_rs-0.32.60-cp312-abi3-manylinux_2_39_x86_64.whl
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
   Compiling proc-macro2 v1.0.106
   Compiling quote v1.0.45
   Compiling unicode-ident v1.0.24
   Compiling libc v0.2.186
   Compiling cfg-if v1.0.4
   Compiling version_check v0.9.5
   Compiling zerocopy v0.8.48
   Compiling memchr v2.8.0
   Compiling once_cell v1.21.4
   Compiling pin-project-lite v0.2.17
   Compiling serde_core v1.0.228
   Compiling hashbrown v0.17.0
   Compiling zmij v1.0.21
   Compiling serde v1.0.228
   Compiling shlex v1.3.0
   Compiling find-msvc-tools v0.1.9
   Compiling typenum v1.20.0
   Compiling equivalent v1.0.2
   Compiling futures-sink v0.3.32
   Compiling futures-core v0.3.32
   Compiling smallvec v1.15.1
   Compiling regex-syntax v0.8.10
   Compiling autocfg v1.5.0
   Compiling serde_json v1.0.149
   Compiling pkg-config v0.3.33
   Compiling vcpkg v0.2.15
   Compiling itoa v1.0.18
   Compiling getrandom v0.4.2
   Compiling crossbeam-utils v0.8.21
   Compiling bitflags v2.11.1
   Compiling futures-io v0.3.32
   Compiling rustix v1.1.4
   Compiling parking_lot_core v0.9.12
   Compiling futures-task v0.3.32
   Compiling slab v0.4.12
   Compiling bitflags v1.3.2
   Compiling bytes v1.11.1
   Compiling httparse v1.10.1
   Compiling scopeguard v1.2.0
   Compiling thiserror v1.0.69
   Compiling linux-raw-sys v0.12.1
   Compiling sync_wrapper v1.0.2
   Compiling lazy_static v1.5.0
   Compiling ryu v1.0.23
   Compiling fallible-iterator v0.3.0
   Compiling fastrand v2.4.1
   Compiling unsafe-libyaml v0.2.11
   Compiling tower-layer v0.3.3
   Compiling tower-service v0.3.3
   Compiling cpufeatures v0.2.17
   Compiling log v0.4.29
   Compiling fallible-streaming-iterator v0.1.9
   Compiling thread_local v1.1.9
   Compiling unicode-width v0.2.2
   Compiling nu-ansi-term v0.50.3
   Compiling hex v0.4.3
   Compiling futures-channel v0.3.32
   Compiling cc v1.2.61
   Compiling lock_api v0.4.14
   Compiling tracing-core v0.1.36
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling sharded-slab v0.1.7
   Compiling num-traits v0.2.19
   Compiling fluent-uri v0.1.4
   Compiling aho-corasick v1.1.4
   Compiling tracing-log v0.2.0
   Compiling indexmap v2.14.0
   Compiling syn v2.0.117
   Compiling libsqlite3-sys v0.30.1
   Compiling chrono v0.4.44
   Compiling errno v0.3.14
   Compiling getrandom v0.2.17
   Compiling mio v1.2.0
   Compiling socket2 v0.6.3
   Compiling fs2 v0.4.3
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling signal-hook-registry v1.4.8
   Compiling digest v0.10.7
   Compiling rand_core v0.6.4
   Compiling sha2 v0.10.9
   Compiling regex-automata v0.4.14
   Compiling tempfile v3.27.0
   Compiling serde_derive v1.0.228
   Compiling futures-macro v0.3.32
   Compiling tracing-attributes v0.1.31
   Compiling tokio-macros v2.7.0
   Compiling thiserror-impl v1.0.69
   Compiling serde_repr v0.1.20
   Compiling ppv-lite86 v0.2.21
   Compiling hashbrown v0.14.5
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling rand_chacha v0.3.1
   Compiling rand v0.8.6
   Compiling tracing v0.1.44
   Compiling hashlink v0.9.1
   Compiling dashmap v6.1.0
   Compiling matchers v0.2.0
   Compiling regex v1.12.3
   Compiling tracing-subscriber v0.3.23
   Compiling serde_yaml v0.9.34+deprecated
   Compiling lsp-types v0.97.0
   Compiling tower v0.5.3
   Compiling futures v0.3.32
   Compiling tokio-util v0.7.18
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.32.60 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_xprompt_lsp v0.32.60 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_xprompt_lsp)
    Finished `dev-update` profile [optimized] target(s) in 1m 58s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/sase-xprompt-lsp
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-visual              │
└───────────────────────────────────────────────────────┘

---------- Running visual pytest subset... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 7/7 workers
7 workers [905 items]

........................................................................ [  7%]
........................................................................ [ 15%]
........................................................................ [ 23%]
.....................F............................................F..... [ 31%]
.............................F.............................F............ [ 39%]
..........................................F..............F............F. [ 47%]
........................F........F...........F...............F..F....F.. [ 55%]
...............................F.......................F.F...F.....F.... [ 63%]
.....F..FF......................................................F.F.F... [ 71%]
.F..........F.........F.....F........................................... [ 79%]
........F....F...........F..............................F............... [ 87%]
...............F.F......F.........................F..................... [ 95%]
.........................................                                [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________ test_artifacts_agents_filter_parse_error_png_snapshot _____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...facts_agents.py', test_line=319, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2e147ba80>

    async def test_artifacts_agents_filter_parse_error_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        snapshot = _snapshot(_populated_rows())
        _install_agents_fixture(monkeypatch, snapshot)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            pane = await _open_agents(page, snapshot)
            bar = pane.query_one(AgentFilterBar)
            await page.press("slash")
            await page.wait_for(lambda _state: bar._editing)  # noqa: SLF001
            bar.query_one("#agent-filter-input", SingleLineVimTextArea).load_text("status:")
            await page.wait_for(
                lambda _state: bar.query_one("#agent-filter-status").has_class("error")
            )
            status = bar.query_one("#agent-filter-status", Static)
            await page.wait_for(
                lambda _state: "Expected property value" in status.content.plain
            )
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "artifacts_agents_filter_parse_error_120x40",
                title="ACE Artifacts - Agent filter parse error",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_agents.py:341: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_agents_filter_parse_error_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xb1\xa3...x00\x00\x00\x80\xa9\xe7\xd9\xec\xa7\'\xfby,&\xeel\xb6\xc0\xff\x05\x87\x90\x94C\x13A"\xdb\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_agents.py::test_artifacts_agents_filter_parse_error_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1672637057-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_agents.py'
test_line = 319
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/artifacts_agents_filter_parse_error_120x40.png
E       Changed pixels: 26951/1520532 (1.772472%); materially changed pixels: 26896/1520532 (1.768855%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_agents.py__test_artifacts_agents_filter_parse_error_png_snapshot/artifacts_agents_filter_parse_error_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_agents.py__test_artifacts_agents_filter_parse_error_png_snapshot/artifacts_agents_filter_parse_error_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_agents.py__test_artifacts_agents_filter_parse_error_png_snapshot/artifacts_agents_filter_parse_error_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_agents.py__test_artifacts_agents_filter_parse_error_png_snapshot/artifacts_agents_filter_parse_error_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____ test_selected_panel_clan_collapse_precedes_status_group_png_snapshot _____
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...clan_collapse.py', test_line=61, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc537cb5b00>

    async def test_selected_panel_clan_collapse_precedes_status_group_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 22, 9, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_panel_clan_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.press("o", "o")
            assert page.app._grouping_mode is GroupingMode.BY_STATUS
    
            clan = next(
                agent
                for agent in page.app._agents_with_children
                if agent.is_clan_container and agent.agent_clan == "toobig-g"
            )
            clan_key = agent_fold_key(clan)
            assert clan_key is not None
            page.app._fold_manager.expand(clan_key)
            page.app._refilter_agents(refresh_content_index=False)
            clan = next(
                agent
                for agent in page.app._agents
                if agent.is_clan_container and agent.agent_clan == "toobig-g"
            )
            page.app._panel_group.focused_idx = page.app._panel_group.panel_keys.index(
                "chop"
            )
            page.app._collapsed_panel_keys.discard("chop")
            page.app._expanded_panel_keys.add("chop")
            page.app._expanded_panel_focus = False
            page.app.current_idx = page.app._agents.index(clan)
            page.app._current_group_key = None
            page.app._refresh_agents_display(list_changed=True)
            assert page.app._resolve_focused_panel() is None
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            await wait_for_visual_idle(page)
    
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            assert ("H", "collapse fold") in footer._last_layout_inputs[0]
            registry = page.app._group_fold_registry.for_panel("chop")
            assert not registry.is_collapsed(("Running",))
            assert not registry.is_collapsed(("Done",))
            assert page.app._fold_manager.get(clan_key) is FoldLevel.EXPANDED
>           ace_png_visual.assert_page_png(
                page,
                "agents_selected_panel_clan_collapse_120x40",
                title="ACE selected panel clan collapse",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_clan_collapse.py:112: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_selected_panel_clan_collapse_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x021ZIDATx\...!\x84\x10B\xc8\xc8\xe3\xb0\xfe\xc4\xf5\xe7#,\xdc\xe9\xb7\xc3\xff\x02H[;\xc6\x82a\xfd\x0f\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_clan_collapse.py::test_selected_panel_clan_collapse_precedes_status_group_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-1848587317-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_clan_collapse.py'
test_line = 61
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_selected_panel_clan_collapse_120x40.png
E       Changed pixels: 144871/1520532 (9.527652%); materially changed pixels: 144836/1520532 (9.525350%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_clan_collapse.py__test_selected_panel_clan_collapse_precedes_status_group_png_snapshot/agents_selected_panel_clan_collapse_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_clan_collapse.py__test_selected_panel_clan_collapse_precedes_status_group_png_snapshot/agents_selected_panel_clan_collapse_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_clan_collapse.py__test_selected_panel_clan_collapse_precedes_status_group_png_snapshot/agents_selected_panel_clan_collapse_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_clan_collapse.py__test_selected_panel_clan_collapse_precedes_status_group_png_snapshot/agents_selected_panel_clan_collapse_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________ test_runner_slot_wait_rows_and_queue_detail_png_snapshot ___________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...shots_agents.py', test_line=133, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07de07b1c0>

    async def test_runner_slot_wait_rows_and_queue_detail_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 12, 12, 3, 0))
        monkeypatch.setattr("sase.config.core.get_max_running_agents", lambda: 10)
        patch_startup_loaders(monkeypatch, agents=runner_slot_wait_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            await page.press("j")
            await wait_for_visual_idle(page)
            selected = page.app._agents[page.app.current_idx]
            assert selected.status == "QUEUED"
            assert selected.runner_slot_queue_position == 1
            assert selected.runner_slot_queue_size == 2
            assert_page_svg_contains(page, "drain-barrier")
            assert_page_svg_contains(page, "global-cap")
            assert_page_svg_contains(page, "dependency-wait")
            assert_page_svg_contains(page, "Queue:")
            assert_page_svg_contains(page, "of 2")
            assert_page_svg_contains(page, "at the front")
            prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            prompt_text = renderable_to_text(prompt.content) or ""
>           assert "3m in queue" in prompt_text
E           AssertionError: assert '3m in queue' in 'AGENT SHELL\nName: global-cap\nPatch: visual-global-cap\nModel: CLAUDE(sonnet)\nPID: 4101\nQueue: #1 of 2 · at the fr... drain-barrier      ≤0 2m\n\n──────────────────────────────────────────────────\n\nAGENT PROMPT\nNo prompt file found.'

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:162: AssertionError
__________________ test_runner_slot_queue_window_png_snapshot __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...shots_agents.py', test_line=211, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07de8f9160>

    async def test_runner_slot_queue_window_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        rows = runner_slot_queue_window_agents()
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 25, 12, 12, 0))
        monkeypatch.setattr("sase.config.core.get_max_running_agents", lambda: 10)
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 9)
            await wait_for_visual_idle(page)
    
            for _ in range(len(rows) + 1):
                selected = (
                    page.app._agents[page.app.current_idx]
                    if 0 <= page.app.current_idx < len(page.app._agents)
                    else None
                )
                if selected is not None and selected.agent_name == "queue-middle":
                    break
                await page.press("j")
                await wait_for_visual_idle(page)
            selected = page.app._agents[page.app.current_idx]
            assert selected.agent_name == "queue-middle"
            assert selected.runner_slot_queue_position == 6
            prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            prompt_text = renderable_to_text(prompt.content) or ""
            assert "5 ahead" in prompt_text
            assert "QUEUE · 9 waiting · 0/10 runners" in prompt_text
            assert "≤0" in prompt_text
            assert "p1" in prompt_text
            assert "… +2 more" in prompt_text
            assert "… +1 more" in prompt_text
>           ace_png_visual.assert_page_png(
                page,
                "agents_runner_slot_queue_window_120x40",
                title="ACE agents runner slot queue window",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:248: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_runner_slot_queue_window_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x03JFIDATx\...00\x00\x00\x00\x00\x00\xf4?\xed\xc1\xa3-x\xbc\xa1\x8e;\xa3\x06\xf8\xbf\xae.2\n^\x94\xeb(\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...5" y="971.6" textLength="48.8" clip-path="url(#terminal-3140936981-line-39)">kill</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py'
test_line = 211
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_runner_slot_queue_window_120x40.png
E       Changed pixels: 1255/1520532 (0.082537%); materially changed pixels: 1255/1520532 (0.082537%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_queue_window_png_snapshot/agents_runner_slot_queue_window_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_queue_window_png_snapshot/agents_runner_slot_queue_window_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_queue_window_png_snapshot/agents_runner_slot_queue_window_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_queue_window_png_snapshot/agents_runner_slot_queue_window_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________________ test_epic_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...s_clan_panel.py', test_line=147, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07fa93acf0>

    async def test_epic_clan_panel_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 17, 12, 15, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=decorate_clan_panel_sections(
                epic_clan_agents(clan_summary=_EPIC_CLAN_SUMMARY)
            ),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "CLAN")
            assert_page_svg_contains(page, "sase-6n")
            assert_page_svg_contains(page, ".phase-runtime")
            assert_page_svg_contains(page, "Title:")
            assert_page_svg_contains(page, "Rich clan summaries")
            assert_page_svg_contains(page, "Counts:")
            assert_page_svg_contains(page, "phases")
            assert_page_svg_contains(page, "waves")
            assert_page_svg_contains(page, "Page:")
            assert_page_svg_contains(page, "3 agents")
            ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_epic_120x40",
                title="ACE epic clan panel fold level 1",
            )
    
            await page.press("z", "z")
            assert page.app.panel_fold_level.value == "expanded"
            await wait_for_visual_idle(page)
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_epic_level_2_120x40",
                title="ACE epic clan panel fold level 2",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:185: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_panel_epic_level_2_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02R\xb3IDA...00\x00\x00\x00\x00\x00\xa0\xfb\xd9\x1d=Z\xa3\xc7k\xea\xb83i\x80\xff\x1f\xc3\xadG2|T_\xe5\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_epic_clan_panel_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-1743729861-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py'
test_line = 147
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_level_2_120x40.png
E       Changed pixels: 901/1520532 (0.059256%); materially changed pixels: 888/1520532 (0.058401%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_level_2_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_level_2_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_level_2_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_level_2_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________ test_models_panel_runner_limit_action_png_snapshot ______________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac..._modals_cards.py', test_line=94, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8c2b7d97f0>

    async def test_models_panel_runner_limit_action_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
            page.app.push_screen(
                RunnerLimitActionModal(
                    runner_limit_snapshot(), now=FROZEN_NOW, use_chezmoi=True
                )
            )
            await page.expect_modal("RunnerLimitActionModal")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "models_panel_runner_limit_action_120x40",
                title="ACE Launch Control — runner-limit action chooser",
            )

tests/ace/tui/visual/test_ace_png_snapshots_models_panel_modals_cards.py:111: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'models_panel_runner_limit_action_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xe2\x97...84\x10B\x08!\x84\x10B\x08!\xa4\xf5\xc8z[\xda\xdbf\xb0p\xa7+\xc0\x9f\x00\xc0\xe0\xa3@j~BN\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_models_panel_modals_cards.py::test_models_panel_runner_limit_action_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3219221853-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_models_panel_modals_cards.py'
test_line = 94
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/models_panel_runner_limit_action_120x40.png
E       Changed pixels: 4390/1520532 (0.288715%); materially changed pixels: 4321/1520532 (0.284177%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_modals_cards.py__test_models_panel_runner_limit_action_png_snapshot/models_panel_runner_limit_action_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_modals_cards.py__test_models_panel_runner_limit_action_png_snapshot/models_panel_runner_limit_action_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_modals_cards.py__test_models_panel_runner_limit_action_png_snapshot/models_panel_runner_limit_action_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_modals_cards.py__test_models_panel_runner_limit_action_png_snapshot/models_panel_runner_limit_action_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...s_clan_panel.py', test_line=284, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07df063cb0>

    async def test_swarm_clan_panel_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 17, 10, 15, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=decorate_clan_panel_sections(
                clan_tree_agents(clan_summary=_RESEARCH_CLAN_SUMMARY)
            ),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "CLAN")
            assert_page_svg_contains(page, ".family")
            assert_page_svg_contains(page, "RESEARCH PROMPT:")
            assert_page_svg_contains(page, "across every fold level?")
            assert_page_svg_contains(page, "3 agents")
            assert_page_svg_contains(page, "1 family")
            assert_page_svg_contains(page, "--code")
            ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_swarm_120x40",
                title="ACE swarm clan panel fold level 1",
            )
    
            await page.press("z", "z")
            assert page.app.panel_fold_level.value == "expanded"
            await wait_for_visual_idle(page)
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_swarm_level_2_120x40",
                title="ACE swarm clan panel fold level 2",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:319: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_panel_swarm_level_2_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x01\x15...84\x10BH\xff\xe3\x98\xf3\x8a8\xaf\xddH\xdc\xe9\xb5\xc1\xff\x07\xe0\xb2a\xb2\x04\xe4\xd4b\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-2667924045-line-39)">cleanup&#160;(1&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py'
test_line = 284
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_clan_panel_swarm_level_2_120x40.png
E       Changed pixels: 2996/1520532 (0.197036%); materially changed pixels: 2976/1520532 (0.195721%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_level_2_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_level_2_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_level_2_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_level_2_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
________________ test_preview_panel_active_search_png_snapshot _________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...review_panel.py', test_line=277, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8043d875b0>

    async def test_preview_panel_active_search_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        payload = PreviewPayload(
            kind_label="chat",
            icon="◈",
            title="reader-search transcript",
            source_path="/workspace/sase/chats/reader-search.md",
            reference="chat:bbugyi200.athena.reader-search",
            lexer="markdown",
            content=(
                "# Reader Search\n\n"
                "The preview reader searches source text on enter.\n\n"
                "## Matching\n\n"
                "Every reader match is highlighted, while n and N navigate.\n\n"
                "The reader keeps navigation responsive on narrow terminals.\n"
            ),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
            modal = PreviewPanelModal(payload)
            page.app.push_screen(modal)
            await page.expect_modal("PreviewPanelModal")
            await page.press("/")
            for key in "reader":
                await page.press(key)
            await page.press("enter")
            await wait_for_state(
                page,
                lambda: modal._match_lines == (1, 3, 7, 9),  # noqa: SLF001
                description="preview search matches to finish loading",
            )
            # Reopen the prefilled input so the snapshot covers the complete search UI.
            await page.press("/")
            await wait_for_state(
                page,
                lambda: (
                    modal.query_one("#preview-search-input", Input).display
                    and modal.query_one("#preview-search-input", Input).value == "reader"
                ),
                description="preview search input to reopen with its committed query",
            )
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "preview_panel_active_search_120x40",
                title="ACE preview panel - active source search",
            )

tests/ace/tui/visual/test_ace_png_snapshots_preview_panel.py:326: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'preview_panel_active_search_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01y\x8dIDA...0\x00\x00\x00\x00\xd0{\xa6\xa2\xd7x\xf4:\xa9\x81;\x93&\xf8\xaf\x13\xb6}\xff\xbbi\xb8\xe1\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_preview_panel.py::test_preview_panel_active_search_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1903480511-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_preview_panel.py'
test_line = 277
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/preview_panel_active_search_120x40.png
E       Changed pixels: 2861/1520532 (0.188158%); materially changed pixels: 2860/1520532 (0.188092%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_preview_panel.py__test_preview_panel_active_search_png_snapshot/preview_panel_active_search_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_preview_panel.py__test_preview_panel_active_search_png_snapshot/preview_panel_active_search_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_preview_panel.py__test_preview_panel_active_search_png_snapshot/preview_panel_active_search_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_preview_panel.py__test_preview_panel_active_search_png_snapshot/preview_panel_active_search_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
________________ test_config_center_launch_default_png_snapshot ________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...config_launch.py', test_line=89, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa9a7009e80>

    async def test_config_center_launch_default_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        _patch_alias_views(monkeypatch, calm_views)
        monkeypatch.setattr(models_panel, "_now", lambda: FROZEN_NOW)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
            await _open_config_launch(page)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "config_center_launch_default_120x40",
                title="ACE SASE Admin Center — Config Launch child",
            )

tests/ace/tui/visual/test_ace_png_snapshots_config_launch.py:104: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'config_center_launch_default_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02o\x98IDA...\xe5\x00\x00\x00\x00\x00\x00\x00\x00h=S\xd1\xcfX\xf4sZ\x03w&=\xe0\xff\x07\x00\tL89\xc6lz\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_config_launch.py::test_config_center_launch_default_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...xtLength="109.8" clip-path="url(#terminal-996145328-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_config_launch.py'
test_line = 89
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/config_center_launch_default_120x40.png
E       Changed pixels: 1630/1520532 (0.107199%); materially changed pixels: 1616/1520532 (0.106279%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_config_launch.py__test_config_center_launch_default_png_snapshot/config_center_launch_default_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_config_launch.py__test_config_center_launch_default_png_snapshot/config_center_launch_default_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_config_launch.py__test_config_center_launch_default_png_snapshot/config_center_launch_default_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_config_launch.py__test_config_center_launch_default_png_snapshot/config_center_launch_default_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________________ test_axe_lumberjack_tree_png_snapshot _____________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...snapshots_axe.py', test_line=66, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa30194a740>

    async def test_axe_lumberjack_tree_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Lumberjack tree with expanded chops and a bgcmd row below."""
        patch_startup_loaders(monkeypatch, axe_data=axe_lumberjack_tree_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_lumberjack_tree_120x40",
                title="ACE axe lumberjack tree",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe.py:79: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_lumberjack_tree_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xccpIDA...08!\x84\x10B\x08!\x84\x10B\x081\xfb\x18\t\x96\xa1`\xe9#qg\\\x81\xb7\x01}\xa7{k\xa0&:\x90\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_lumberjack_tree_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric... textLength="73.2" clip-path="url(#terminal-4254261217-line-39)">&#160;[✓1]&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py', test_line = 66
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/axe_lumberjack_tree_120x40.png
E       Changed pixels: 3043/1520532 (0.200127%); materially changed pixels: 3043/1520532 (0.200127%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_lumberjack_tree_png_snapshot/axe_lumberjack_tree_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_lumberjack_tree_png_snapshot/axe_lumberjack_tree_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_lumberjack_tree_png_snapshot/axe_lumberjack_tree_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_lumberjack_tree_png_snapshot/axe_lumberjack_tree_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________________ test_axe_chop_overrun_png_snapshot ______________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...napshots_axe.py', test_line=129, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2dcb0ef90>

    async def test_axe_chop_overrun_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The sidebar chips, roll-up chip, PACE column, and advisory line together."""
        patch_startup_loaders(monkeypatch, axe_data=axe_chop_overrun_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await _pin_axe_output_top(page, hide_scrollbar=True)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_chop_overrun_120x40",
                title="ACE axe chop overrun",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe.py:143: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_chop_overrun_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xb7\x01...0\x00\x00\x80\xf5\xe7\xa9\xc1\xcf\xee\xc1\xcf72pg\xd7\x13\xfe\x7f\x83}.\x8b\x18\x8c$\x06\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_chop_overrun_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-2634223678-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py'
test_line = 129
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/axe_chop_overrun_120x40.png
E       Changed pixels: 2989/1520532 (0.196576%); materially changed pixels: 2989/1520532 (0.196576%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_png_snapshot/axe_chop_overrun_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_png_snapshot/axe_chop_overrun_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_png_snapshot/axe_chop_overrun_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_png_snapshot/axe_chop_overrun_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
__________________ test_axe_chop_overrun_narrow_png_snapshot ___________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...napshots_axe.py', test_line=150, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2c4e38750>

    async def test_axe_chop_overrun_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The overrun indicators degrade sanely in the narrow compact layout."""
        patch_startup_loaders(monkeypatch, axe_data=axe_chop_overrun_data())
    
        async with AcePage(query='"visual"', patches=patches(), size=(70, 36)) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await _pin_axe_output_top(page, hide_scrollbar=True)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_chop_overrun_narrow_70x36",
                title="ACE axe chop overrun narrow",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe.py:164: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_chop_overrun_narrow_70x36'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x03h\x00\x00\x03\xa0\x08\x06\x00\x00\x00H\xadU\xe4\x00\x01{oIDATx\x9c\xe...VE\xc6\x8f\x8d\x9f\xf8\xc4\'\x1e\x8b\xde\xf2\xf7\xde\xf81\xff\x01\xcc\xffX\xb3iR\xbb\x04\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_chop_overrun_narrow_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 872 928.4" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich ...tLength="109.8" clip-path="url(#terminal-3300072793-line-35)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py'
test_line = 150
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/axe_chop_overrun_narrow_70x36.png
E       Changed pixels: 27052/809216 (3.342989%); materially changed pixels: 26970/809216 (3.332856%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_narrow_png_snapshot/axe_chop_overrun_narrow_70x36/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_narrow_png_snapshot/axe_chop_overrun_narrow_70x36/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_narrow_png_snapshot/axe_chop_overrun_narrow_70x36/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_narrow_png_snapshot/axe_chop_overrun_narrow_70x36/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________________ test_axe_lumberjack_description_png_snapshot _________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac..._descriptions.py', test_line=23, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2d614fa10>

    async def test_axe_lumberjack_description_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A selected lumberjack keeps its description above scrolling output."""
        patch_startup_loaders(monkeypatch, axe_data=axe_lumberjack_tree_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            page.app._refresh_axe_display()
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_lumberjack_description_120x40",
                title="ACE axe lumberjack description banner",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_descriptions.py:37: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_lumberjack_description_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xd0\xa2...x84\x10B\x08!\x84\x10B\x08!F\x1e\'\xc2\xa5?\\\x0e\x91\xb83n\x85\xf7\x01\xc9a\x15c%3H\x8b\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_descriptions.py::test_axe_lumberjack_description_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric... textLength="73.2" clip-path="url(#terminal-1710613867-line-39)">&#160;[✓1]&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_descriptions.py'
test_line = 23
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/axe_lumberjack_description_120x40.png
E       Changed pixels: 3043/1520532 (0.200127%); materially changed pixels: 3043/1520532 (0.200127%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_descriptions.py__test_axe_lumberjack_description_png_snapshot/axe_lumberjack_description_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_descriptions.py__test_axe_lumberjack_description_png_snapshot/axe_lumberjack_description_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_descriptions.py__test_axe_lumberjack_description_png_snapshot/axe_lumberjack_description_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_descriptions.py__test_axe_lumberjack_description_png_snapshot/axe_lumberjack_description_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_______ test_family_panel_fold_levels_and_member_override_png_snapshots ________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac..._family_panel.py', test_line=34, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07deef5d30>
tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-11/popen-gw0/test_family_panel_fold_levels_0')

    async def test_family_panel_fold_levels_and_member_override_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_family_agents(tmp_path, member_count=3, with_content=True),
        )
    
        async with AcePage(query='"visual-family"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            container = page.app._agents[page.app.current_idx]
            container_identity = container.identity
            assert container.is_family_container_row is True
            assert len(page.app._member_jump_maps[container_identity].targets) == 3
            ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_level_1_120x40",
                title="ACE family panel fold level 1",
            )
    
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                await page.press("ctrl+j")
                if panel.active_section_identity == "agent-xprompt":
                    break
            assert panel.active_section_identity == "agent-xprompt"
            await wait_for_visual_idle(page)
            ace_png_visual.assert_page_png(
                page,
                "agents_family_conversation_level_1_120x40",
                title="ACE family conversation at fold level 1",
            )
    
            await page.press("z", "z")
            assert page.app.panel_fold_level is FoldLevel.FULLY_EXPANDED
            await wait_for_visual_idle(page)
            assert panel.active_section_identity == "agent-xprompt"
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_conversation_level_2_120x40",
                title="ACE family conversation at fold level 2",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py:79: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_conversation_level_2_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02-\x15IDA...10B\x08!\x84\x10B\x08!\x84\x0c=z\xf4+\xa8_\x07\x11\xb8\xd3k\x83\xff\x07\xbav=\x16WZL\x8b\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-3033066951-line-39)">cleanup&#160;(1&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py'
test_line = 34
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_family_conversation_level_2_120x40.png
E       Changed pixels: 287/1520532 (0.018875%); materially changed pixels: 267/1520532 (0.017560%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_conversation_level_2_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_conversation_level_2_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_conversation_level_2_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_conversation_level_2_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_______________ test_models_panel_usage_120_columns_png_snapshot _______________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...s_panel_usage.py', test_line=92, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8c4929e4a0>

    async def test_models_panel_usage_120_columns_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        monkeypatch.setattr(usage_modal, "_now", lambda: FROZEN_NOW)
    
        async with AcePage(query='"visual"', patches=patches(), size=(120, 40)) as page:
            await _open_usage_view(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "models_panel_usage_120x40",
                title="ACE Providers - Usage view at 120 columns",
            )

tests/ace/tui/visual/test_ace_png_snapshots_models_panel_usage.py:102: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'models_panel_usage_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x00\xdc\x8e...f\x04\x00\x00\x00\x00\x00\x0e<wL\xbfvO\xbf\xae\xcf\xc4\x9dc\x0b\xfc\x7f\x80a)X\x1b`\x82p\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_models_panel_usage.py::test_models_panel_usage_120_columns_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...464" y="947.2" textLength="12.2" clip-path="url(#terminal-1569073981-line-38)">\n</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_models_panel_usage.py'
test_line = 92
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/models_panel_usage_120x40.png
E       Changed pixels: 1551/1520532 (0.102004%); materially changed pixels: 1551/1520532 (0.102004%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_usage.py__test_models_panel_usage_120_columns_png_snapshot/models_panel_usage_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_usage.py__test_models_panel_usage_120_columns_png_snapshot/models_panel_usage_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_usage.py__test_models_panel_usage_120_columns_png_snapshot/models_panel_usage_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_usage.py__test_models_panel_usage_120_columns_png_snapshot/models_panel_usage_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________________ test_agents_task_bead_notes_png_snapshot ___________________
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...sase_context.py', test_line=288, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc5318dbe00>
tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-11/popen-gw6/test_agents_task_bead_notes_pn0')

    async def test_agents_task_bead_notes_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        notes = (
            "[2026-08-01T14:03:00Z · alice] Confirmed the notes row belongs "
            "directly under the task description.\n\n"
            "[2026-08-01T14:07:00Z · bob] This second note is intentionally long "
            "enough to wrap in the BEAD lane while keeping attribution readable."
        )
        bead = BeadSummary(
            id="sase-notes.4",
            phase_title="Display persisted bead notes",
            description="Render task metadata without requiring a plan file.",
            actual_plan_path=None,
            display_plan_path=None,
            plan_exists=False,
            plan_readable=False,
            epic_title=None,
            size="medium",
            created_at="2026-07-03T13:00:00Z",
            bead_type="task",
            notes=notes,
        )
        agent = Agent(
            agent_type=AgentType.RUNNING,
            cl_name="visual-task-notes",
            project_file="/workspace/sase/visual_project.sase",
            status="RUNNING",
            start_time=datetime(2026, 8, 1, 14, 0, 0),
            raw_suffix="20260801140000",
            agent_name="sase-notes.4",
            step_type="bash",
            workspace_dir=str(tmp_path),
            llm_provider="codex",
            model="gpt-5",
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.prompt_panel._agent_display_header_summary."
            "resolve_agent_plan_enrichment",
            lambda *_args, **_kwargs: _AgentPlanEnrichment("task", bead, None, ()),
        )
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual-task-notes"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_svg_contains(page, "Notes:")
            await page.press("z", "z")
            await wait_for_svg_contains(page, "alice")
            await wait_for_svg_contains(page, "attribution readable")
            await wait_for_visual_idle(page)
    
            svg_plain = page.export_svg(title="ACE task BEAD notes assertion").replace(
                "&#160;",
                " ",
            )
            assert "Task Title:" in svg_plain
            assert "Description:" in svg_plain
            assert "Notes:" in svg_plain
>           assert "Size:" in svg_plain
E           assert 'Size:' in '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric..." y="971.6" textLength="85.4" clip-path="url(#terminal-61125597-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py:351: AssertionError
____________________ test_family_gate_shells_png_snapshots _____________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...ly_panel_gate.py', test_line=32, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07f4039940>
tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-11/popen-gw0/test_family_gate_shells_png_sn0')

    async def test_family_gate_shells_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_gate_family_agents(tmp_path),
        )
    
        async with AcePage(
            query='"visual-family-root"',
            size=(120, 40),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            container = page.app._agents[page.app.current_idx]
            assert container.is_family_container_row is True
            shells = concrete_family_shell_rows(container)
            assert [shell.is_gate for shell in shells] == [
                False,
                False,
                True,
                True,
                True,
                True,
            ]
            assert [shell.gate_state for shell in shells if shell.is_gate] == [
                "pending",
                "settling",
                "answered",
                "failed",
            ]
            assert_page_svg_contains(page, "Shells:")
            assert_page_svg_contains(page, "pending")
            assert_page_svg_contains(page, "settling")
            assert_page_svg_contains(page, "answered")
            assert_page_svg_contains(page, "failed")
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_shells_gate_120x40",
                title="ACE family panel shell metadata with gate rows",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py:76: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_shells_gate_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x1dUIDA...10B\x08!\x03\x8fS\xfa\x15\xd6\xaf\xbd\x08\xdc\xe9\x95\xe0\x7f\x03\xee{\xd6iq\xa2\x97\x1d\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-3776423625-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py'
test_line = 32
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_gate_120x40.png
E       Changed pixels: 131/1520532 (0.008615%); materially changed pixels: 129/1520532 (0.008484%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________________ test_family_gate_shells_narrow_png_snapshot __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...ly_panel_gate.py', test_line=83, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07deef48a0>
tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-11/popen-gw0/test_family_gate_shells_narrow0')

    async def test_family_gate_shells_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_gate_family_agents(tmp_path),
        )
    
        async with AcePage(
            query='"visual-family-root"',
            size=(90, 40),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "visual-family")
            assert_page_svg_contains(page, "⋔")
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_shells_gate_90x40",
                title="ACE family panel gate shells narrow",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_shells_gate_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x01#BIDATx\x9...0\x00\xb0@\xf8\x9b\x04@!\\\xb6K\xca.Cj\x90\x9bm\x87\xff\x00\x80\x06\xd6\xc7\x87\xeb"\x94\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_narrow_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1116 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-3352958946-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py'
test_line = 83
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_gate_90x40.png
E       Changed pixels: 131/1145016 (0.011441%); materially changed pixels: 129/1145016 (0.011266%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
__________________ test_axe_long_label_widening_png_snapshot ___________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...ts_axe_layout.py', test_line=54, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2d4316970>

    async def test_axe_long_label_widening_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Long lumberjack/chop labels widen the sidebar without wrapping."""
        patch_startup_loaders(monkeypatch, axe_data=axe_long_label_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
    
            sidebar = page.app.query_one("#bgcmd-list-container")
            width = sidebar.styles.width
            assert width is not None, "expected sidebar to have a width set"
            sidebar_width = int(width.value)
            assert sidebar_width > _MIN_BGCMD_LIST_WIDTH, (
                f"expected sidebar to widen past {_MIN_BGCMD_LIST_WIDTH}, "
                f"got {sidebar_width}"
            )
            # The AXE footer repaint can lag the tab change under xdist; settle
            # only the footer so the dashboard golden stays focused on layout.
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            footer.update_axe_bindings(axe_current_view=page.app._axe_current_view)
            await wait_for_state(
                page,
                lambda: _axe_long_label_summary_populated(page),
                description="populated AXE long-label status summary",
            )
            await _pin_axe_output_top(page)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_long_label_widened_120x40",
                title="ACE axe long-label widened sidebar",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py:86: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_long_label_widened_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01[\x95IDA...x00\x00\x13\xcf\xbe\xdam\xa0v\xdb\x1c\x17\xee\x1cm\x87\x7f\x07\x97k\xce\xdd\xbdg\x08\xae\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py::test_axe_long_label_widening_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...6" textLength="73.2" clip-path="url(#terminal-78485834-line-39)">&#160;[✓1]&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py'
test_line = 54
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/axe_long_label_widened_120x40.png
E       Changed pixels: 11748/1520532 (0.772624%); materially changed pixels: 11748/1520532 (0.772624%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_long_label_widening_png_snapshot/axe_long_label_widened_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_long_label_widening_png_snapshot/axe_long_label_widened_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_long_label_widening_png_snapshot/axe_long_label_widened_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_long_label_widening_png_snapshot/axe_long_label_widened_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________ test_family_panel_shells_monitor_metadata_png_snapshot ____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...panel_monitor.py', test_line=33, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07fa8311d0>
tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-11/popen-gw0/test_family_panel_shells_monit0')

    async def test_family_panel_shells_monitor_metadata_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_family_agents(
                tmp_path,
                member_count=2,
                with_content=False,
                with_monitor=True,
                monitor_command=(
                    "just check-full --include visual --include slow "
                    "--include every-family-shell-metadata-case"
                ),
                monitor_reason=(
                    "Full-suite verification before landing the family shell "
                    "metadata renderer"
                ),
            ),
        )
    
        async with AcePage(
            query='"visual-family-root"',
            size=(120, 40),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            container = page.app._agents[page.app.current_idx]
            assert container.is_family_container_row is True
            shells = concrete_family_shell_rows(container)
            assert [shell.is_monitor for shell in shells] == [False, False, True]
            monitor = shells[2]
            assert monitor.parent_timestamp != container.raw_suffix
            jump_map = page.app._member_jump_maps[container.identity]
            assert [target.number for target in jump_map.targets] == ["0", "1", "2"]
            assert jump_map.targets[2].member_identity == monitor.identity
            assert_page_svg_contains(page, "Shells:")
            assert_page_svg_contains(page, "⚙")
            assert_page_svg_contains(page, "why")
            assert_page_svg_contains(page, "Full-suite")
            assert_page_svg_contains(page, "verification")
            assert_page_svg_contains(page, "FAMILY SHELLS")
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_shells_monitor_120x40",
                title="ACE family panel shell metadata with monitor",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:83: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_shells_monitor_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xff\x07...x08!\x84\x90\xe2\xe3\xac\xfe\x04\xf5\xe7\x08\x12w\xba\xad\xf0\xef\xf7\x12J\xe6\x90H2\x13\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-2034667708-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py'
test_line = 33
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_monitor_120x40.png
E       Changed pixels: 99/1520532 (0.006511%); materially changed pixels: 93/1520532 (0.006116%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_______________ test_axe_constrained_width_no_wrap_png_snapshot ________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...ts_axe_layout.py', test_line=93, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2d5e4b380>

    async def test_axe_constrained_width_no_wrap_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Narrow terminal with long labels proves no-wrap + ellipsis behavior."""
        patch_startup_loaders(monkeypatch, axe_data=axe_long_label_data())
    
        # 60x30 is small enough that the sidebar gets clamped to its minimum and
        # the long lumberjack/chop labels can't fit — they must ellipsize on a
        # single line rather than wrap.
        async with AcePage(query='"visual"', patches=patches(), size=(60, 30)) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await wait_for_state(
                page,
                lambda: _axe_long_label_summary_populated(page),
                description="populated AXE long-label status summary",
            )
            await _pin_axe_output_top(page)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_constrained_width_no_wrap_60x30",
                title="ACE axe constrained width no-wrap",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py:115: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_constrained_width_no_wrap_60x30'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x02\xee\x00\x00\x03\x0e\x08\x06\x00\x00\x00A.\x83\xfc\x00\x01\x1buIDATx\...\x1b\x00\x00\x00\x00\x85r0\xb84\x06\x97\xb74\x105j\x81\xff\x1f\xff\xcb\xca\xe2\xbbN\x02.\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py::test_axe_constrained_width_no_wrap_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 750 782.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich ...6" textLength="109.8" clip-path="url(#terminal-952786875-line-29)">start&#160;axe</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py'
test_line = 93
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/axe_constrained_width_no_wrap_60x30.png
E       Changed pixels: 10835/586500 (1.847400%); materially changed pixels: 10834/586500 (1.847229%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_constrained_width_no_wrap_png_snapshot/axe_constrained_width_no_wrap_60x30/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_constrained_width_no_wrap_png_snapshot/axe_constrained_width_no_wrap_60x30/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_constrained_width_no_wrap_png_snapshot/axe_constrained_width_no_wrap_60x30/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_constrained_width_no_wrap_png_snapshot/axe_constrained_width_no_wrap_60x30/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________ test_family_conversation_monitor_phase_png_snapshot ______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...anel_monitor.py', test_line=114, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f080974b380>
tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-11/popen-gw0/test_family_conversation_monit0')

    async def test_family_conversation_monitor_phase_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_family_agents(
                tmp_path,
                member_count=2,
                with_content=False,
                with_monitor=True,
            ),
        )
    
        async with AcePage(query='"visual-family"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            container = page.app._agents[page.app.current_idx]
            assert container.is_family_container_row is True
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                await page.press("ctrl+j")
                if panel.active_section_identity == "agent-reply":
                    break
            assert panel.active_section_identity == "agent-reply"
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "MONITOR")
            assert_page_svg_contains(page, "just check-full")
            panel = page.app.query_one("#agent-list-panel", AgentList)
            assert "⚙1" in Text.from_markup(panel.border_title).plain
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_conversation_monitor_120x40",
                title="ACE family conversation with monitor phase",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:150: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_conversation_monitor_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xe8\xf9...\x00\x00\x00\x00X|\xceG?\x99\xe8\xe7\xb4\x06\xeeLz\xc1\xff\x03\x14\x89n\x0f\x91\x8d\xe7+\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric... y="971.6" textLength="85.4" clip-path="url(#terminal-853941433-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py'
test_line = 114
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_family_conversation_monitor_120x40.png
E       Changed pixels: 99/1520532 (0.006511%); materially changed pixels: 93/1520532 (0.006116%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________________ test_axe_lumberjack_error_png_snapshot ____________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...hots_axe_runs.py', test_line=88, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2dc52d400>

    async def test_axe_lumberjack_error_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Errored lumberjack exercises red/warning styling in tree row + panel."""
        patch_startup_loaders(monkeypatch, axe_data=axe_lumberjack_error_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_lumberjack_error_120x40",
                title="ACE axe lumberjack error",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py:101: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_lumberjack_error_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x012\xf3IDA...a\x00\x00\x00\x00\x00\xe0\xf8\xf3l\xef6\xde\xbb=\x9c\x81;\xdb&\xf8\'-X\x06\xf6$6\xc1\x85\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py::test_axe_lumberjack_error_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3295740626-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py'
test_line = 88
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/axe_lumberjack_error_120x40.png
E       Changed pixels: 31171/1520532 (2.050006%); materially changed pixels: 31158/1520532 (2.049151%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_lumberjack_error_png_snapshot/axe_lumberjack_error_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_lumberjack_error_png_snapshot/axe_lumberjack_error_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_lumberjack_error_png_snapshot/axe_lumberjack_error_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_lumberjack_error_png_snapshot/axe_lumberjack_error_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________ test_agents_fleet_followed_partial_offline_png_snapshot ____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...agents_fleet.py', test_line=190, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07de8a37e0>

    async def test_agents_fleet_followed_partial_offline_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        summary_response, attention_response, follow_snapshot = _fleet_visual_responses()
        facade = OfflineFleetFacade(
            summary_response=summary_response,
            followed_response=summary_response,
            catalog_response=summary_response,
            attention_response=attention_response,
        )
        patch_startup_loaders(monkeypatch, agents=agents())
        _patch_fleet_refresh(
            monkeypatch,
            follow_snapshot=follow_snapshot,
            facade=facade,
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _open_agents(page)
            await _show_fleet(page, expected_count=3)
            await wait_for_visual_idle(page)
    
            assert facade.calls[:3] == ["summary", "followed_batch", "attention"]
            assert "catalog" in facade.calls
            assert_page_svg_contains(page, "★apollo")
            assert_page_svg_contains(page, "☆apollo")
            assert_page_svg_contains(page, "☆mac")
            assert_page_svg_contains(page, "partial")
            assert_page_svg_contains(page, "offline")
            assert_page_svg_contains(page, "cached 12m")
>           ace_png_visual.assert_page_png(
                page,
                "agents_fleet_followed_partial_offline_120x40",
                title="ACE agents Fleet followed partial offline",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py:221: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_fleet_followed_partial_offline_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xca\xbb...0\x00\x00\x00\x00\xc0\xe6s\xcfmY\xb7\xcdj\xe1\xceR\x03>\x01\xba\xeb\x10\xb1\xf6i\x99\xd1\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py::test_agents_fleet_followed_partial_offline_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-2658634363-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py'
test_line = 190
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_fleet_followed_partial_offline_120x40.png
E       Changed pixels: 184/1520532 (0.012101%); materially changed pixels: 174/1520532 (0.011443%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_fleet.py__test_agents_fleet_followed_partial_offline_png_snapshot/agents_fleet_followed_partial_offline_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_fleet.py__test_agents_fleet_followed_partial_offline_png_snapshot/agents_fleet_followed_partial_offline_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_fleet.py__test_agents_fleet_followed_partial_offline_png_snapshot/agents_fleet_followed_partial_offline_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_fleet.py__test_agents_fleet_followed_partial_offline_png_snapshot/agents_fleet_followed_partial_offline_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________ test_agents_fleet_keyboard_focus_and_narrow_png_snapshot ___________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...agents_fleet.py', test_line=228, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07fa6b5550>

    async def test_agents_fleet_keyboard_focus_and_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        summary_response, attention_response, follow_snapshot = _fleet_visual_responses()
        facade = OfflineFleetFacade(
            summary_response=summary_response,
            followed_response=summary_response,
            catalog_response=summary_response,
            attention_response=attention_response,
        )
        patch_startup_loaders(monkeypatch, agents=agents())
        _patch_fleet_refresh(
            monkeypatch,
            follow_snapshot=follow_snapshot,
            facade=facade,
        )
    
        async with AcePage(query='"visual"', patches=patches(), size=(82, 28)) as page:
            await _open_agents(page)
            await _show_fleet(page, expected_count=3)
            page.app.action_view_agent_in_focus()
            await page.wait_for(
                lambda _s: (
                    page.app.current_agents_subtab == "focus"
                    and any(row.fleet_followed for row in page.app._agents)
                )
            )
            await wait_for_visual_idle(page)
    
            assert page.app.current_agents_subtab == "focus"
            assert_page_svg_contains(page, "★apollo")
            assert_page_svg_contains(page, "Focus")
>           ace_png_visual.assert_page_png(
                page,
                "agents_fleet_keyboard_focus_narrow_82x28",
                title="ACE agents Fleet keyboard focus narrow",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py:261: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_fleet_keyboard_focus_narrow_82x28'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x03\xfb\x00\x00\x02\xdd\x08\x06\x00\x00\x00s\xfas\xa5\x00\x01\x94\xa1IDA...7+B\x08!\x84\xe45>\x9f\xefd}}=\xbc\xf8\x9fi%\xff\xb8\xdb1\xff\x1f\xf2\x99/\xf0j\xafy\xc3\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py::test_agents_fleet_keyboard_focus_and_narrow_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1019 733.1999999999999" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generat...="195.2" clip-path="url(#terminal-3129525346-line-27)">cleanup&#160;(3&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py'
test_line = 228
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_fleet_keyboard_focus_narrow_82x28.png
E       Changed pixels: 200/746927 (0.026776%); materially changed pixels: 181/746927 (0.024233%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_fleet.py__test_agents_fleet_keyboard_focus_and_narrow_png_snapshot/agents_fleet_keyboard_focus_narrow_82x28/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_fleet.py__test_agents_fleet_keyboard_focus_and_narrow_png_snapshot/agents_fleet_keyboard_focus_narrow_82x28/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_fleet.py__test_agents_fleet_keyboard_focus_and_narrow_png_snapshot/agents_fleet_keyboard_focus_narrow_82x28/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_fleet.py__test_agents_fleet_keyboard_focus_and_narrow_png_snapshot/agents_fleet_keyboard_focus_narrow_82x28/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________________ test_axe_chop_report_error_png_snapshot ____________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...ots_axe_runs.py', test_line=175, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2c6647f50>

    async def test_axe_chop_report_error_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A check_error run surfaces reason and error in the RESULT card."""
        patch_startup_loaders(monkeypatch, axe_data=axe_chop_report_error_120x40())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            selected = await _select_first_chop(page)
            assert (selected.lumberjack_name, selected.chop_name) == (
                "reports",
                "recent_bug_audit",
            )
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_chop_report_error_120x40",
                title="ACE axe chop report error",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py:189: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_chop_report_error_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x00\xe6\xad...\x00\x00\x00\x00\x80\xe3\xb3\tg\x1d\xce"\xbe\xb8\xf3\xb2\x07~\x02T\xda|\xaf\xf5\x99y\xaa\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py::test_axe_chop_report_error_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3534565456-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py'
test_line = 175
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/axe_chop_report_error_120x40.png
E       Changed pixels: 33298/1520532 (2.189891%); materially changed pixels: 33295/1520532 (2.189694%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_chop_report_error_png_snapshot/axe_chop_report_error_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_chop_report_error_png_snapshot/axe_chop_report_error_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_chop_report_error_png_snapshot/axe_chop_report_error_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_chop_report_error_png_snapshot/axe_chop_report_error_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
________ test_selected_clan_collapses_before_open_sibling_png_snapshot _________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...clan_collapse.py', test_line=84, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07ccaf40c0>

    async def test_selected_clan_collapses_before_open_sibling_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 22, 9, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_group_clan_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.press("o", "o")
            assert page.app._grouping_mode is GroupingMode.BY_STATUS
    
            clans = {
                agent.agent_clan: agent
                for agent in page.app._agents_with_children
                if agent.is_clan_container and agent.agent_clan in {"sase-8k", "sase-8l"}
            }
            selected_clan = clans["sase-8k"]
            sibling_clan = clans["sase-8l"]
            selected_key = agent_fold_key(selected_clan)
            sibling_key = agent_fold_key(sibling_clan)
            assert selected_key is not None and sibling_key is not None
            page.app._fold_manager.expand(selected_key)
            page.app._fold_manager.expand(sibling_key)
            page.app._refilter_agents(refresh_content_index=False)
    
            selected_member = next(
                agent for agent in page.app._agents if agent.cl_name == "sase-8k.plan"
            )
            page.app._panel_group.focused_idx = page.app._panel_group.panel_keys.index(
                "epic"
            )
            page.app._collapsed_panel_keys.discard("epic")
            page.app._expanded_panel_keys.add("epic")
            page.app._expanded_panel_focus = False
            page.app.current_idx = page.app._agents.index(selected_member)
            page.app._current_group_key = None
            page.app._refresh_agents_display(list_changed=True)
            await wait_for_visual_idle(page)
    
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            assert ("H", "collapse clan") in footer._last_layout_inputs[0]
            registry = page.app._group_fold_registry.for_panel("epic")
            assert page.app._fold_manager.get(selected_key) is FoldLevel.EXPANDED
            assert page.app._fold_manager.get(sibling_key) is FoldLevel.EXPANDED
            assert not registry.is_collapsed(("Running",))
    
            await page.press("H")
            await wait_for_visual_idle(page)
    
            selected = page.app._agents[page.app.current_idx]
            assert selected.identity == selected_clan.identity
            assert page.app._fold_manager.get(selected_key) is FoldLevel.COLLAPSED
            assert page.app._fold_manager.get(sibling_key) is FoldLevel.EXPANDED
            assert not registry.is_collapsed(("Running",))
            assert footer._last_layout_inputs is not None
            assert ("H", "collapse clans") in footer._last_layout_inputs[0]
>           ace_png_visual.assert_page_png(
                page,
                "agents_selected_clan_collapse_precedence_120x40",
                title="ACE selected clan collapse before sibling clans",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_group_clan_collapse.py:144: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_selected_clan_collapse_precedence_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\n^IDATx...B\x08!\x84\x90\xd1\xc7q\xfd\x1a\xd6\xaf\xfdH\xdc\xe9\xb7\xc1\xbf\x03\xa7(nFP\x90\xf8\xfb\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_group_clan_collapse.py::test_selected_clan_collapses_before_open_sibling_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-1670966647-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_group_clan_collapse.py'
test_line = 84
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_selected_clan_collapse_precedence_120x40.png
E       Changed pixels: 11754/1520532 (0.773019%); materially changed pixels: 11732/1520532 (0.771572%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_selected_clan_collapses_before_open_sibling_png_snapshot/agents_selected_clan_collapse_precedence_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_selected_clan_collapses_before_open_sibling_png_snapshot/agents_selected_clan_collapse_precedence_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_selected_clan_collapses_before_open_sibling_png_snapshot/agents_selected_clan_collapse_precedence_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_selected_clan_collapses_before_open_sibling_png_snapshot/agents_selected_clan_collapse_precedence_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
__________________ test_tribe_panel_four_level_png_snapshots ___________________
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac..._tribe_panel.py', test_line=355, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc536dd1e10>

    async def test_tribe_panel_four_level_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 15, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_tribe_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            epic_index = page.app._panel_group.panel_keys.index("epic")
            epic_panel = list(page.app.query("AgentList"))[epic_index]
            assert Text.from_markup(epic_panel.border_title).plain == (
                "▲ @epic · 2 [R1 F1]"
            )
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "epic"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
    
            await page.press("=")
            await page.wait_for(
                lambda _screen: (
                    None in page.app._collapsed_panel_keys
                    and page.app._panel_isolation_revert is not None
                )
            )
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "↺")
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            bindings, _mode_label = footer._last_layout_inputs
            assert ("H", "collapse fold") in bindings
            assert ("=", "restore panels") in bindings
            ace_png_visual.assert_page_png(
                page,
                "agents_tribe_panel_isolation_armed_120x40",
                title="ACE tribe panel isolation restore markers",
            )
    
            await page.press("=")
            await page.wait_for(
                lambda _screen: (
                    None not in page.app._collapsed_panel_keys
                    and page.app._panel_isolation_revert is None
                )
            )
            await page.press("h")
            await page.wait_for(lambda _screen: "epic" in page.app._collapsed_panel_keys)
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "TRIBE")
            assert_page_svg_contains(page, "@epic")
            tribe_summary = page.app._focused_tribe_summary()
            assert tribe_summary is not None
            assert tribe_summary.lane_count == 2
            assert_page_svg_contains(page, "lanes")
            assert_page_svg_contains(page, "NEEDS ATTENTION")
            assert page.app._member_jump_maps[("panel", "epic")].targets
            ace_png_visual.assert_page_png(
                page,
                "agents_tribe_panel_level_1_120x40",
                title="ACE tribe panel glance",
            )
    
            await page.press("z", "1")
            assert page.app.panel_fold_level.value == "collapsed"
            assert page.app._member_jump_pending_digit is None
    
            for position, fold_value, snapshot_name, title in (
                (
                    "2",
                    "expanded",
                    "agents_tribe_panel_level_2_120x40",
                    "ACE tribe panel triage",
                ),
                (
                    "3",
                    "fully_expanded",
                    "agents_tribe_panel_level_3_120x40",
                    "ACE tribe panel inspect",
                ),
                (
                    "4",
                    "exhaustive",
                    "agents_tribe_panel_level_4_120x40",
                    "ACE tribe panel forensics",
                ),
            ):
                selected_idx = page.app.current_idx
                await page.press("z", position)
                assert page.app.panel_fold_level.value == fold_value
                assert page.app._member_jump_pending_digit is None
                assert page.app.current_idx == selected_idx
                assert page.app._resolve_focused_panel() is not None
                await wait_for_visual_idle(page)
>               ace_png_visual.assert_page_png(page, snapshot_name, title=title)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py:457: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_tribe_panel_level_2_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xd6\x08...\x00\x00\x00\x80\xab\xcfe\xef\x91\xf0\x1e\'\xb4pg\xd0\x06\xff\x03P\x98\xc8\x8f.\xc6N\xab\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...h="195.2" clip-path="url(#terminal-922010455-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py'
test_line = 355
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_2_120x40.png
E       Changed pixels: 1058/1520532 (0.069581%); materially changed pixels: 1032/1520532 (0.067871%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_tribe_panel.py__test_tribe_panel_four_level_png_snapshots/agents_tribe_panel_level_2_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_tribe_panel.py__test_tribe_panel_four_level_png_snapshots/agents_tribe_panel_level_2_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_tribe_panel.py__test_tribe_panel_four_level_png_snapshots/agents_tribe_panel_level_2_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_tribe_panel.py__test_tribe_panel_four_level_png_snapshots/agents_tribe_panel_level_2_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________________ test_update_panel_pending_png_snapshot ____________________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...update_panel.py', test_line=138, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f3649971a90>

    async def test_update_panel_pending_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Populated rows: core rebuild and manual-steps providers."""
        patch_startup_loaders(monkeypatch)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
    
            option_list = await _push_update_panel(page, _pending_state())
            await wait_for_state(
                page,
                lambda: (
                    option_list.option_count == 3
                    and "e/E" in _option_plain(option_list, 0)
                    and "core rebuild" in _option_plain(option_list, 1)
                    and "needs manual steps" in _option_plain(option_list, 2)
                ),
                description="pending Update panel rows",
            )
            await wait_for_svg_contains(page, "core rebuild")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "update_panel_pending_120x40",
                title="ACE Update panel (pending)",
            )

tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py:164: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'update_panel_pending_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xfc\x16...00\x00\x00\x00\x00\x00\x00\xa0\xfe\xacG\xb7\xe5\xe86\xad\x81;\x93&\xf8g\xde-\x86G\xcfs{!\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py::test_update_panel_pending_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3471882741-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py'
test_line = 138
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/update_panel_pending_120x40.png
E       Changed pixels: 244012/1520532 (16.047804%); materially changed pixels: 229114/1520532 (15.068016%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_pending_png_snapshot/update_panel_pending_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_pending_png_snapshot/update_panel_pending_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_pending_png_snapshot/update_panel_pending_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_pending_png_snapshot/update_panel_pending_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________________ test_update_panel_unchecked_png_snapshot ___________________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...update_panel.py', test_line=171, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f3630fffe00>

    async def test_update_panel_unchecked_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Never-checked evidence still renders three selectable unknown rows."""
        patch_startup_loaders(monkeypatch)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
    
            option_list = await _push_update_panel(page, _unchecked_state())
            await wait_for_state(
                page,
                lambda: (
                    option_list.option_count == 3
                    and "e/E" in _option_plain(option_list, 0)
                    and all(
                        "· not checked yet" in _option_plain(option_list, index)
                        for index in range(3)
                    )
                ),
                description="never-checked Update panel rows",
            )
            await wait_for_svg_contains(page, "never checked")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "update_panel_unchecked_120x40",
                title="ACE Update panel (never checked)",
            )

tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py:199: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'update_panel_unchecked_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xf0EIDA...x00\x00\x80\xd6\xb3\x11\xddV\xa2\xdb\xb4\x06\xeeL\x9a\xe0?\x00\xca\xf6\x9eJ\xdb\x9f+\xe3\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py::test_update_panel_unchecked_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...xtLength="109.8" clip-path="url(#terminal-864792578-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py'
test_line = 171
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/update_panel_unchecked_120x40.png
E       Changed pixels: 189561/1520532 (12.466755%); materially changed pixels: 184696/1520532 (12.146801%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_unchecked_png_snapshot/update_panel_unchecked_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_unchecked_png_snapshot/update_panel_unchecked_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_unchecked_png_snapshot/update_panel_unchecked_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_unchecked_png_snapshot/update_panel_unchecked_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________ test_agents_neighbor_jump_expands_target_panel_png_snapshot __________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...ts_neighbors.py', test_line=238, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07ddf81780>

    async def test_agents_neighbor_jump_expands_target_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        agents = _neighbor_panel_reveal_agents()
        target = agents[1]
        patch_startup_loaders(monkeypatch, agents=agents)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "alpha"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            await page.press("h")
            await page.wait_for(lambda _screen: "alpha" in page.app._collapsed_panel_keys)
            assert page.app._panel_group.panel_keys == [None, "zeta", "alpha"]
            await page.press("J")
            assert page.app._panel_group.focused_key is None
            assert page.app._agents[page.app.current_idx].identity == agents[0].identity
    
            page.app.action_start_sibling_mode()
            await page.wait_for(
                lambda _screen: "alpha" not in page.app._collapsed_panel_keys
            )
            await wait_for_visual_idle(page)
    
            assert page.app._panel_group.panel_keys == [None, "alpha", "zeta"]
            assert page.app._panel_group.focused_key == "alpha"
            assert page.app._agents[page.app.current_idx].identity == target.identity
            target_widget = page.app.query_one("#agent-list-panel-1", AgentList)
            assert target_widget.highlighted is not None
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_neighbor_jump_expanded_panel_120x40",
                title="ACE folded-clan neighbor jump expanded panel",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py:277: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_neighbor_jump_expanded_panel_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02Y>IDATx\...84\x10B\x08!\x84\x10B\x06\x1f\'\xf5\'\xa8?{\x10\xb8\xd3+\xc1\xff\x03[\xcb\xe8\xfd0]u\x19\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_neighbor_jump_expands_target_panel_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...h="195.2" clip-path="url(#terminal-237326837-line-39)">cleanup&#160;(1&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py'
test_line = 238
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_neighbor_jump_expanded_panel_120x40.png
E       Changed pixels: 229774/1520532 (15.111422%); materially changed pixels: 229467/1520532 (15.091231%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_jump_expands_target_panel_png_snapshot/agents_neighbor_jump_expanded_panel_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_jump_expands_target_panel_png_snapshot/agents_neighbor_jump_expanded_panel_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_jump_expands_target_panel_png_snapshot/agents_neighbor_jump_expanded_panel_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_jump_expands_target_panel_png_snapshot/agents_neighbor_jump_expanded_panel_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________ test_agents_lane_neighbors_section_fold_levels_png_snapshots _________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...ts_neighbors.py', test_line=452, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07cef6f070>

    async def test_agents_lane_neighbors_section_fold_levels_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, _LANE_NOW)
        patch_startup_loaders(monkeypatch, agents=_single_lane_neighbor_agents())
    
        async with AcePage(query='"visual"', patches=patches(), size=(160, 50)) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 6)
            lane = next(
                agent
                for agent in page.app._agents
                if agent.agent_name == "visual.lane.plan"
            )
            lane_identity = lane.identity
            page.app.current_idx = page.app._agents.index(lane)
            await wait_for_svg_contains(page, "NEIGHBORS")
            await wait_for_visual_idle(page)
    
            # A startup refresh may replace and reorder the Agent instances while
            # preserving their stable identities. Re-resolve the row after the
            # startup frame settles so the numeric selection cannot drift onto a
            # different lane under contention.
            lane = next(
                agent for agent in page.app._agents if agent.identity == lane_identity
            )
            page.app.current_idx = page.app._agents.index(lane)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].identity == lane_identity
            jump_map = page.app._member_jump_maps[lane.identity]
            assert [target.number for target in jump_map.targets] == ["0", "1", "2"]
            assert {target.role for target in jump_map.targets} == {"neighbor"}
            assert_page_svg_contains(page, "NEIGHBORS")
            assert_page_svg_contains(page, "visual.lane hood")
            assert_page_svg_contains(page, "more neighbors")
    
            ace_png_visual.assert_page_png(
                page,
                "agents_lane_neighbors_section_first_level_160x50",
                title="ACE lane neighbors section first fold level",
            )
    
            await page.press("z", "z")
            assert page.app.panel_fold_level is FoldLevel.EXPANDED
            await wait_for_svg_contains(page, "visual hood")
            await wait_for_visual_idle(page)
    
            expanded_map = page.app._member_jump_maps[lane.identity]
            assert [target.number for target in expanded_map.targets] == list("01234")
            assert_page_svg_contains(page, ".bench")
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_lane_neighbors_section_expanded_160x50",
                title="ACE lane neighbors section expanded",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py:507: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_lane_neighbors_section_expanded_160x50'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x07\xb2\x00\x00\x04\xf6\x08\x06\x00\x00\x00\xaf7\xec\x82\x00\x031;IDATx\...\x08!\x84\x10B\x08\xd1<\x87\xe2\xd7H\xfcz&v`\x1fJ\xdb\xe1\xff\x03\xe2"\xfdz\x90\xbbl\xac\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_lane_neighbors_section_fold_levels_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1970 1270.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-1218152774-line-49)">cleanup&#160;(4&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py'
test_line = 452
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_section_expanded_160x50.png
E       Changed pixels: 1250/2501900 (0.049962%); materially changed pixels: 1250/2501900 (0.049962%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_expanded_160x50/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_expanded_160x50/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_expanded_160x50/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_expanded_160x50/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_artifact_links_panel_needs_reveal_row_png_snapshots[size0-artifact_links_panel_needs_reveal_row_120x40] _
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac..._links_panel.py', test_line=246, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc536dd1e10>
size = (120, 40), snapshot_name = 'artifact_links_panel_needs_reveal_row_120x40'

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "artifact_links_panel_needs_reveal_row_120x40"),
            ((60, 30), "artifact_links_panel_needs_reveal_row_60x30"),
        ],
    )
    async def test_artifact_links_panel_needs_reveal_row_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        size: tuple[int, int],
        snapshot_name: str,
    ) -> None:
>       await _assert_panel_snapshot(
            ace_png_visual=ace_png_visual,
            monkeypatch=monkeypatch,
            size=size,
            snapshot_name=snapshot_name,
            title="ACE artifact links panel needs-reveal row",
            chips=_needs_reveal_chips(),
            wait_text="needs reveal",
            reveal_flags=frozenset({1}),
        )

tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py:259: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py:170: in _assert_panel_snapshot
    ace_png_visual.assert_page_png(page, snapshot_name, title=title)
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifact_links_panel_needs_reveal_row_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x028\x8dIDA...00\x00\x00\x00\xe0\xf63S\xff\\\xaf\x7f^\xca\xc4\x9d\xc3^\xf0\xff\x03RLu\x8f\xfb\xb6z\x1e\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py::test_artifact_links_panel_needs_reveal_row_png_snapshots[size0-artifact_links_panel_needs_reveal_row_120x40]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3774766520-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py'
test_line = 246
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
>           raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
E           AssertionError: Missing ACE PNG snapshot golden: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/artifact_links_panel_needs_reveal_row_120x40.png
E           Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifact_links_panel.py__test_artifact_links_panel_needs_reveal_row_png_snapshots_size0-artifact_links_panel_needs_reveal_row_120x40/artifact_links_panel_needs_reveal_row_120x40/actual.png
E           Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifact_links_panel.py__test_artifact_links_panel_needs_reveal_row_png_snapshots_size0-artifact_links_panel_needs_reveal_row_120x40/artifact_links_panel_needs_reveal_row_120x40/summary.txt
E           Re-run with --sase-update-visual-snapshots to accept this snapshot intentionally.

tests/ace/tui/visual/png_diff.py:234: AssertionError
_ test_artifact_links_panel_needs_reveal_row_png_snapshots[size1-artifact_links_panel_needs_reveal_row_60x30] _
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac..._links_panel.py', test_line=246, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc53630df60>
size = (60, 30), snapshot_name = 'artifact_links_panel_needs_reveal_row_60x30'

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "artifact_links_panel_needs_reveal_row_120x40"),
            ((60, 30), "artifact_links_panel_needs_reveal_row_60x30"),
        ],
    )
    async def test_artifact_links_panel_needs_reveal_row_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        size: tuple[int, int],
        snapshot_name: str,
    ) -> None:
>       await _assert_panel_snapshot(
            ace_png_visual=ace_png_visual,
            monkeypatch=monkeypatch,
            size=size,
            snapshot_name=snapshot_name,
            title="ACE artifact links panel needs-reveal row",
            chips=_needs_reveal_chips(),
            wait_text="needs reveal",
            reveal_flags=frozenset({1}),
        )

tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py:259: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py:170: in _assert_panel_snapshot
    ace_png_visual.assert_page_png(page, snapshot_name, title=title)
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifact_links_panel_needs_reveal_row_60x30'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x02\xee\x00\x00\x03\x0e\x08\x06\x00\x00\x00A.\x83\xfc\x00\x01~WIDATx\x9c...x97\x18\x86a\x18\x86a\x18\x86\xd1.\xaeW_3\xd5\xd7\x04\x0bQc7\xfc\x06\x1b*?W\xd6\xe4:\xad\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py::test_artifact_links_panel_needs_reveal_row_png_snapshots[size1-artifact_links_panel_needs_reveal_row_60x30]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 750 782.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich ...83.2" y="727.6" textLength="24.4" clip-path="url(#terminal-650478770-line-29)">ED</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py'
test_line = 246
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
>           raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
E           AssertionError: Missing ACE PNG snapshot golden: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/visual/snapshots/png/artifact_links_panel_needs_reveal_row_60x30.png
E           Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifact_links_panel.py__test_artifact_links_panel_needs_reveal_row_png_snapshots_size1-artifact_links_panel_needs_reveal_row_60x30/artifact_links_panel_needs_reveal_row_60x30/actual.png
E           Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifact_links_panel.py__test_artifact_links_panel_needs_reveal_row_png_snapshots_size1-artifact_links_panel_needs_reveal_row_60x30/artifact_links_panel_needs_reveal_row_60x30/summary.txt
E           Re-run with --sase-update-visual-snapshots to accept this snapshot intentionally.

tests/ace/tui/visual/png_diff.py:234: AssertionError
_ test_beads_link_reveal_chip_png_snapshots[size0-link_reveal_chip_beads_120x40] _
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...k_reveal_chip.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f07de5411d0>
tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-11/popen-gw0/test_beads_link_reveal_chip_pn0')
size = (120, 40), snapshot_name = 'link_reveal_chip_beads_120x40'

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "link_reveal_chip_beads_120x40"),
            ((60, 30), "link_reveal_chip_beads_60x30"),
        ],
    )
    async def test_beads_link_reveal_chip_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        size: tuple[int, int],
        snapshot_name: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        snapshot = _snapshot(tmp_path)
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.artifacts.beads_pane.load_beads_snapshot",
            lambda _project, **_kwargs: snapshot,
        )
    
        async with AcePage(query='"visual"', patches=patches(), size=size) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("beads"))
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            await page.wait_for(
                lambda _state: getattr(pane, "_project_display_name", None) == "Alpha",
                timeout=15.0,
            )
    
            current = pane_canonical_query(pane)
            page.app._link_reveals["beads"] = make_link_reveal(  # type: ignore[attr-defined]
                pane_id="beads",
                ref="bead:sase-hidden.3",
                origin_source="-status:closed",
                origin_canonical="-status:closed",
                origin_target=None,
                revealed_canonical=current,
            )
            pane._update_static("#beads-info", pane._scope_text())
>           await wait_for_svg_contains(page, "Revealed bead:sase-hidden.3")

tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py:72: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/_ace_png_snapshot_waits.py:56: in wait_for_svg_contains
    await wait_for_state(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f07cf31e5d0>
predicate = <function wait_for_svg_contains.<locals>.<lambda> at 0x7f07c34435e0>
description = "SVG sentinel 'Revealed bead:sase-hidden.3'", timeout = 15.0

    async def wait_for_state(
        page: AcePage,
        predicate: Callable[[], bool],
        *,
        description: str = "visual state predicate",
        timeout: float = 15.0,
    ) -> None:
        """Wait until a semantic visual-state predicate becomes true.
    
        Unlike :func:`wait_for_visual_idle`, this helper proves that the intended
        UI state was reached. Frame convergence alone can accept a stable but
        incorrect frame (for example, the screen behind a modal that has not
        painted yet).
        """
        loop = asyncio.get_running_loop()
        deadline = loop.time() + timeout
    
        while True:
            await page.pause(0)
            if predicate():
                return
            if loop.time() >= deadline:
                last_frame = page.export_svg(title="ACE visual state timeout")
                digest = hashlib.sha256(last_frame.encode()).hexdigest()[:12]
>               raise AssertionError(
                    f"Timed out after {timeout:.2f}s waiting for {description}; "
                    f"last_frame_digest={digest}; last_frame_svg={last_frame!r}"
                )
E               AssertionError: Timed out after 15.00s waiting for SVG sentinel 'Revealed bead:sase-hidden.3'; last_frame_digest=20ef33044e1f; last_frame_svg='<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich https://www.textualize.io -->\n    <style>\n\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Regular"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Regular.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Regular.woff") format("woff");\n        font-style: normal;\n        font-weight: 400;\n    }\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Bold"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Bold.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Bold.woff") format("woff");\n        font-style: bold;\n        font-weight: 700;\n    }\n\n    .terminal-1083259580-matrix {\n        font-family: Fira Code, monospace;\n        font-size: 20px;\n        line-height: 24.4px;\n        font-variant-east-asian: full-width;\n    }\n\n    .terminal-1083259580-title {\n        font-size: 18px;\n        font-weight: bold;\n        font-family: arial;\n    }\n\n    .terminal-1083259580-r1 { fill: #c5c8c6 }\n.terminal-1083259580-r2 { fill: #fffcf0 }\n.terminal-1083259580-r3 { fill: #888888 }\n.terminal-1083259580-r4 { fill: #444444 }\n.terminal-1083259580-r5 { fill: #00d7af;font-weight: bold }\n.terminal-1083259580-r6 { fill: #05adad }\n.terminal-1083259580-r7 { fill: #adaba3 }\n.terminal-1083259580-r8 { fill: #ad5e05;font-weight: bold }\n.terminal-1083259580-r9 { fill: #ad9305;font-weight: bold }\n.terminal-1083259580-r10 { fill: #666666 }\n.terminal-1083259580-r11 { fill: #d787ff }\n.terminal-1083259580-r12 { fill: #d787ff;font-weight: bold }\n.terminal-1083259580-r13 { fill: #3a3a3a }\n.terminal-1083259580-r14 { fill: #fffcf0;font-style: italic; }\n.terminal-1083259580-r15 { fill: #9762b1 }\n.terminal-1083259580-r16 { fill: #ff5f5f;font-weight: bold }\n.terminal-1083259580-r17 { fill: #87d7ff;font-weight: bold }\n.terminal-1083259580-r18 { fill: #d7af5f }\n.terminal-1083259580-r19 { fill: #fffcf0;font-weight: bold }\n.terminal-1083259580-r20 { fill: #1a1a1a;font-weight: bold }\n.terminal-1083259580-r21 { fill: #b1afa7 }\n.terminal-1083259580-r22 { fill: #5f5f87 }\n.terminal-1083259580-r23 { fill: #ff875f }\n.terminal-1083259580-r24 { fill: #ffd700 }\n.terminal-1083259580-r25 { fill: #87d7ff }\n.terminal-1083259580-r26 { fill: #100f0f }\n.terminal-1083259580-r27 { fill: #205ea6 }\n.terminal-1083259580-r28 { fill: #205ea6;font-weight: bold }\n.terminal-1083259580-r29 { fill: #5d5c5a }\n.terminal-1083259580-r30 { fill: #4b4b65 }\n.terminal-1083259580-r31 { fill: #797877 }\n.terminal-1083259580-r32 { fill: #b5b3aa;font-style: italic; }\n.terminal-1083259580-r33 { fill: #ffd700;font-weight: bold }\n.terminal-1083259580-r34 { fill: #c4c5b5 }\n.terminal-1083259580-r35 { fill: #5fd787;font-weight: bold }\n.terminal-1083259580-r36 { fill: #af87ff;font-weight: bold }\n.terminal-1083259580-r37 { fill: #c4c5b5;font-weight: bold }\n.terminal-1083259580-r38 { fill: #494846 }\n    </style>\n\n    <defs>\n    <clipPath id="terminal-1083259580-clip-terminal">\n      <rect x="0" y="0" width="1463.0" height="975.0" />\n    </clipPath>\n    <clipPath id="terminal-1083259580-line-0">\n    <rect x="0" y="1.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-1">\n    <rect x="0" y="25.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-2">\n    <rect x="0" y="50.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-3">\n    <rect x="0" y="74.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-4">\n    <rect x="0" y="99.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-5">\n    <rect x="0" y="123.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-6">\n    <rect x="0" y="147.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-7">\n    <rect x="0" y="172.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-8">\n    <rect x="0" y="196.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-9">\n    <rect x="0" y="221.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-10">\n    <rect x="0" y="245.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-11">\n    <rect x="0" y="269.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-12">\n    <rect x="0" y="294.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-13">\n    <rect x="0" y="318.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-14">\n    <rect x="0" y="343.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-15">\n    <rect x="0" y="367.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-16">\n    <rect x="0" y="391.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-17">\n    <rect x="0" y="416.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-18">\n    <rect x="0" y="440.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-19">\n    <rect x="0" y="465.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-20">\n    <rect x="0" y="489.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-21">\n    <rect x="0" y="513.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-22">\n    <rect x="0" y="538.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-23">\n    <rect x="0" y="562.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-24">\n    <rect x="0" y="587.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-25">\n    <rect x="0" y="611.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-26">\n    <rect x="0" y="635.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-27">\n    <rect x="0" y="660.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-28">\n    <rect x="0" y="684.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-29">\n    <rect x="0" y="709.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-30">\n    <rect x="0" y="733.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-31">\n    <rect x="0" y="757.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-32">\n    <rect x="0" y="782.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-33">\n    <rect x="0" y="806.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-34">\n    <rect x="0" y="831.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-35">\n    <rect x="0" y="855.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-36">\n    <rect x="0" y="879.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-37">\n    <rect x="0" y="904.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-38">\n    <rect x="0" y="928.7" width="1464" height="24.65"/>\n            </clipPath>\n    </defs>\n\n    <rect fill="#292929" stroke="rgba(255,255,255,0.35)" stroke-width="1" x="1" y="1" width="1480" height="1024" rx="8"/><text class="terminal-1083259580-title" fill="#c5c8c6" text-anchor="middle" x="740" y="27">ACE&#160;visual&#160;state&#160;timeout</text>\n            <g transform="translate(26,22)">\n            <circle cx="0" cy="0" r="7" fill="#ff5f57"/>\n            <circle cx="22" cy="0" r="7" fill="#febc2e"/>\n            <circle cx="44" cy="0" r="7" fill="#28c840"/>\n            </g>\n        \n    <g transform="translate(9, 41)" clip-path="url(#terminal-1083259580-clip-terminal)">\n    <rect fill="#282726" x="0" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="12.2" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="24.4" y="1.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="85.4" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="97.6" y="1.5" width="512.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="610" y="1.5" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="817.4" y="1.5" width="524.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1342" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1354.2" y="1.5" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1354.2" y="1.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="25.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="25.9" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="317.2" y="25.9" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="25.9" width="622.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1000.4" y="25.9" width="366" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1366.4" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1378.6" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1403" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1415.2" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="244" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="244" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="292.8" y="50.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="414.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="451.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="50.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="561.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="597.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="634.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="646.6" y="50.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="732" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="768.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="805.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="817.4" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="890.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="927.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="963.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="976" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1049.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1085.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1122.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1134.6" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1207.8" y="50.3" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1378.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1390.8" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1415.2" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1439.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="74.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="73.2" y="74.7" width="1146.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1220" y="74.7" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1415.2" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="99.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="99.1" width="1171.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1207.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1220" y="99.1" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="12.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="48.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="73.2" y="123.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="123.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="231.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="244" y="123.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="353.8" y="123.5" width="829.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1183.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1195.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1207.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1220" y="123.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1329.8" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1390.8" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="147.9" width="1171.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1207.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1220" y="147.9" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="172.3" width="463.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#d787ff" x="463.6" y="172.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="536.8" y="172.3" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="172.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="829.6" y="172.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="890.6" y="172.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="988.2" y="172.3" width="475.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="196.7" width="1439.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="221.1" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="221.1" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="195.2" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="305" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="366" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="536.8" y="245.5" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="658.8" y="245.5" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="707.6" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="245.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="269.9" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="707.6" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="269.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="294.3" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="294.3" width="280.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1049.2" y="294.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1110.2" y="294.3" width="292.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1403" y="294.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="318.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="318.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="318.7" width="268.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="488" y="318.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="585.6" y="318.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="318.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="318.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="109.8" y="343.1" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="256.2" y="343.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="451.4" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="488" y="343.1" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="561.2" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#87d7ff" x="585.6" y="343.1" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="343.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="343.1" width="500.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1268.8" y="343.1" width="183" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="367.5" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="367.5" width="219.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="439.2" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="367.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="536.8" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#ffd75f" x="561.2" y="367.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="658.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="367.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="367.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="391.9" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="391.9" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="391.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="317.2" y="391.9" width="353.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="391.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="391.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="416.3" width="292.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="329.4" y="416.3" width="341.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="416.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="416.3" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="440.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="440.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="244" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="256.2" y="440.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="366" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="378.2" y="440.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="440.7" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="597.8" y="440.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="440.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="440.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="109.8" y="465.1" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="207.4" y="465.1" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="439.2" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="465.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="536.8" y="465.1" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="465.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="465.1" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="489.5" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="489.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="489.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="513.9" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="513.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="513.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="538.3" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="538.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="538.3" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="562.7" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="562.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="562.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="587.1" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="587.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="587.1" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="611.5" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="611.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="611.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="635.9" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="635.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="635.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="660.3" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="660.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="660.3" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="684.7" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="684.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="684.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="709.1" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="709.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="709.1" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="733.5" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="733.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="733.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="757.9" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="757.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="757.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="782.3" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="782.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="782.3" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="806.7" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="806.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="806.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="831.1" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="831.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="831.1" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="855.5" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="855.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="879.9" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="879.9" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="73.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="329.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="390.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="451.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="904.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="549" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="610" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="805.2" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="878.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="939.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1012.6" y="904.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1098" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1159" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1171.2" y="904.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1281" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1342" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1354.2" y="904.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="928.7" width="1464" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="953.1" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="953.1" width="1268.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#44475a" x="1281" y="953.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#f4005f" x="1342" y="953.1" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/>\n    <g class="terminal-1083259580-matrix">\n    <text class="terminal-1083259580-r2" x="12.2" y="20" textLength="12.2" clip-path="url(#terminal-1083259580-line-0)">⭘</text><text class="terminal-1083259580-r2" x="610" y="20" textLength="207.4" clip-path="url(#terminal-1083259580-line-0)">sase&#160;ace&#160;(v0.7.1)</text><text class="terminal-1083259580-r1" x="1464" y="20" textLength="12.2" clip-path="url(#terminal-1083259580-line-0)">\n</text><text class="terminal-1083259580-r3" x="12.2" y="44.4" textLength="97.6" clip-path="url(#terminal-1083259580-line-1)">&#160;Agents&#160;</text><text class="terminal-1083259580-r4" x="109.8" y="44.4" textLength="36.6" clip-path="url(#terminal-1083259580-line-1)">&#160;│&#160;</text><text class="terminal-1083259580-r5" x="146.4" y="44.4" textLength="134.2" clip-path="url(#terminal-1083259580-line-1)">&#160;Artifacts&#160;</text><text class="terminal-1083259580-r4" x="280.6" y="44.4" textLength="36.6" clip-path="url(#terminal-1083259580-line-1)">&#160;│&#160;</text><text class="terminal-1083259580-r3" x="317.2" y="44.4" textLength="61" clip-path="url(#terminal-1083259580-line-1)">&#160;AXE&#160;</text><text class="terminal-1083259580-r6" x="1000.4" y="44.4" textLength="366" clip-path="url(#terminal-1083259580-line-1)">&#160;CODEX(visual-snapshot-model)&#160;</text><text class="terminal-1083259580-r8" x="1378.6" y="44.4" textLength="24.4" clip-path="url(#terminal-1083259580-line-1)">⚑1</text><text class="terminal-1083259580-r9" x="1415.2" y="44.4" textLength="36.6" clip-path="url(#terminal-1083259580-line-1)">✉18</text><text class="terminal-1083259580-r1" x="1464" y="44.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-1)">\n</text><text class="terminal-1083259580-r10" x="244" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;1&#160;</text><text class="terminal-1083259580-r10" x="280.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">⬡</text><text class="terminal-1083259580-r3" x="292.8" y="68.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-2)">&#160;Agent&#160;</text><text class="terminal-1083259580-r4" x="378.2" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r10" x="414.8" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;2&#160;</text><text class="terminal-1083259580-r10" x="451.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">◉</text><text class="terminal-1083259580-r3" x="463.6" y="68.8" textLength="97.6" clip-path="url(#terminal-1083259580-line-2)">&#160;Stitch&#160;</text><text class="terminal-1083259580-r4" x="561.2" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r10" x="597.8" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;3&#160;</text><text class="terminal-1083259580-r10" x="634.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">⎇</text><text class="terminal-1083259580-r3" x="646.6" y="68.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-2)">&#160;Patch&#160;</text><text class="terminal-1083259580-r4" x="732" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r11" x="768.6" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;4&#160;</text><text class="terminal-1083259580-r11" x="805.2" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">◈</text><text class="terminal-1083259580-r12" x="817.4" y="68.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-2)">&#160;BEAD&#160;</text><text class="terminal-1083259580-r4" x="890.6" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r10" x="927.2" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;5&#160;</text><text class="terminal-1083259580-r10" x="963.8" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">✎</text><text class="terminal-1083259580-r3" x="976" y="68.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-2)">&#160;Plan&#160;</text><text class="terminal-1083259580-r4" x="1049.2" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r10" x="1085.8" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;6&#160;</text><text class="terminal-1083259580-r10" x="1122.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">▤</text><text class="terminal-1083259580-r3" x="1134.6" y="68.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-2)">&#160;File&#160;</text><text class="terminal-1083259580-r10" x="1378.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">{</text><text class="terminal-1083259580-r11" x="1390.8" y="68.8" textLength="24.4" clip-path="url(#terminal-1083259580-line-2)">██</text><text class="terminal-1083259580-r13" x="1415.2" y="68.8" textLength="24.4" clip-path="url(#terminal-1083259580-line-2)">██</text><text class="terminal-1083259580-r10" x="1439.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">}</text><text class="terminal-1083259580-r1" x="1464" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">\n</text><text class="terminal-1083259580-r12" x="12.2" y="93.2" textLength="24.4" clip-path="url(#terminal-1083259580-line-3)">▌&#160;</text><text class="terminal-1083259580-r2" x="36.6" y="93.2" textLength="36.6" clip-path="url(#terminal-1083259580-line-3)">◈&#160;&#160;</text><text class="terminal-1083259580-r14" x="73.2" y="93.2" textLength="1146.8" clip-path="url(#terminal-1083259580-line-3)">The&#160;work&#160;SASE&#160;tracks:&#160;plan&#160;and&#160;epic&#160;beads,&#160;the&#160;phases&#160;beneath&#160;them,&#160;and&#160;standalone&#160;task&#160;beads.</text><text class="terminal-1083259580-r15" x="1415.2" y="93.2" textLength="36.6" clip-path="url(#terminal-1083259580-line-3)">▸&#160;D</text><text class="terminal-1083259580-r1" x="1464" y="93.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-3)">\n</text><text class="terminal-1083259580-r11" x="36.6" y="117.6" textLength="1171.2" clip-path="url(#terminal-1083259580-line-4)">┌──────────────────────────────────────────────────────────────────────────────────────────────┐</text><text class="terminal-1083259580-r1" x="1464" y="117.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-4)">\n</text><text class="terminal-1083259580-r12" x="12.2" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">/</text><text class="terminal-1083259580-r11" x="36.6" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">│</text><text class="terminal-1083259580-r16" x="61" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">-</text><text class="terminal-1083259580-r17" x="73.2" y="142" textLength="85.4" clip-path="url(#terminal-1083259580-line-5)">status:</text><text class="terminal-1083259580-r18" x="158.6" y="142" textLength="73.2" clip-path="url(#terminal-1083259580-line-5)">closed</text><text class="terminal-1083259580-r17" x="244" y="142" textLength="73.2" clip-path="url(#terminal-1083259580-line-5)">limit:</text><text class="terminal-1083259580-r18" x="317.2" y="142" textLength="36.6" clip-path="url(#terminal-1083259580-line-5)">100</text><text class="terminal-1083259580-r11" x="1195.6" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">│</text><text class="terminal-1083259580-r19" x="1220" y="142" textLength="109.8" clip-path="url(#terminal-1083259580-line-5)">4&#160;matches</text><text class="terminal-1083259580-r7" x="1329.8" y="142" textLength="61" clip-path="url(#terminal-1083259580-line-5)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r11" x="1390.8" y="142" textLength="61" clip-path="url(#terminal-1083259580-line-5)">exact</text><text class="terminal-1083259580-r1" x="1464" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">\n</text><text class="terminal-1083259580-r11" x="36.6" y="166.4" textLength="1171.2" clip-path="url(#terminal-1083259580-line-6)">└──────────────────────────────────────────────────────────────────────────────────────────────┘</text><text class="terminal-1083259580-r1" x="1464" y="166.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-6)">\n</text><text class="terminal-1083259580-r20" x="463.6" y="190.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-7)">&#160;Bead&#160;</text><text class="terminal-1083259580-r21" x="536.8" y="190.8" textLength="207.4" clip-path="url(#terminal-1083259580-line-7)">&#160;&#160;Project&#160;scope&#160;&#160;</text><text class="terminal-1083259580-r12" x="744.2" y="190.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-7)">&#160;Alpha&#160;</text><text class="terminal-1083259580-r21" x="829.6" y="190.8" textLength="61" clip-path="url(#terminal-1083259580-line-7)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r21" x="890.6" y="190.8" textLength="97.6" clip-path="url(#terminal-1083259580-line-7)">p&#160;change</text><text class="terminal-1083259580-r1" x="1464" y="190.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-7)">\n</text><text class="terminal-1083259580-r1" x="1464" y="215.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-8)">\n</text><text class="terminal-1083259580-r11" x="0" y="239.6" textLength="732" clip-path="url(#terminal-1083259580-line-9)">╭─&#160;Beads&#160;──────────────────────────────────────────────────╮</text><text class="terminal-1083259580-r22" x="732" y="239.6" textLength="732" clip-path="url(#terminal-1083259580-line-9)">╭─&#160;Details&#160;────────────────────────────────────────────────╮</text><text class="terminal-1083259580-r1" x="1464" y="239.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-9)">\n</text><text class="terminal-1083259580-r11" x="0" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">│</text><text class="terminal-1083259580-r11" x="24.4" y="264" textLength="109.8" clip-path="url(#terminal-1083259580-line-10)">2/2&#160;tasks</text><text class="terminal-1083259580-r21" x="134.2" y="264" textLength="61" clip-path="url(#terminal-1083259580-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r23" x="195.2" y="264" textLength="109.8" clip-path="url(#terminal-1083259580-line-10)">0/0&#160;flags</text><text class="terminal-1083259580-r21" x="305" y="264" textLength="61" clip-path="url(#terminal-1083259580-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r24" x="366" y="264" textLength="109.8" clip-path="url(#terminal-1083259580-line-10)">1/1&#160;epics</text><text class="terminal-1083259580-r21" x="475.8" y="264" textLength="61" clip-path="url(#terminal-1083259580-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r25" x="536.8" y="264" textLength="122" clip-path="url(#terminal-1083259580-line-10)">1/2&#160;phases</text><text class="terminal-1083259580-r21" x="658.8" y="264" textLength="48.8" clip-path="url(#terminal-1083259580-line-10)">&#160;&#160;·…</text><text class="terminal-1083259580-r11" x="719.8" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">│</text><text class="terminal-1083259580-r22" x="732" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">│</text><text class="terminal-1083259580-r1" x="1464" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">\n</text><text class="terminal-1083259580-r11" x="0" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">│</text><text class="terminal-1083259580-r11" x="719.8" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">│</text><text class="terminal-1083259580-r22" x="732" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">│</text><text class="terminal-1083259580-r1" x="1464" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">\n</text><text class="terminal-1083259580-r11" x="0" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">│</text><text class="terminal-1083259580-r26" x="12.2" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">▊</text><text class="terminal-1083259580-r27" x="24.4" y="312.8" textLength="683.2" clip-path="url(#terminal-1083259580-line-12)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-1083259580-r27" x="707.6" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">│</text><text class="terminal-1083259580-r22" x="732" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">│</text><text class="terminal-1083259580-r28" x="1049.2" y="312.8" textLength="61" clip-path="url(#terminal-1083259580-line-12)">Beads</text><text class="terminal-1083259580-r22" x="1451.8" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">│</text><text class="terminal-1083259580-r1" x="1464" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">\n</text><text class="terminal-1083259580-r11" x="0" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">│</text><text class="terminal-1083259580-r26" x="12.2" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="337.2" textLength="109.8" clip-path="url(#terminal-1083259580-line-13)">──&#160;Tasks&#160;</text><text class="terminal-1083259580-r29" x="146.4" y="337.2" textLength="73.2" clip-path="url(#terminal-1083259580-line-13)">(2/2)&#160;</text><text class="terminal-1083259580-r12" x="219.6" y="337.2" textLength="268.4" clip-path="url(#terminal-1083259580-line-13)">·&#160;✦&#160;1&#160;awaiting&#160;triage&#160;</text><text class="terminal-1083259580-r30" x="488" y="337.2" textLength="97.6" clip-path="url(#terminal-1083259580-line-13)">────────</text><text class="terminal-1083259580-r27" x="707.6" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">│</text><text class="terminal-1083259580-r22" x="732" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">│</text><text class="terminal-1083259580-r1" x="1464" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">\n</text><text class="terminal-1083259580-r11" x="0" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">│</text><text class="terminal-1083259580-r26" x="12.2" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="361.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-14)">◆&#160;</text><text class="terminal-1083259580-r32" x="61" y="361.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-14)">·&#160;</text><text class="terminal-1083259580-r12" x="85.4" y="361.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-14)">✦&#160;</text><text class="terminal-1083259580-r33" x="109.8" y="361.6" textLength="146.4" clip-path="url(#terminal-1083259580-line-14)">alpha-ready&#160;</text><text class="terminal-1083259580-r34" x="256.2" y="361.6" textLength="195.2" clip-path="url(#terminal-1083259580-line-14)">Ready&#160;for&#160;triage</text><text class="terminal-1083259580-r5" x="475.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">◇</text><text class="terminal-1083259580-r5" x="488" y="361.6" textLength="73.2" clip-path="url(#terminal-1083259580-line-14)">&#160;ready</text><text class="terminal-1083259580-r20" x="585.6" y="361.6" textLength="85.4" clip-path="url(#terminal-1083259580-line-14)">&#160;small…</text><text class="terminal-1083259580-r27" x="707.6" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">│</text><text class="terminal-1083259580-r22" x="732" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">│</text><text class="terminal-1083259580-r2" x="768.6" y="361.6" textLength="500.2" clip-path="url(#terminal-1083259580-line-14)">Select&#160;a&#160;task,&#160;flag,&#160;epic,&#160;or&#160;phase&#160;bead.</text><text class="terminal-1083259580-r22" x="1451.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">│</text><text class="terminal-1083259580-r1" x="1464" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">\n</text><text class="terminal-1083259580-r11" x="0" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">│</text><text class="terminal-1083259580-r26" x="12.2" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="386" textLength="24.4" clip-path="url(#terminal-1083259580-line-15)">◆&#160;</text><text class="terminal-1083259580-r32" x="61" y="386" textLength="24.4" clip-path="url(#terminal-1083259580-line-15)">·&#160;</text><text class="terminal-1083259580-r33" x="85.4" y="386" textLength="134.2" clip-path="url(#terminal-1083259580-line-15)">alpha-open&#160;</text><text class="terminal-1083259580-r34" x="219.6" y="386" textLength="219.6" clip-path="url(#terminal-1083259580-line-15)">Ordinary&#160;follow-up</text><text class="terminal-1083259580-r17" x="463.6" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">○</text><text class="terminal-1083259580-r17" x="475.8" y="386" textLength="61" clip-path="url(#terminal-1083259580-line-15)">&#160;open</text><text class="terminal-1083259580-r20" x="561.2" y="386" textLength="97.6" clip-path="url(#terminal-1083259580-line-15)">&#160;medium&#160;</text><text class="terminal-1083259580-r2" x="658.8" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">…</text><text class="terminal-1083259580-r27" x="707.6" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">│</text><text class="terminal-1083259580-r22" x="732" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">│</text><text class="terminal-1083259580-r1" x="1464" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">\n</text><text class="terminal-1083259580-r11" x="0" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">│</text><text class="terminal-1083259580-r26" x="12.2" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="410.4" textLength="109.8" clip-path="url(#terminal-1083259580-line-16)">──&#160;Flags&#160;</text><text class="terminal-1083259580-r29" x="146.4" y="410.4" textLength="73.2" clip-path="url(#terminal-1083259580-line-16)">(0/0)&#160;</text><text class="terminal-1083259580-r30" x="219.6" y="410.4" textLength="97.6" clip-path="url(#terminal-1083259580-line-16)">────────</text><text class="terminal-1083259580-r27" x="707.6" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">│</text><text class="terminal-1083259580-r22" x="732" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">│</text><text class="terminal-1083259580-r1" x="1464" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">\n</text><text class="terminal-1083259580-r11" x="0" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">│</text><text class="terminal-1083259580-r26" x="12.2" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">▊</text><text class="terminal-1083259580-r29" x="36.6" y="434.8" textLength="292.8" clip-path="url(#terminal-1083259580-line-17)">&#160;&#160;No&#160;matching&#160;flag&#160;beads</text><text class="terminal-1083259580-r27" x="707.6" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">│</text><text class="terminal-1083259580-r22" x="732" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">│</text><text class="terminal-1083259580-r1" x="1464" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">\n</text><text class="terminal-1083259580-r11" x="0" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">│</text><text class="terminal-1083259580-r26" x="12.2" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="459.2" textLength="109.8" clip-path="url(#terminal-1083259580-line-18)">──&#160;Epics&#160;</text><text class="terminal-1083259580-r29" x="146.4" y="459.2" textLength="73.2" clip-path="url(#terminal-1083259580-line-18)">(1/1)&#160;</text><text class="terminal-1083259580-r29" x="219.6" y="459.2" textLength="24.4" clip-path="url(#terminal-1083259580-line-18)">·&#160;</text><text class="terminal-1083259580-r16" x="244" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">⊜</text><text class="terminal-1083259580-r29" x="256.2" y="459.2" textLength="109.8" clip-path="url(#terminal-1083259580-line-18)">&#160;blocked&#160;</text><text class="terminal-1083259580-r35" x="366" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">►</text><text class="terminal-1083259580-r29" x="378.2" y="459.2" textLength="85.4" clip-path="url(#terminal-1083259580-line-18)">&#160;ready&#160;</text><text class="terminal-1083259580-r5" x="463.6" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">▶</text><text class="terminal-1083259580-r29" x="475.8" y="459.2" textLength="122" clip-path="url(#terminal-1083259580-line-18)">&#160;launched&#160;</text><text class="terminal-1083259580-r30" x="597.8" y="459.2" textLength="73.2" clip-path="url(#terminal-1083259580-line-18)">─────…</text><text class="terminal-1083259580-r27" x="707.6" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">│</text><text class="terminal-1083259580-r22" x="732" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">│</text><text class="terminal-1083259580-r1" x="1464" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">\n</text><text class="terminal-1083259580-r11" x="0" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">│</text><text class="terminal-1083259580-r26" x="12.2" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="483.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-19)">▸&#160;</text><text class="terminal-1083259580-r33" x="61" y="483.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-19)">▸&#160;</text><text class="terminal-1083259580-r36" x="85.4" y="483.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-19)">▤&#160;</text><text class="terminal-1083259580-r33" x="109.8" y="483.6" textLength="97.6" clip-path="url(#terminal-1083259580-line-19)">alpha-1&#160;</text><text class="terminal-1083259580-r37" x="207.4" y="483.6" textLength="231.8" clip-path="url(#terminal-1083259580-line-19)">Build&#160;bead&#160;browsing</text><text class="terminal-1083259580-r17" x="463.6" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">○</text><text class="terminal-1083259580-r17" x="475.8" y="483.6" textLength="61" clip-path="url(#terminal-1083259580-line-19)">&#160;open</text><text class="terminal-1083259580-r25" x="536.8" y="483.6" textLength="134.2" clip-path="url(#terminal-1083259580-line-19)">&#160;&#160;1/2&#160;phas…</text><text class="terminal-1083259580-r27" x="707.6" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">│</text><text class="terminal-1083259580-r22" x="732" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">│</text><text class="terminal-1083259580-r1" x="1464" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">\n</text><text class="terminal-1083259580-r11" x="0" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">│</text><text class="terminal-1083259580-r26" x="12.2" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">│</text><text class="terminal-1083259580-r22" x="732" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">│</text><text class="terminal-1083259580-r1" x="1464" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">\n</text><text class="terminal-1083259580-r11" x="0" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">│</text><text class="terminal-1083259580-r26" x="12.2" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">│</text><text class="terminal-1083259580-r22" x="732" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">│</text><text class="terminal-1083259580-r1" x="1464" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">\n</text><text class="terminal-1083259580-r11" x="0" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">│</text><text class="terminal-1083259580-r26" x="12.2" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">│</text><text class="terminal-1083259580-r22" x="732" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">│</text><text class="terminal-1083259580-r1" x="1464" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">\n</text><text class="terminal-1083259580-r11" x="0" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">│</text><text class="terminal-1083259580-r26" x="12.2" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">│</text><text class="terminal-1083259580-r22" x="732" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">│</text><text class="terminal-1083259580-r1" x="1464" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">\n</text><text class="terminal-1083259580-r11" x="0" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">│</text><text class="terminal-1083259580-r26" x="12.2" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">│</text><text class="terminal-1083259580-r22" x="732" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">│</text><text class="terminal-1083259580-r1" x="1464" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">\n</text><text class="terminal-1083259580-r11" x="0" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">│</text><text class="terminal-1083259580-r26" x="12.2" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">│</text><text class="terminal-1083259580-r22" x="732" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">│</text><text class="terminal-1083259580-r1" x="1464" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">\n</text><text class="terminal-1083259580-r11" x="0" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">│</text><text class="terminal-1083259580-r26" x="12.2" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">│</text><text class="terminal-1083259580-r22" x="732" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">│</text><text class="terminal-1083259580-r1" x="1464" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">\n</text><text class="terminal-1083259580-r11" x="0" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">│</text><text class="terminal-1083259580-r26" x="12.2" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">│</text><text class="terminal-1083259580-r22" x="732" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">│</text><text class="terminal-1083259580-r1" x="1464" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">\n</text><text class="terminal-1083259580-r11" x="0" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">│</text><text class="terminal-1083259580-r26" x="12.2" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">│</text><text class="terminal-1083259580-r22" x="732" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">│</text><text class="terminal-1083259580-r1" x="1464" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">\n</text><text class="terminal-1083259580-r11" x="0" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">│</text><text class="terminal-1083259580-r26" x="12.2" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">│</text><text class="terminal-1083259580-r22" x="732" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">│</text><text class="terminal-1083259580-r1" x="1464" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">\n</text><text class="terminal-1083259580-r11" x="0" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">│</text><text class="terminal-1083259580-r26" x="12.2" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">│</text><text class="terminal-1083259580-r22" x="732" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">│</text><text class="terminal-1083259580-r1" x="1464" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">\n</text><text class="terminal-1083259580-r11" x="0" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">│</text><text class="terminal-1083259580-r26" x="12.2" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">│</text><text class="terminal-1083259580-r22" x="732" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">│</text><text class="terminal-1083259580-r1" x="1464" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">\n</text><text class="terminal-1083259580-r11" x="0" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">│</text><text class="terminal-1083259580-r26" x="12.2" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">│</text><text class="terminal-1083259580-r22" x="732" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">│</text><text class="terminal-1083259580-r1" x="1464" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">\n</text><text class="terminal-1083259580-r11" x="0" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">│</text><text class="terminal-1083259580-r26" x="12.2" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">│</text><text class="terminal-1083259580-r22" x="732" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">│</text><text class="terminal-1083259580-r1" x="1464" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">\n</text><text class="terminal-1083259580-r11" x="0" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">│</text><text class="terminal-1083259580-r26" x="12.2" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">│</text><text class="terminal-1083259580-r22" x="732" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">│</text><text class="terminal-1083259580-r1" x="1464" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">\n</text><text class="terminal-1083259580-r11" x="0" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">│</text><text class="terminal-1083259580-r26" x="12.2" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">▊</text><text class="terminal-1083259580-r27" x="24.4" y="874" textLength="683.2" clip-path="url(#terminal-1083259580-line-35)">▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁</text><text class="terminal-1083259580-r27" x="707.6" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">│</text><text class="terminal-1083259580-r22" x="732" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">│</text><text class="terminal-1083259580-r1" x="1464" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">\n</text><text class="terminal-1083259580-r11" x="0" y="898.4" textLength="732" clip-path="url(#terminal-1083259580-line-36)">╰──────────────────────────────────────────────────────────╯</text><text class="terminal-1083259580-r22" x="732" y="898.4" textLength="732" clip-path="url(#terminal-1083259580-line-36)">╰──────────────────────────────────────────────────────────╯</text><text class="terminal-1083259580-r1" x="1464" y="898.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-36)">\n</text><text class="terminal-1083259580-r12" x="0" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">j</text><text class="terminal-1083259580-r21" x="12.2" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;next</text><text class="terminal-1083259580-r21" x="73.2" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="134.2" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">k</text><text class="terminal-1083259580-r21" x="146.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;prev</text><text class="terminal-1083259580-r21" x="207.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="268.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">Enter</text><text class="terminal-1083259580-r21" x="329.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;view</text><text class="terminal-1083259580-r21" x="390.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="451.4" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">f</text><text class="terminal-1083259580-r21" x="463.6" y="922.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-37)">&#160;filter</text><text class="terminal-1083259580-r21" x="549" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="610" y="922.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-37)">Ctrl+J</text><text class="terminal-1083259580-r21" x="683.2" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;more</text><text class="terminal-1083259580-r21" x="744.2" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="805.2" y="922.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-37)">Ctrl+K</text><text class="terminal-1083259580-r21" x="878.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;less</text><text class="terminal-1083259580-r21" x="939.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="1000.4" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">l</text><text class="terminal-1083259580-r21" x="1012.6" y="922.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-37)">&#160;expand</text><text class="terminal-1083259580-r21" x="1098" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="1159" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">h</text><text class="terminal-1083259580-r21" x="1171.2" y="922.8" textLength="109.8" clip-path="url(#terminal-1083259580-line-37)">&#160;collapse</text><text class="terminal-1083259580-r21" x="1281" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="1342" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">R</text><text class="terminal-1083259580-r21" x="1354.2" y="922.8" textLength="97.6" clip-path="url(#terminal-1083259580-line-37)">&#160;refresh</text><text class="terminal-1083259580-r1" x="1464" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">\n</text><text class="terminal-1083259580-r38" x="0" y="947.2" textLength="1464" clip-path="url(#terminal-1083259580-line-38)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-1083259580-r1" x="1464" y="947.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-38)">\n</text><text class="terminal-1083259580-r37" x="1281" y="971.6" textLength="61" clip-path="url(#terminal-1083259580-line-39)">&#160;AXE&#160;</text><text class="terminal-1083259580-r37" x="1342" y="971.6" textLength="109.8" clip-path="url(#terminal-1083259580-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/_ace_png_snapshot_waits.py:42: AssertionError
_ test_beads_link_reveal_chip_png_snapshots[size1-link_reveal_chip_beads_60x30] _
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac...k_reveal_chip.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f080191c130>
tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-11/popen-gw0/test_beads_link_reveal_chip_pn1')
size = (60, 30), snapshot_name = 'link_reveal_chip_beads_60x30'

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "link_reveal_chip_beads_120x40"),
            ((60, 30), "link_reveal_chip_beads_60x30"),
        ],
    )
    async def test_beads_link_reveal_chip_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        size: tuple[int, int],
        snapshot_name: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        snapshot = _snapshot(tmp_path)
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.artifacts.beads_pane.load_beads_snapshot",
            lambda _project, **_kwargs: snapshot,
        )
    
        async with AcePage(query='"visual"', patches=patches(), size=size) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("beads"))
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            await page.wait_for(
                lambda _state: getattr(pane, "_project_display_name", None) == "Alpha",
                timeout=15.0,
            )
    
            current = pane_canonical_query(pane)
            page.app._link_reveals["beads"] = make_link_reveal(  # type: ignore[attr-defined]
                pane_id="beads",
                ref="bead:sase-hidden.3",
                origin_source="-status:closed",
                origin_canonical="-status:closed",
                origin_target=None,
                revealed_canonical=current,
            )
            pane._update_static("#beads-info", pane._scope_text())
>           await wait_for_svg_contains(page, "Revealed bead:sase-hidden.3")

tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py:72: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/_ace_png_snapshot_waits.py:56: in wait_for_svg_contains
    await wait_for_state(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f07dc7a8950>
predicate = <function wait_for_svg_contains.<locals>.<lambda> at 0x7f07cf997110>
description = "SVG sentinel 'Revealed bead:sase-hidden.3'", timeout = 15.0

    async def wait_for_state(
        page: AcePage,
        predicate: Callable[[], bool],
        *,
        description: str = "visual state predicate",
        timeout: float = 15.0,
    ) -> None:
        """Wait until a semantic visual-state predicate becomes true.
    
        Unlike :func:`wait_for_visual_idle`, this helper proves that the intended
        UI state was reached. Frame convergence alone can accept a stable but
        incorrect frame (for example, the screen behind a modal that has not
        painted yet).
        """
        loop = asyncio.get_running_loop()
        deadline = loop.time() + timeout
    
        while True:
            await page.pause(0)
            if predicate():
                return
            if loop.time() >= deadline:
                last_frame = page.export_svg(title="ACE visual state timeout")
                digest = hashlib.sha256(last_frame.encode()).hexdigest()[:12]
>               raise AssertionError(
                    f"Timed out after {timeout:.2f}s waiting for {description}; "
                    f"last_frame_digest={digest}; last_frame_svg={last_frame!r}"
                )
E               AssertionError: Timed out after 15.00s waiting for SVG sentinel 'Revealed bead:sase-hidden.3'; last_frame_digest=00824c895556; last_frame_svg='<svg class="rich-terminal" viewBox="0 0 750 782.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich https://www.textualize.io -->\n    <style>\n\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Regular"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Regular.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Regular.woff") format("woff");\n        font-style: normal;\n        font-weight: 400;\n    }\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Bold"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Bold.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Bold.woff") format("woff");\n        font-style: bold;\n        font-weight: 700;\n    }\n\n    .terminal-1526668734-matrix {\n        font-family: Fira Code, monospace;\n        font-size: 20px;\n        line-height: 24.4px;\n        font-variant-east-asian: full-width;\n    }\n\n    .terminal-1526668734-title {\n        font-size: 18px;\n        font-weight: bold;\n        font-family: arial;\n    }\n\n    .terminal-1526668734-r1 { fill: #c5c8c6 }\n.terminal-1526668734-r2 { fill: #fffcf0 }\n.terminal-1526668734-r3 { fill: #888888 }\n.terminal-1526668734-r4 { fill: #444444 }\n.terminal-1526668734-r5 { fill: #05adad }\n.terminal-1526668734-r6 { fill: #adaba3 }\n.terminal-1526668734-r7 { fill: #ad5e05;font-weight: bold }\n.terminal-1526668734-r8 { fill: #ad9305;font-weight: bold }\n.terminal-1526668734-r9 { fill: #666666 }\n.terminal-1526668734-r10 { fill: #d787ff }\n.terminal-1526668734-r11 { fill: #d787ff;font-weight: bold }\n.terminal-1526668734-r12 { fill: #3a3a3a }\n.terminal-1526668734-r13 { fill: #fffcf0;font-style: italic; }\n.terminal-1526668734-r14 { fill: #ff5f5f;font-weight: bold }\n.terminal-1526668734-r15 { fill: #87d7ff;font-weight: bold }\n.terminal-1526668734-r16 { fill: #d7af5f }\n.terminal-1526668734-r17 { fill: #fffcf0;font-weight: bold }\n.terminal-1526668734-r18 { fill: #1a1a1a;font-weight: bold }\n.terminal-1526668734-r19 { fill: #b1afa7 }\n.terminal-1526668734-r20 { fill: #5f5f87 }\n.terminal-1526668734-r21 { fill: #ff875f }\n.terminal-1526668734-r22 { fill: #ffd700 }\n.terminal-1526668734-r23 { fill: #100f0f }\n.terminal-1526668734-r24 { fill: #205ea6 }\n.terminal-1526668734-r25 { fill: #205ea6;font-weight: bold }\n.terminal-1526668734-r26 { fill: #5d5c5a }\n.terminal-1526668734-r27 { fill: #b5b3aa;font-style: italic; }\n.terminal-1526668734-r28 { fill: #ffd700;font-weight: bold }\n.terminal-1526668734-r29 { fill: #c4c5b5 }\n.terminal-1526668734-r30 { fill: #4b4b65 }\n.terminal-1526668734-r31 { fill: #797877 }\n.terminal-1526668734-r32 { fill: #5fd787;font-weight: bold }\n.terminal-1526668734-r33 { fill: #00d7af;font-weight: bold }\n.terminal-1526668734-r34 { fill: #af87ff;font-weight: bold }\n.terminal-1526668734-r35 { fill: #c4c5b5;font-weight: bold }\n.terminal-1526668734-r36 { fill: #494846 }\n    </style>\n\n    <defs>\n    <clipPath id="terminal-1526668734-clip-terminal">\n      <rect x="0" y="0" width="731.0" height="731.0" />\n    </clipPath>\n    <clipPath id="terminal-1526668734-line-0">\n    <rect x="0" y="1.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-1">\n    <rect x="0" y="25.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-2">\n    <rect x="0" y="50.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-3">\n    <rect x="0" y="74.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-4">\n    <rect x="0" y="99.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-5">\n    <rect x="0" y="123.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-6">\n    <rect x="0" y="147.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-7">\n    <rect x="0" y="172.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-8">\n    <rect x="0" y="196.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-9">\n    <rect x="0" y="221.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-10">\n    <rect x="0" y="245.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-11">\n    <rect x="0" y="269.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-12">\n    <rect x="0" y="294.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-13">\n    <rect x="0" y="318.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-14">\n    <rect x="0" y="343.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-15">\n    <rect x="0" y="367.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-16">\n    <rect x="0" y="391.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-17">\n    <rect x="0" y="416.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-18">\n    <rect x="0" y="440.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-19">\n    <rect x="0" y="465.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-20">\n    <rect x="0" y="489.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-21">\n    <rect x="0" y="513.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-22">\n    <rect x="0" y="538.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-23">\n    <rect x="0" y="562.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-24">\n    <rect x="0" y="587.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-25">\n    <rect x="0" y="611.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-26">\n    <rect x="0" y="635.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-27">\n    <rect x="0" y="660.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-28">\n    <rect x="0" y="684.7" width="732" height="24.65"/>\n            </clipPath>\n    </defs>\n\n    <rect fill="#292929" stroke="rgba(255,255,255,0.35)" stroke-width="1" x="1" y="1" width="748" height="780" rx="8"/><text class="terminal-1526668734-title" fill="#c5c8c6" text-anchor="middle" x="374" y="27">ACE&#160;visual&#160;state&#160;timeout</text>\n            <g transform="translate(26,22)">\n            <circle cx="0" cy="0" r="7" fill="#ff5f57"/>\n            <circle cx="22" cy="0" r="7" fill="#febc2e"/>\n            <circle cx="44" cy="0" r="7" fill="#28c840"/>\n            </g>\n        \n    <g transform="translate(9, 41)" clip-path="url(#terminal-1526668734-clip-terminal)">\n    <rect fill="#282726" x="0" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="12.2" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="24.4" y="1.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="85.4" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="97.6" y="1.5" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="244" y="1.5" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="451.4" y="1.5" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="610" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="622.2" y="1.5" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="622.2" y="1.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="25.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="25.9" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="268.4" y="25.9" width="366" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="646.6" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="671" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="683.2" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="195.2" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="219.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="231.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="244" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="292.8" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="317.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="329.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="341.6" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="366" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="50.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="439.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="451.4" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="488" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="500.2" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="536.8" y="50.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="646.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="658.8" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="707.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="719.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="74.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="73.2" y="74.7" width="646.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="719.8" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="99.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="99.1" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="475.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="488" y="99.1" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="12.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="48.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="73.2" y="123.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="123.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="231.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="244" y="123.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="353.8" y="123.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="451.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="463.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="475.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="488" y="123.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="597.8" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="658.8" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="147.9" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="475.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="488" y="147.9" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="172.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#d787ff" x="97.6" y="172.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="170.8" y="172.3" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="172.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="172.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="172.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="622.2" y="172.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="196.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="719.8" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="221.1" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="221.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="195.2" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="305" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="366" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="245.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="245.5" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="269.9" width="488" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="269.9" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="294.3" width="488" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="585.6" y="294.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="646.6" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="671" y="294.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="318.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="318.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="318.7" width="256.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="318.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="318.7" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="109.8" y="343.1" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="256.2" y="343.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="451.4" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="343.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="343.1" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="671" y="343.1" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="367.5" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="367.5" width="219.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="439.2" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="367.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="367.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="367.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="391.9" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="391.9" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="391.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="317.2" y="391.9" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="391.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="391.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="391.9" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="391.9" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="416.3" width="292.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="329.4" y="416.3" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="416.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="416.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="416.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="671" y="416.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="440.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="440.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="244" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="256.2" y="440.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="366" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="378.2" y="440.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="440.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="440.7" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="440.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="109.8" y="465.1" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="207.4" y="465.1" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="439.2" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="465.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="465.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="465.1" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="489.5" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="489.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="489.5" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="513.9" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="513.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="513.9" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="538.3" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="538.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="538.3" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="562.7" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="562.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="562.7" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="587.1" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="587.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="587.1" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="611.5" width="488" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="611.5" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="635.9" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="635.9" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="73.2" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="329.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="390.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="451.4" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="660.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="549" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="610" y="660.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="660.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="684.7" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="709.1" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="709.1" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#44475a" x="549" y="709.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#f4005f" x="610" y="709.1" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="719.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/>\n    <g class="terminal-1526668734-matrix">\n    <text class="terminal-1526668734-r2" x="12.2" y="20" textLength="12.2" clip-path="url(#terminal-1526668734-line-0)">⭘</text><text class="terminal-1526668734-r2" x="244" y="20" textLength="207.4" clip-path="url(#terminal-1526668734-line-0)">sase&#160;ace&#160;(v0.7.1)</text><text class="terminal-1526668734-r1" x="732" y="20" textLength="12.2" clip-path="url(#terminal-1526668734-line-0)">\n</text><text class="terminal-1526668734-r3" x="12.2" y="44.4" textLength="97.6" clip-path="url(#terminal-1526668734-line-1)">&#160;Agents&#160;</text><text class="terminal-1526668734-r4" x="109.8" y="44.4" textLength="24.4" clip-path="url(#terminal-1526668734-line-1)">&#160;│</text><text class="terminal-1526668734-r5" x="268.4" y="44.4" textLength="366" clip-path="url(#terminal-1526668734-line-1)">&#160;CODEX(visual-snapshot-model)&#160;</text><text class="terminal-1526668734-r7" x="646.6" y="44.4" textLength="24.4" clip-path="url(#terminal-1526668734-line-1)">⚑1</text><text class="terminal-1526668734-r8" x="683.2" y="44.4" textLength="36.6" clip-path="url(#terminal-1526668734-line-1)">✉18</text><text class="terminal-1526668734-r1" x="732" y="44.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-1)">\n</text><text class="terminal-1526668734-r9" x="195.2" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">1&#160;</text><text class="terminal-1526668734-r9" x="219.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">⬡</text><text class="terminal-1526668734-r4" x="231.8" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r9" x="244" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">2&#160;</text><text class="terminal-1526668734-r9" x="268.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">◉</text><text class="terminal-1526668734-r4" x="280.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r9" x="292.8" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">3&#160;</text><text class="terminal-1526668734-r9" x="317.2" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">⎇</text><text class="terminal-1526668734-r4" x="329.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r10" x="341.6" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">4&#160;</text><text class="terminal-1526668734-r10" x="366" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">◈</text><text class="terminal-1526668734-r11" x="378.2" y="68.8" textLength="61" clip-path="url(#terminal-1526668734-line-2)">&#160;BEAD</text><text class="terminal-1526668734-r4" x="439.2" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r9" x="451.4" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">5&#160;</text><text class="terminal-1526668734-r9" x="475.8" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">✎</text><text class="terminal-1526668734-r4" x="488" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r9" x="500.2" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">6&#160;</text><text class="terminal-1526668734-r9" x="524.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">▤</text><text class="terminal-1526668734-r9" x="646.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">{</text><text class="terminal-1526668734-r10" x="658.8" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">██</text><text class="terminal-1526668734-r12" x="683.2" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">██</text><text class="terminal-1526668734-r9" x="707.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">}</text><text class="terminal-1526668734-r1" x="732" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">\n</text><text class="terminal-1526668734-r11" x="12.2" y="93.2" textLength="24.4" clip-path="url(#terminal-1526668734-line-3)">▌&#160;</text><text class="terminal-1526668734-r2" x="36.6" y="93.2" textLength="36.6" clip-path="url(#terminal-1526668734-line-3)">◈&#160;&#160;</text><text class="terminal-1526668734-r13" x="73.2" y="93.2" textLength="646.6" clip-path="url(#terminal-1526668734-line-3)">The&#160;work&#160;SASE&#160;tracks:&#160;plan&#160;and&#160;epic&#160;beads,&#160;the&#160;phase…</text><text class="terminal-1526668734-r1" x="732" y="93.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-3)">\n</text><text class="terminal-1526668734-r10" x="36.6" y="117.6" textLength="439.2" clip-path="url(#terminal-1526668734-line-4)">┌──────────────────────────────────┐</text><text class="terminal-1526668734-r1" x="732" y="117.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-4)">\n</text><text class="terminal-1526668734-r11" x="12.2" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">/</text><text class="terminal-1526668734-r10" x="36.6" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">│</text><text class="terminal-1526668734-r14" x="61" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">-</text><text class="terminal-1526668734-r15" x="73.2" y="142" textLength="85.4" clip-path="url(#terminal-1526668734-line-5)">status:</text><text class="terminal-1526668734-r16" x="158.6" y="142" textLength="73.2" clip-path="url(#terminal-1526668734-line-5)">closed</text><text class="terminal-1526668734-r15" x="244" y="142" textLength="73.2" clip-path="url(#terminal-1526668734-line-5)">limit:</text><text class="terminal-1526668734-r16" x="317.2" y="142" textLength="36.6" clip-path="url(#terminal-1526668734-line-5)">100</text><text class="terminal-1526668734-r10" x="463.6" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">│</text><text class="terminal-1526668734-r17" x="488" y="142" textLength="109.8" clip-path="url(#terminal-1526668734-line-5)">4&#160;matches</text><text class="terminal-1526668734-r6" x="597.8" y="142" textLength="61" clip-path="url(#terminal-1526668734-line-5)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r10" x="658.8" y="142" textLength="61" clip-path="url(#terminal-1526668734-line-5)">exact</text><text class="terminal-1526668734-r1" x="732" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">\n</text><text class="terminal-1526668734-r10" x="36.6" y="166.4" textLength="439.2" clip-path="url(#terminal-1526668734-line-6)">└──────────────────────────────────┘</text><text class="terminal-1526668734-r1" x="732" y="166.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-6)">\n</text><text class="terminal-1526668734-r18" x="97.6" y="190.8" textLength="73.2" clip-path="url(#terminal-1526668734-line-7)">&#160;Bead&#160;</text><text class="terminal-1526668734-r19" x="170.8" y="190.8" textLength="207.4" clip-path="url(#terminal-1526668734-line-7)">&#160;&#160;Project&#160;scope&#160;&#160;</text><text class="terminal-1526668734-r11" x="378.2" y="190.8" textLength="85.4" clip-path="url(#terminal-1526668734-line-7)">&#160;Alpha&#160;</text><text class="terminal-1526668734-r19" x="463.6" y="190.8" textLength="61" clip-path="url(#terminal-1526668734-line-7)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r19" x="524.6" y="190.8" textLength="97.6" clip-path="url(#terminal-1526668734-line-7)">p&#160;change</text><text class="terminal-1526668734-r1" x="732" y="190.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-7)">\n</text><text class="terminal-1526668734-r1" x="732" y="215.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-8)">\n</text><text class="terminal-1526668734-r10" x="0" y="239.6" textLength="536.8" clip-path="url(#terminal-1526668734-line-9)">╭─&#160;Beads&#160;──────────────────────────────────╮</text><text class="terminal-1526668734-r20" x="536.8" y="239.6" textLength="195.2" clip-path="url(#terminal-1526668734-line-9)">╭─&#160;Details&#160;────╮</text><text class="terminal-1526668734-r1" x="732" y="239.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-9)">\n</text><text class="terminal-1526668734-r10" x="0" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">│</text><text class="terminal-1526668734-r10" x="24.4" y="264" textLength="109.8" clip-path="url(#terminal-1526668734-line-10)">2/2&#160;tasks</text><text class="terminal-1526668734-r19" x="134.2" y="264" textLength="61" clip-path="url(#terminal-1526668734-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r21" x="195.2" y="264" textLength="109.8" clip-path="url(#terminal-1526668734-line-10)">0/0&#160;flags</text><text class="terminal-1526668734-r19" x="305" y="264" textLength="61" clip-path="url(#terminal-1526668734-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r22" x="366" y="264" textLength="109.8" clip-path="url(#terminal-1526668734-line-10)">1/1&#160;epics</text><text class="terminal-1526668734-r19" x="475.8" y="264" textLength="36.6" clip-path="url(#terminal-1526668734-line-10)">&#160;&#160;…</text><text class="terminal-1526668734-r10" x="524.6" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">│</text><text class="terminal-1526668734-r20" x="536.8" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">│</text><text class="terminal-1526668734-r20" x="719.8" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">│</text><text class="terminal-1526668734-r1" x="732" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">\n</text><text class="terminal-1526668734-r10" x="0" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">│</text><text class="terminal-1526668734-r10" x="524.6" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">│</text><text class="terminal-1526668734-r20" x="536.8" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">│</text><text class="terminal-1526668734-r20" x="719.8" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">│</text><text class="terminal-1526668734-r1" x="732" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">\n</text><text class="terminal-1526668734-r10" x="0" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">│</text><text class="terminal-1526668734-r23" x="12.2" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">▊</text><text class="terminal-1526668734-r24" x="24.4" y="312.8" textLength="488" clip-path="url(#terminal-1526668734-line-12)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-1526668734-r24" x="512.4" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">│</text><text class="terminal-1526668734-r20" x="536.8" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">│</text><text class="terminal-1526668734-r25" x="585.6" y="312.8" textLength="61" clip-path="url(#terminal-1526668734-line-12)">Beads</text><text class="terminal-1526668734-r20" x="719.8" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">│</text><text class="terminal-1526668734-r1" x="732" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">\n</text><text class="terminal-1526668734-r10" x="0" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">│</text><text class="terminal-1526668734-r23" x="12.2" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="337.2" textLength="109.8" clip-path="url(#terminal-1526668734-line-13)">──&#160;Tasks&#160;</text><text class="terminal-1526668734-r26" x="146.4" y="337.2" textLength="73.2" clip-path="url(#terminal-1526668734-line-13)">(2/2)&#160;</text><text class="terminal-1526668734-r11" x="219.6" y="337.2" textLength="256.2" clip-path="url(#terminal-1526668734-line-13)">·&#160;✦&#160;1&#160;awaiting&#160;triag…</text><text class="terminal-1526668734-r24" x="512.4" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">│</text><text class="terminal-1526668734-r20" x="536.8" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">│</text><text class="terminal-1526668734-r20" x="719.8" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">│</text><text class="terminal-1526668734-r1" x="732" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">\n</text><text class="terminal-1526668734-r10" x="0" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">│</text><text class="terminal-1526668734-r23" x="12.2" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="361.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-14)">◆&#160;</text><text class="terminal-1526668734-r27" x="61" y="361.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-14)">·&#160;</text><text class="terminal-1526668734-r11" x="85.4" y="361.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-14)">✦&#160;</text><text class="terminal-1526668734-r28" x="109.8" y="361.6" textLength="146.4" clip-path="url(#terminal-1526668734-line-14)">alpha-ready&#160;</text><text class="terminal-1526668734-r29" x="256.2" y="361.6" textLength="195.2" clip-path="url(#terminal-1526668734-line-14)">Ready&#160;for&#160;triage</text><text class="terminal-1526668734-r2" x="451.4" y="361.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-14)">&#160;…</text><text class="terminal-1526668734-r24" x="512.4" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">│</text><text class="terminal-1526668734-r20" x="536.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">│</text><text class="terminal-1526668734-r2" x="573.4" y="361.6" textLength="97.6" clip-path="url(#terminal-1526668734-line-14)">Select&#160;a</text><text class="terminal-1526668734-r20" x="719.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">│</text><text class="terminal-1526668734-r1" x="732" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">\n</text><text class="terminal-1526668734-r10" x="0" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">│</text><text class="terminal-1526668734-r23" x="12.2" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="386" textLength="24.4" clip-path="url(#terminal-1526668734-line-15)">◆&#160;</text><text class="terminal-1526668734-r27" x="61" y="386" textLength="24.4" clip-path="url(#terminal-1526668734-line-15)">·&#160;</text><text class="terminal-1526668734-r28" x="85.4" y="386" textLength="134.2" clip-path="url(#terminal-1526668734-line-15)">alpha-open&#160;</text><text class="terminal-1526668734-r29" x="219.6" y="386" textLength="219.6" clip-path="url(#terminal-1526668734-line-15)">Ordinary&#160;follow-up</text><text class="terminal-1526668734-r15" x="463.6" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">…</text><text class="terminal-1526668734-r24" x="512.4" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">│</text><text class="terminal-1526668734-r20" x="536.8" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">│</text><text class="terminal-1526668734-r2" x="573.4" y="386" textLength="61" clip-path="url(#terminal-1526668734-line-15)">task,</text><text class="terminal-1526668734-r20" x="719.8" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">│</text><text class="terminal-1526668734-r1" x="732" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">\n</text><text class="terminal-1526668734-r10" x="0" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">│</text><text class="terminal-1526668734-r23" x="12.2" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="410.4" textLength="109.8" clip-path="url(#terminal-1526668734-line-16)">──&#160;Flags&#160;</text><text class="terminal-1526668734-r26" x="146.4" y="410.4" textLength="73.2" clip-path="url(#terminal-1526668734-line-16)">(0/0)&#160;</text><text class="terminal-1526668734-r30" x="219.6" y="410.4" textLength="97.6" clip-path="url(#terminal-1526668734-line-16)">────────</text><text class="terminal-1526668734-r24" x="512.4" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">│</text><text class="terminal-1526668734-r20" x="536.8" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">│</text><text class="terminal-1526668734-r2" x="573.4" y="410.4" textLength="61" clip-path="url(#terminal-1526668734-line-16)">flag,</text><text class="terminal-1526668734-r20" x="719.8" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">│</text><text class="terminal-1526668734-r1" x="732" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">\n</text><text class="terminal-1526668734-r10" x="0" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">│</text><text class="terminal-1526668734-r23" x="12.2" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">▊</text><text class="terminal-1526668734-r26" x="36.6" y="434.8" textLength="292.8" clip-path="url(#terminal-1526668734-line-17)">&#160;&#160;No&#160;matching&#160;flag&#160;beads</text><text class="terminal-1526668734-r24" x="512.4" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">│</text><text class="terminal-1526668734-r20" x="536.8" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">│</text><text class="terminal-1526668734-r2" x="573.4" y="434.8" textLength="97.6" clip-path="url(#terminal-1526668734-line-17)">epic,&#160;or</text><text class="terminal-1526668734-r20" x="719.8" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">│</text><text class="terminal-1526668734-r1" x="732" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">\n</text><text class="terminal-1526668734-r10" x="0" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">│</text><text class="terminal-1526668734-r23" x="12.2" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="459.2" textLength="109.8" clip-path="url(#terminal-1526668734-line-18)">──&#160;Epics&#160;</text><text class="terminal-1526668734-r26" x="146.4" y="459.2" textLength="73.2" clip-path="url(#terminal-1526668734-line-18)">(1/1)&#160;</text><text class="terminal-1526668734-r26" x="219.6" y="459.2" textLength="24.4" clip-path="url(#terminal-1526668734-line-18)">·&#160;</text><text class="terminal-1526668734-r14" x="244" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">⊜</text><text class="terminal-1526668734-r26" x="256.2" y="459.2" textLength="109.8" clip-path="url(#terminal-1526668734-line-18)">&#160;blocked&#160;</text><text class="terminal-1526668734-r32" x="366" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">►</text><text class="terminal-1526668734-r26" x="378.2" y="459.2" textLength="85.4" clip-path="url(#terminal-1526668734-line-18)">&#160;ready&#160;</text><text class="terminal-1526668734-r33" x="463.6" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">…</text><text class="terminal-1526668734-r24" x="512.4" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">│</text><text class="terminal-1526668734-r20" x="536.8" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">│</text><text class="terminal-1526668734-r2" x="573.4" y="459.2" textLength="61" clip-path="url(#terminal-1526668734-line-18)">phase</text><text class="terminal-1526668734-r20" x="719.8" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">│</text><text class="terminal-1526668734-r1" x="732" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">\n</text><text class="terminal-1526668734-r10" x="0" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">│</text><text class="terminal-1526668734-r23" x="12.2" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="483.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-19)">▸&#160;</text><text class="terminal-1526668734-r28" x="61" y="483.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-19)">▸&#160;</text><text class="terminal-1526668734-r34" x="85.4" y="483.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-19)">▤&#160;</text><text class="terminal-1526668734-r28" x="109.8" y="483.6" textLength="97.6" clip-path="url(#terminal-1526668734-line-19)">alpha-1&#160;</text><text class="terminal-1526668734-r35" x="207.4" y="483.6" textLength="231.8" clip-path="url(#terminal-1526668734-line-19)">Build&#160;bead&#160;browsing</text><text class="terminal-1526668734-r15" x="463.6" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">…</text><text class="terminal-1526668734-r24" x="512.4" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">│</text><text class="terminal-1526668734-r20" x="536.8" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">│</text><text class="terminal-1526668734-r2" x="573.4" y="483.6" textLength="61" clip-path="url(#terminal-1526668734-line-19)">bead.</text><text class="terminal-1526668734-r20" x="719.8" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">│</text><text class="terminal-1526668734-r1" x="732" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">\n</text><text class="terminal-1526668734-r10" x="0" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">│</text><text class="terminal-1526668734-r23" x="12.2" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">│</text><text class="terminal-1526668734-r20" x="536.8" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">│</text><text class="terminal-1526668734-r20" x="719.8" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">│</text><text class="terminal-1526668734-r1" x="732" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">\n</text><text class="terminal-1526668734-r10" x="0" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">│</text><text class="terminal-1526668734-r23" x="12.2" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">│</text><text class="terminal-1526668734-r20" x="536.8" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">│</text><text class="terminal-1526668734-r20" x="719.8" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">│</text><text class="terminal-1526668734-r1" x="732" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">\n</text><text class="terminal-1526668734-r10" x="0" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">│</text><text class="terminal-1526668734-r23" x="12.2" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">│</text><text class="terminal-1526668734-r20" x="536.8" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">│</text><text class="terminal-1526668734-r20" x="719.8" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">│</text><text class="terminal-1526668734-r1" x="732" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">\n</text><text class="terminal-1526668734-r10" x="0" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">│</text><text class="terminal-1526668734-r23" x="12.2" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">│</text><text class="terminal-1526668734-r20" x="536.8" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">│</text><text class="terminal-1526668734-r20" x="719.8" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">│</text><text class="terminal-1526668734-r1" x="732" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">\n</text><text class="terminal-1526668734-r10" x="0" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">│</text><text class="terminal-1526668734-r23" x="12.2" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">│</text><text class="terminal-1526668734-r20" x="536.8" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">│</text><text class="terminal-1526668734-r20" x="719.8" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">│</text><text class="terminal-1526668734-r1" x="732" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">\n</text><text class="terminal-1526668734-r10" x="0" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">│</text><text class="terminal-1526668734-r23" x="12.2" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">▊</text><text class="terminal-1526668734-r24" x="24.4" y="630" textLength="488" clip-path="url(#terminal-1526668734-line-25)">▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁</text><text class="terminal-1526668734-r24" x="512.4" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">│</text><text class="terminal-1526668734-r20" x="536.8" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">│</text><text class="terminal-1526668734-r20" x="719.8" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">│</text><text class="terminal-1526668734-r1" x="732" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">\n</text><text class="terminal-1526668734-r10" x="0" y="654.4" textLength="536.8" clip-path="url(#terminal-1526668734-line-26)">╰──────────────────────────────────────────╯</text><text class="terminal-1526668734-r20" x="536.8" y="654.4" textLength="195.2" clip-path="url(#terminal-1526668734-line-26)">╰──────────────╯</text><text class="terminal-1526668734-r1" x="732" y="654.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-26)">\n</text><text class="terminal-1526668734-r11" x="0" y="678.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-27)">j</text><text class="terminal-1526668734-r19" x="12.2" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;next</text><text class="terminal-1526668734-r19" x="73.2" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r11" x="134.2" y="678.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-27)">k</text><text class="terminal-1526668734-r19" x="146.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;prev</text><text class="terminal-1526668734-r19" x="207.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r11" x="268.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">Enter</text><text class="terminal-1526668734-r19" x="329.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;view</text><text class="terminal-1526668734-r19" x="390.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r11" x="451.4" y="678.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-27)">f</text><text class="terminal-1526668734-r19" x="463.6" y="678.8" textLength="85.4" clip-path="url(#terminal-1526668734-line-27)">&#160;filter</text><text class="terminal-1526668734-r19" x="549" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r11" x="610" y="678.8" textLength="73.2" clip-path="url(#terminal-1526668734-line-27)">Ctrl+J</text><text class="terminal-1526668734-r19" x="683.2" y="678.8" textLength="48.8" clip-path="url(#terminal-1526668734-line-27)">&#160;mo…</text><text class="terminal-1526668734-r1" x="732" y="678.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-27)">\n</text><text class="terminal-1526668734-r36" x="0" y="703.2" textLength="732" clip-path="url(#terminal-1526668734-line-28)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-1526668734-r1" x="732" y="703.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-28)">\n</text><text class="terminal-1526668734-r35" x="549" y="727.6" textLength="61" clip-path="url(#terminal-1526668734-line-29)">&#160;AXE&#160;</text><text class="terminal-1526668734-r35" x="610" y="727.6" textLength="109.8" clip-path="url(#terminal-1526668734-line-29)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/_ace_png_snapshot_waits.py:42: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
32.22s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
29.86s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
20.09s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
16.87s call     tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py::test_beads_link_reveal_chip_png_snapshots[size1-link_reveal_chip_beads_60x30]
16.75s call     tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py::test_beads_link_reveal_chip_png_snapshots[size0-link_reveal_chip_beads_120x40]
13.85s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
12.32s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_new_and_clean_png_snapshots[True-mini_xprompt_pane_clean_light_120x40-ACE mini-xprompt pane - clean light]
12.20s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_raw_diagnostics_png_snapshot
11.31s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_xprompt_highlight_solo_light_png_snapshot
11.03s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_readonly_png_snapshot
10.98s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_error_png_snapshot
10.98s call     tests/ace/tui/visual/test_ace_png_snapshots_vcs_repo_completion.py::test_vcs_repo_loading_panel_png_snapshot
10.46s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_completion_provider_scoped_menu_png_snapshot
10.45s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_alias_completion_filtered_preview_png_snapshot
10.38s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
10.24s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_explicit_completion_full_menu_png_snapshot[dark]
9.95s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_family_bead_and_plan_context_png_snapshot
9.92s call     tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py::test_at_reference_completion_panel_png_snapshot
9.71s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_explicit_completion_filtered_preview_png_snapshot
9.56s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_active_upper_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_agents.py::test_artifacts_agents_filter_parse_error_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_clan_collapse.py::test_selected_panel_clan_collapse_precedes_status_group_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_wait_rows_and_queue_detail_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_epic_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_models_panel_modals_cards.py::test_models_panel_runner_limit_action_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_preview_panel.py::test_preview_panel_active_search_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_launch.py::test_config_center_launch_default_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_lumberjack_tree_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_chop_overrun_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_chop_overrun_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_descriptions.py::test_axe_lumberjack_description_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_models_panel_usage.py::test_models_panel_usage_120_columns_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_task_bead_notes_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py::test_axe_long_label_widening_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py::test_axe_constrained_width_no_wrap_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py::test_axe_lumberjack_error_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py::test_agents_fleet_followed_partial_offline_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py::test_agents_fleet_keyboard_focus_and_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py::test_axe_chop_report_error_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_group_clan_collapse.py::test_selected_clan_collapses_before_open_sibling_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py::test_update_panel_pending_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py::test_update_panel_unchecked_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_neighbor_jump_expands_target_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_lane_neighbors_section_fold_levels_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py::test_artifact_links_panel_needs_reveal_row_png_snapshots[size0-artifact_links_panel_needs_reveal_row_120x40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py::test_artifact_links_panel_needs_reveal_row_png_snapshots[size1-artifact_links_panel_needs_reveal_row_60x30]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py::test_beads_link_reveal_chip_png_snapshots[size0-link_reveal_chip_beads_120x40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py::test_beads_link_reveal_chip_png_snapshots[size1-link_reveal_chip_beads_60x30]
====== 36 failed, 869 passed, 1 skipped, 7 warnings in 451.51s (0:07:31) =======
error: recipe `test-visual` failed on line 455 with exit code 1
SASE_YW3_VISUAL_STATUS=1

