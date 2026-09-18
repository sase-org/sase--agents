# Chat History - ace-run (sase-11l.5.1.land--mon)

- **TIMESTAMP:** 2026-09-18 03:14:59 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-11l.5.1.land--mon

## Prompt

sase monitor start --command '(cd sase/repos/linked/sase-core && cargo test -p sase_core agent_hold && cargo test -p sase_core agent_launch && cargo test -p sase_core agent_scan && cargo test -p sase_core_py) && tools/check_sase_core_rs_bindings && tools/validate_sase_core_rs && tools/probe_core_floor && just check-full' --reason 'Run the complete Rust/Python verification required before landing epic sase-11l.5.1'

## Response

   Compiling version_check v0.9.5
   Compiling cfg-if v1.0.4
   Compiling zerocopy v0.8.48
   Compiling proc-macro2 v1.0.106
   Compiling libc v0.2.186
   Compiling unicode-ident v1.0.24
   Compiling quote v1.0.45
   Compiling serde_core v1.0.228
   Compiling find-msvc-tools v0.1.9
   Compiling once_cell v1.21.4
   Compiling shlex v1.3.0
   Compiling typenum v1.20.0
   Compiling autocfg v1.5.0
   Compiling memchr v2.8.0
   Compiling pkg-config v0.3.33
   Compiling vcpkg v0.2.15
   Compiling zmij v1.0.21
   Compiling bitflags v2.11.1
   Compiling rustix v1.1.4
   Compiling serde v1.0.228
   Compiling hashbrown v0.17.0
   Compiling equivalent v1.0.2
   Compiling getrandom v0.4.2
   Compiling regex-syntax v0.8.10
   Compiling linux-raw-sys v0.12.1
   Compiling serde_json v1.0.149
   Compiling thiserror v1.0.69
   Compiling itoa v1.0.18
   Compiling fastrand v2.4.1
   Compiling cpufeatures v0.2.17
   Compiling ryu v1.0.23
   Compiling smallvec v1.15.1
   Compiling unsafe-libyaml v0.2.11
   Compiling fallible-streaming-iterator v0.1.9
   Compiling fallible-iterator v0.3.0
   Compiling unicode-width v0.2.2
   Compiling hex v0.4.3
   Compiling generic-array v0.14.7
   Compiling ahash v0.8.12
   Compiling cc v1.2.61
   Compiling num-traits v0.2.19
   Compiling indexmap v2.14.0
   Compiling aho-corasick v1.1.4
   Compiling getrandom v0.2.17
   Compiling fs2 v0.4.3
   Compiling libsqlite3-sys v0.30.1
   Compiling rand_core v0.6.4
   Compiling syn v2.0.117
   Compiling chrono v0.4.44
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling digest v0.10.7
   Compiling sha2 v0.10.9
   Compiling tempfile v3.27.0
   Compiling regex-automata v0.4.14
   Compiling serde_derive v1.0.228
   Compiling thiserror-impl v1.0.69
   Compiling ppv-lite86 v0.2.21
   Compiling hashbrown v0.14.5
   Compiling rand_chacha v0.3.1
   Compiling regex v1.12.3
   Compiling rand v0.8.6
   Compiling hashlink v0.9.1
   Compiling serde_yaml v0.9.34+deprecated
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.34.50 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/crates/sase_core)
    Finished `test` profile [unoptimized + debuginfo] target(s) in 1m 31s
     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/sase_core-37a4b0a501dd36f3)

running 17 tests
test agent_hold::tests::future_selector_only_matches_after_arm_time ... ok
test agent_hold::tests::hood_matching_honors_component_boundaries_and_shell_suffixes ... ok
test agent_hold::tests::armer_kin_exclusion_covers_self_family_clan_and_descendant ... ok
test agent_hold::tests::proc_shell_matches_name_and_hood_selectors_without_family_kin ... ok
test agent_hold::tests::predicate_matches_each_selector_and_scope ... ok
test agent_hold::tests::unreadable_store_path_is_treated_as_empty ... ok
test agent_hold::tests::list_prunes_expired_malformed_stale_schema_and_dead_armers ... ok
test agent_hold::tests::lock_wait_is_bounded ... ok
test agent_hold::tests::launch_armer_ignores_agent_liveness_fact ... ok
test agent_hold::tests::arm_time_kin_rejection_covers_names_families_clans_and_workflows ... ok
test agent_hold::tests::validation_rejects_bad_inputs_and_sorts_sets ... ok
test agent_hold::tests::proc_terminal_fact_prunes_record ... ok
test agent_hold::tests::rebind_kin_invalid_new_armer_leaves_old_record ... ok
test agent_hold::tests::rebind_absent_key_writes_nothing_and_same_key_works ... ok
test agent_hold::tests::rebind_keeps_timing_and_replaces_key_atomically ... ok
test agent_hold::tests::arm_list_rearm_and_release_round_trip ... ok
test agent_hold::tests::launch_armer_validation_and_liveness_pruning ... ok

test result: ok. 17 passed; 0 failed; 0 ignored; 0 measured; 2972 filtered out; finished in 0.05s

     Running tests/agent_scan_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/agent_scan_parity-2d9af2ffec0752ed)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 45 filtered out; finished in 0.00s

     Running tests/artifact_ref_commit_budget.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/artifact_ref_commit_budget-42ef149d4c373c3d)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/bead_event_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/bead_event_parity-9a5aa7ca588385b9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 33 filtered out; finished in 0.00s

     Running tests/bead_read_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/bead_read_parity-454f395a66a2d338)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 15 filtered out; finished in 0.00s

     Running tests/bead_storage_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/bead_storage_parity-d0fb54e7e79bc388)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 8 filtered out; finished in 0.00s

     Running tests/config_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/config_parity-b44ff980ed652b38)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 26 filtered out; finished in 0.00s

     Running tests/continuation_contract.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/continuation_contract-992cb3fbe549447a)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/git_query_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/git_query_parity-acd1954ac59ed68f)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 33 filtered out; finished in 0.00s

     Running tests/golden_corpus_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/golden_corpus_parity-0aa922a8e63f4ac6)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/notification_store_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/notification_store_parity-0f23827ef8276204)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 59 filtered out; finished in 0.00s

     Running tests/plan_validate_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/plan_validate_parity-b9897e6f32889002)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/prompt_stash_store_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/prompt_stash_store_parity-3b33b071722ba5b9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 12 filtered out; finished in 0.00s

     Running tests/python_wire_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/python_wire_parity-4e671417512e9c1c)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 10 filtered out; finished in 0.00s

     Running tests/query_evaluator_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/query_evaluator_parity-69ea96ba9142d0c4)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 17 filtered out; finished in 0.00s

     Running tests/retryability_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/retryability_parity-d48c40a4bf12db1a)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/vcs_log_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/vcs_log_parity-9081d690a91f7967)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 27 filtered out; finished in 0.00s

    Finished `test` profile [unoptimized + debuginfo] target(s) in 0.17s
     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/sase_core-37a4b0a501dd36f3)

running 169 tests
test agent_launch::admission::tests::agent_dispatch_prompt_keeps_resolved_default_weight_implicit ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_family_and_direct_tribe ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_workspace_and_dispatch ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_clan_declaration_and_join ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_identity_with_queue_directive ... ok
test agent_launch::admission::tests::condition_units_check_after_waits_and_fail_interrupted_checks ... ok
test agent_launch::admission::tests::external_wait_facts_gate_admission ... ok
test agent_launch::admission::tests::dispatching_without_identity_fails_instead_of_redoing_spawn ... ok
test agent_launch::admission::tests::dispatch_fingerprint_is_stable_for_same_payload ... ok
test agent_launch::admission::tests::next_actions_reserve_then_wait_then_dispatch_agent ... ok
test agent_launch::admission::tests::proc_payload_fingerprint_uses_code_digest ... ok
test agent_launch::admission::tests::proc_hold_blocks_waiting_to_eligible_and_eligible_to_dispatch ... ok
test agent_launch::admission::tests::reconcile_keeps_latest_phase_and_identity ... ok
test agent_launch::admission::tests::remote_dispatching_without_identity_retries_same_fingerprint ... ok
test agent_launch::admission::tests::skipped_predecessor_is_terminal_and_does_not_retarget ... ok
test agent_launch::condition::tests::argv_is_not_interpolated ... ok
test agent_launch::admission::tests::summary_counts_partial_success_without_collapsing_errors ... ok
test agent_launch::condition::tests::classify_exit_classes ... ok
test agent_launch::condition::tests::secret_inputs_are_stripped_and_workspace_is_not_shared ... ok
test agent_launch::launch_hold::tests::launch_unit_hold_armer_builds_proc_without_identity_fields ... ok
test agent_launch::launch_hold::tests::launch_unit_hold_key_validates_components ... ok
test agent_launch::launch_hold::tests::launch_unit_hold_armer_builds_agent_identity_shapes ... ok
test agent_launch::proc_runtime::tests::duration_parser_matches_sase_grammar ... ok
test agent_launch::proc_runtime::tests::phases_and_origin_are_stable ... ok
test agent_launch::proc_runtime::tests::ordinary_cwd_requires_an_existing_directory ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_falls_back_to_default_path_without_a_base ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_does_not_duplicate_an_already_prefixed_interpreter_dir ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_preserves_inherited_path_and_prefixes_interpreter_once ... ok
test agent_launch::proc_runtime::tests::shell_names_reject_family_qualification ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_never_copies_forbidden_identity_from_the_base ... ok
test agent_launch::proc_runtime::tests::workspace_false_without_cwd_is_rejected ... ok
test agent_launch::proc_runtime::tests::relative_cwd_rejects_parent_escape ... ok
test agent_launch::proc_runtime::tests::workspace_true_without_project_is_rejected ... ok
test agent_launch::proc_runtime::tests::relative_cwd_stays_inside_the_lease ... ok
test agent_launch::tests::agent_unit_legacy_json_defaults_to_plain_identity ... ok
test agent_launch::proc_runtime::tests::symlink_cwd_cannot_escape_the_lease ... ok
test agent_launch::tests::agent_unit_identity_forms_round_trip_json ... ok
test agent_launch::tests::allocate_and_claim_picks_first_available_workspace ... ok
test agent_launch::tests::batch_predecessor_binding_validates_context ... ok
test agent_launch::tests::claim_workspace_rejects_duplicate_nonzero_but_allows_zero ... ok
test agent_launch::tests::fanout_plan_round_trips_slots ... ok
test agent_launch::conditional::tests::prose_if_mentions_are_literal ... ok
test agent_launch::conditional::tests::invalid_boolean_blocks_entire_batch ... ok
test agent_launch::tests::fanout_planner_deprecated_time_directive_is_not_special ... ok
test agent_launch::conditional::tests::false_boolean_omits_segments ... ok
test agent_launch::conditional::tests::true_boolean_strips_only_directive ... ok
test agent_launch::tests::batch_predecessor_binding_without_name_keeps_identity_only_dependency ... ok
test agent_launch::tests::batch_predecessor_binding_preserves_explicit_and_non_wait_targets ... ok
test agent_launch::tests::batch_predecessor_binding_consumes_zero_argument_wait_forms ... ok
test agent_launch::tests::fanout_planner_time_waits_defer_workspace ... ok
test agent_launch::tests::fanout_planner_rejects_paren_multi_model_directive ... ok
test agent_launch::tests::fanout_planner_rejects_repeated_top_level_model_directives ... ok
test agent_launch::tests::fanout_planner_brace_shorthand_splits_pipe_branches ... ok
test agent_launch::tests::fanout_planner_empty_branch_removes_trailing_space ... ok
test agent_launch::tests::fanout_planner_brace_branch_text_keeps_commas ... ok
test agent_launch::tests::fanout_planner_rejects_same_value_repeated_model_directives ... ok
test agent_launch::tests::fanout_planner_brace_named_and_numeric_branch_ids ... ok
test agent_launch::tests::fanout_planner_empty_branch_preserves_newlines_and_indentation ... ok
test agent_launch::tests::fanout_planner_single_shared_key_collapses_to_one_slot ... ok
test agent_launch::tests::fanout_planner_correlated_group_mixes_named_and_unnamed_ids ... ok
test agent_launch::tests::fanout_planner_empty_branch_collapses_multiple_spaces ... ok
test agent_launch::tests::fanout_planner_brace_composes_cartesian_with_paren_alt ... ok
test agent_launch::tests::fanout_planner_rejects_repeated_top_level_models_with_alternatives ... ok
test agent_launch::tests::fanout_planner_brace_named_text_blocks ... ok
test agent_launch::tests::fanout_planner_empty_branch_removes_leading_space ... ok
test agent_launch::tests::fanout_planner_correlates_transitive_alt_keys ... ok
test agent_launch::tests::fanout_planner_cartesian_products_independent_correlated_groups ... ok
test agent_launch::tests::fanout_planner_brace_model_branches_match_paren_parity ... ok
test agent_launch::tests::fanout_planner_single_top_level_model_is_single_launch ... ok
test agent_launch::tests::fanout_planner_allocates_unnamed_alt_ids_after_named_ids ... ok
test agent_launch::tests::fanout_planner_rejects_repeated_models_with_brace_alternatives ... ok
test agent_launch::conditional::tests::boolean_and_script_body_conflict ... ok
test agent_launch::tests::fanout_planner_model_value_fanout_after_directive_colon ... ok
test agent_launch::tests::fanout_planner_model_alt_ids_preserve_named_model_branches ... ok
test agent_launch::tests::extract_first_model_value_strips_known_effort_suffix ... ok
test agent_launch::tests::fanout_planner_brace_value_fanout_after_directive_colon ... ok
test agent_launch::tests::batch_predecessor_binding_ignores_literal_regions ... ok
test agent_launch::conditional::tests::literal_zones_do_not_trigger_boolean_filter ... ok
test agent_launch::tests::fanout_planner_t_xprompt_defer_workspace ... ok
test agent_launch::tests::fanout_planner_correlates_shared_named_alt_keys ... ok
test agent_launch::tests::fanout_planner_splits_multi_prompt_outside_fences ... ok
test agent_launch::tests::fanout_planner_ignores_alternative_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout_planner_preserves_named_alt_ids_and_values_only ... ok
test agent_launch::tests::fanout_planner_brace_model_branches_report_model_slots ... ok
test agent_launch::tests::fanout_planner_brace_value_fanout_after_effort_e_alias ... ok
test agent_launch::tests::fanout_planner_brace_nested_pipes_do_not_split ... ok
test agent_launch::tests::fanout_planner_ignores_wait_forms_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout_planner_value_fanouts_compose_cartesian ... ok
test agent_launch::tests::fanout_planner_ignores_models_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout_planner_empty_branch_preserves_following_directive_separator ... ok
test agent_launch::tests::fanout_planner_strips_branch_effort_for_slot_naming ... ok
test agent_launch::tests::fanout_planner_unvalued_model_markers_do_not_count_as_repeated ... ok
test agent_launch::tests::fanout_planner_splits_model_branches_and_alternatives ... ok
test agent_launch::tests::fanout_planner_brace_single_branch_has_implicit_empty_variant ... ok
test agent_launch::tests::fanout_planner_empty_branch_collapses_between_words ... ok
test agent_launch::tests::fanout_planner_composes_cartesian_alt_ids ... ok
test agent_launch::tests::fanout_planner_unclosed_brace_reports_missing_close ... ok
test agent_launch::tests::fanout_planner_does_not_support_removed_name_spellings ... ok
test agent_launch::tests::fanout_planner_extracts_repeat_slots ... ok
test agent_launch::tests::fanout_planner_empty_branch_removes_space_before_punctuation ... ok
test agent_launch::tests::occupancy_proceeds_when_no_occupant_record ... ok
test agent_launch::tests::occupancy_proceeds_when_occupant_pid_is_dead ... ok
test agent_launch::tests::launch_request_round_trips_json_shape ... ok
test agent_launch::tests::occupancy_refuses_and_flags_disagreement_when_running_field_missing ... ok
test agent_launch::tests::fanout_planner_preserves_repeat_bead_association ... ok
test agent_launch::tests::occupancy_refuses_and_flags_disagreement_when_running_pid_differs ... ok
test agent_launch::tests::occupancy_proceeds_when_occupant_is_caller ... ok
test agent_launch::tests::launch_inline_scanner_preserves_argument_parser_precedence ... ok
test agent_launch::tests::fanout_planner_preserves_repeat_and_id_inside_literal_zones ... ok
test agent_launch::tests::occupancy_refuses_when_occupant_is_live_other_pid ... ok
test agent_launch::tests::parse_directive_args_text_block_corpus_matches_python ... ok
test agent_launch::tests::prepared_wire_preserves_null_claim_request ... ok
test agent_launch::tests::occupancy_refuses_when_running_field_disagrees_with_dead_occupant ... ok
test agent_launch::tests::timestamp_batch_allocates_unique_visible_timestamps ... ok
test agent_launch::tests::prepare_agent_launch_deferred_and_home_claim_shapes ... ok
test agent_launch::tests::prompt_has_identity_directive_ignores_fenced_id ... ok
test agent_launch::tests::timestamp_batch_rejects_invalid_format ... ok
test agent_launch::tests::transfer_numbered_workspace_matches_pid_when_claim_name_changes ... ok
test agent_launch::tests::timestamp_batch_starts_after_previous_allocation ... ok
test agent_launch::tests::render_alternative_prompt_empty_branch_does_not_invent_space ... ok
test agent_launch::tests::transfer_workspace_claim_matches_pid_and_preserves_claim_name ... ok
test agent_launch::tests::transfer_workspace_claim_preserves_unknown_suffix_fields ... ok
test agent_launch::tests::transfer_workspace_claim_updates_claim_name ... ok
test agent_launch::tests::transfer_placeholder_workspace_still_matches_claim_name ... ok
test agent_launch::tests::prepare_agent_launch_writes_prompt_and_shapes_process_data ... ok
test agent_launch::tests::typed_launch_plan_rejects_invalid_if_forms_without_owned_fence ... ok
test agent_launch::tests::workspace_claims_parse_valid_rows_and_ignore_malformed ... ok
test agent_launch::tests::workspace_claims_keep_suffix_corrupt_rows_occupied ... ok
test agent_launch::tests::typed_launch_future_hold_cycle_rejects_wait_on_sibling ... ok
test agent_launch::tests::typed_launch_future_hold_cycle_rejects_two_future_siblings ... ok
test agent_launch::tests::typed_launch_plan_rejects_agent_directives_on_proc ... ok
test agent_launch::tests::typed_launch_clan_summary_keeps_unbalanced_inner_closer ... ok
test agent_launch::tests::typed_launch_plan_preserves_prose_if_proc_mentions ... ok
test agent_launch::tests::typed_launch_future_hold_without_cycle_is_allowed ... ok
test agent_launch::tests::typed_launch_clan_summary_ignores_inner_text_block_marker ... ok
test agent_launch::tests::typed_launch_plan_captures_bare_fenced_proc ... ok
test agent_launch::tests::typed_launch_plan_validates_proc_project_policy ... ok
test agent_launch::tests::typed_launch_plan_rejects_bare_proc_without_body ... ok
test agent_launch::tests::typed_launch_plan_captures_if_fence_without_duplicate_form_error ... ok
test agent_launch::tests::typed_launch_does_not_replace_unit_workspace_with_plan_project ... ok
test agent_launch::tests::typed_launch_keeps_fenced_workspace_and_dispatch_inert ... ok
test agent_launch::tests::typed_launch_plan_resolves_forward_proc_wait ... ok
test agent_launch::tests::typed_launch_future_hold_cycle_ignores_kin_sibling ... ok
test agent_launch::tests::typed_launch_composes_disjoint_queue_and_fanout ... ok
test agent_launch::tests::typed_launch_plan_keeps_fenced_proc_options ... ok
test agent_launch::tests::typed_launch_plan_builds_mixed_proc_agent_wait_graph ... ok
test agent_launch::tests::typed_launch_plan_preserves_clan_declaration_and_join ... ok
test agent_launch::tests::typed_launch_plan_rejects_conflicting_identity_forms ... ok
test agent_launch::tests::typed_launch_plan_rejects_wait_cycles ... ok
test bead::mutation::tests::claim_for_agent_launch_rejects_missing_closed_and_blank_requests ... ok
test agent_launch::tests::typed_launch_plan_preserves_family_and_direct_tribe ... ok
test agent_launch::tests::typed_launch_preserves_per_unit_workspace_and_dispatch ... ok
test agent_launch::tests::typed_launch_rejects_wait_queue_keywords ... ok
test agent_launch::tests::typed_launch_proc_queue_changes_content_digest ... ok
test agent_launch::tests::typed_launch_parses_queue_spellings_and_round_trips ... ok
test agent_launch::tests::typed_launch_rejects_dispatch_combined_with_wait_or_family ... ok
test agent_launch::tests::typed_launch_proc_accepts_queue_spellings_and_authored_weight ... ok
test agent_launch::proc_runtime::tests::prepare_python_script_uses_sase_interpreter ... ok
test agent_launch::proc_runtime::tests::prepare_bash_script_uses_argv_without_interpolation ... ok
test agent_launch::proc_runtime::tests::prepare_proc_script_preserves_an_inherited_user_bin_directory ... ok
test agent_launch::condition::tests::bash_exit_one_is_skipped ... ok
test agent_launch::condition::tests::bash_exit_two_is_condition_error ... ok
test agent_launch::condition::tests::cancel_path_settles_as_condition_error ... ok
test agent_launch::condition::tests::bash_exit_zero_is_eligible ... ok
test agent_launch::condition::tests::missing_interpreter_and_digest_mismatch_are_errors ... ok
test agent_launch::condition::tests::output_is_truncated_and_cwd_missing_is_error ... ok
test agent_launch::condition::tests::python_reads_condition_context_and_matches_bash_skip ... ok
test agent_launch::condition::tests::timeout_kills_process_group ... ok
test bead::mutation::tests::claim_for_agent_launch_claims_open_and_reassigns_in_progress_issue ... ok

test result: ok. 169 passed; 0 failed; 0 ignored; 0 measured; 2820 filtered out; finished in 0.32s

     Running tests/agent_scan_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/agent_scan_parity-2d9af2ffec0752ed)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 45 filtered out; finished in 0.00s

     Running tests/artifact_ref_commit_budget.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/artifact_ref_commit_budget-42ef149d4c373c3d)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/bead_event_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/bead_event_parity-9a5aa7ca588385b9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 33 filtered out; finished in 0.00s

     Running tests/bead_read_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/bead_read_parity-454f395a66a2d338)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 15 filtered out; finished in 0.00s

     Running tests/bead_storage_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/bead_storage_parity-d0fb54e7e79bc388)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 8 filtered out; finished in 0.00s

     Running tests/config_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/config_parity-b44ff980ed652b38)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 26 filtered out; finished in 0.00s

     Running tests/continuation_contract.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/continuation_contract-992cb3fbe549447a)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/git_query_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/git_query_parity-acd1954ac59ed68f)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 33 filtered out; finished in 0.00s

     Running tests/golden_corpus_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/golden_corpus_parity-0aa922a8e63f4ac6)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/notification_store_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/notification_store_parity-0f23827ef8276204)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 59 filtered out; finished in 0.00s

     Running tests/plan_validate_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/plan_validate_parity-b9897e6f32889002)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/prompt_stash_store_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/prompt_stash_store_parity-3b33b071722ba5b9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 12 filtered out; finished in 0.00s

     Running tests/python_wire_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/python_wire_parity-4e671417512e9c1c)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 10 filtered out; finished in 0.00s

     Running tests/query_evaluator_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/query_evaluator_parity-69ea96ba9142d0c4)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 17 filtered out; finished in 0.00s

     Running tests/retryability_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/retryability_parity-d48c40a4bf12db1a)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/vcs_log_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/vcs_log_parity-9081d690a91f7967)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 27 filtered out; finished in 0.00s

    Finished `test` profile [unoptimized + debuginfo] target(s) in 0.09s
     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/sase_core-37a4b0a501dd36f3)

running 138 tests
test agent_scan::index::tests::abandoned_terminalization_prefers_stopped_at_then_directory_mtime ... ok
test agent_scan::index::tests::index_query_wire_round_trips_active_limit ... ok
test agent_scan::index::tests::prompt_snippet_truncation_stays_on_utf8_char_boundary ... ok
test agent_scan::index::tests::query_keeps_corrupt_existing_index_strict ... ok
test agent_scan::index::tests::alias_history_rejects_empty_aliases ... ok
test agent_scan::index::tests::read_only_open_cannot_write ... ok
test agent_scan::index::tests::refresh_stale_rows_signature_query_does_not_select_record_json ... ok
test agent_scan::index::tests::explicit_workflow_state_hidden_is_still_filtered ... ok
test agent_scan::index::tests::replace_unusable_index_file_renames_sidecars ... ok
test agent_scan::index::tests::active_limit_prioritizes_waiting_rows_over_newer_stale_rows ... ok
test agent_scan::index::tests::explicit_done_finished_at_is_not_overridden_by_stopped_at ... ok
test agent_scan::index::tests::cached_query_returns_rebuilt_records_without_revalidation ... ok
test agent_scan::index::tests::find_gate_shell_by_gate_id_returns_none_for_unknown_id ... ok
test agent_scan::index::tests::done_marker_without_finished_at_or_stopped_at_indexes_null ... ok
test agent_scan::index::tests::find_gate_shell_by_gate_id_prefers_newest_real_shell ... ok
test agent_scan::index::tests::alias_history_falls_back_to_legacy_first_hop ... ok
test agent_scan::index::tests::find_gate_shell_by_gate_id_ignores_inherited_id_on_descendant ... ok
test agent_scan::index::tests::alias_history_preserves_request_order_and_empty_groups ... ok
test agent_scan::index::tests::cached_query_does_not_refresh_stale_marker_rows ... ok
test agent_scan::index::tests::anonymous_appears_as_agent_workflow_is_not_hidden ... ok
test agent_scan::index::tests::find_gate_shell_by_gate_id_respects_project_scoping ... ok
test agent_scan::index::tests::alias_history_truncates_newest_first_and_reports_counts ... ok
test agent_scan::index::tests::alias_history_filters_hidden_and_project_keys ... ok
test agent_scan::index::tests::alias_history_prompt_snippets_strip_collapse_and_truncate ... ok
test agent_scan::index::tests::bounded_artifact_index_delete_skips_locked_database ... ok
test agent_scan::index::tests::machine_candidate_column_is_populated_and_queryable ... ok
test agent_scan::index::tests::machine_candidate_keeps_conflicting_source_and_owner_values ... ok
test agent_scan::index::tests::read_only_open_falls_back_when_index_missing ... ok
test agent_scan::index::tests::index_rebuild_preserves_canonical_queue_capacity_without_waiting_marker ... ok
test agent_scan::index::tests::list_record_shape_projects_only_heavy_leaves ... ok
test agent_scan::index::tests::alias_history_status_counts_projection_rows ... ok
test agent_scan::index::tests::rebuild_replaces_corrupt_existing_index ... ok
test agent_scan::index::tests::output_variable_history_filters_groups_and_truncates ... ok
test agent_scan::index::tests::only_monitors_filters_to_monitor_family_role ... ok
test agent_scan::index::tests::missing_done_finished_at_indexes_from_meta_stopped_at ... ok
test agent_scan::index::tests::indexed_clan_context_honors_latest_declarations_and_generations ... ok
test agent_scan::index::tests::recent_completed_limit_does_not_bound_active_rows ... ok
test agent_scan::layout::tests::canonical_ace_run_path_is_day_sharded ... ok
test agent_scan::layout::tests::non_ace_run_path_stays_flat ... ok
test agent_scan::layout::tests::parse_accepts_legacy_and_sharded_paths ... ok
test agent_scan::layout::tests::collect_prefers_sharded_duplicate_timestamp ... ok
test agent_scan::layout::tests::parse_rejects_malformed_shard_paths ... ok
test agent_scan::scanner::tests::capacity_only_keeps_active_dir_without_running_or_waiting_marker ... ok
test agent_scan::scanner::tests::capacity_only_omits_plan_path_and_used_xprompts ... ok
test agent_scan::index::tests::machine_candidate_uses_meta_then_done_machine_precedence ... ok
test agent_scan::scanner::tests::capacity_only_preserves_capacity_snapshot_fields ... ok
test agent_scan::layout::tests::resolve_legacy_path_to_shard_when_present ... ok
test agent_scan::index::tests::machine_candidate_includes_mixed_provenance_family_relatives ... ok
test agent_scan::scanner::tests::scanner_accepts_explicit_zero_queue_weight_but_rejects_implicit_zero ... ok
test agent_scan::scanner::tests::scanner_defaults_absent_alias_trail_and_origin ... ok
test agent_scan::scanner::tests::scanner_distinguishes_absent_valid_and_invalid_queue_weight ... ok
test agent_scan::scanner::tests::scanner_projects_runner_claim_owner_key_and_ignores_blank ... ok
test agent_scan::scanner::tests::scanner_defaults_absent_monitor_next_model ... ok
test agent_scan::scanner::tests::scanner_preserves_canonical_legacy_and_dual_queue_capacity ... ok
test agent_scan::scanner::tests::scanner_round_trips_alias_trail_and_origin ... ok
test agent_scan::scanner::tests::scanner_round_trips_gate_shell_metadata ... ok
test agent_scan::scanner::tests::scanner_round_trips_monitor_next_model ... ok
test agent_scan::scanner::tests::capacity_only_skips_done_dirs_before_parsing_markers ... ok
test agent_scan::index::tests::find_gate_shell_by_gate_id_uses_indexed_lookup_not_full_decode ... ok
test agent_scan::index::tests::active_query_excludes_dismissed_identity_after_rebuild ... ok
test agent_scan::selector::tests::parser_accepts_nested_and_escaped_paths ... ok
test agent_scan::selector::tests::parser_rejects_invalid_selectors ... ok
test agent_scan::selector::tests::parser_splits_dotted_names_from_the_right ... ok
test agent_scan::index::tests::late_xprompts_file_refreshes_cached_record ... ok
test agent_scan::index::tests::full_history_query_applies_candidate_filter_before_decoding ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_alias_trail_and_origin ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_every_gate_field ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::agent_meta_wire_without_gate_fields_still_parses ... ok
test agent_scan::wire::tests::agent_meta_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::done_marker_wire_round_trips_every_gate_field ... ok
test agent_scan::wire::tests::done_marker_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::done_marker_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_defaults_absent_alias_trail ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_round_trips_alias_trail_and_origin ... ok
test agent_scan::index::tests::load_agent_artifact_records_returns_full_records_for_dirs_and_aliases ... ok
test agent_scan::index::tests::query_self_heals_newly_added_run_started_at ... ok
test agent_scan::index::tests::query_self_heals_done_creation_before_completed_filter ... ok
test agent_scan::index::tests::query_self_heals_waiting_deletion_to_running ... ok
test agent_scan::index::tests::query_self_heals_running_to_done_transition ... ok
test agent_scan::index::tests::cached_full_history_after_reconcile_reuses_watermark_without_discovery ... ok
test agent_scan::index::tests::query_self_heals_hidden_to_visible_before_visible_filter ... ok
test agent_scan::index::tests::query_self_heals_appended_feedback_submitted_at ... ok
test agent_scan::index::tests::full_history_revalidate_discovers_unindexed_artifact_and_claims_complete ... ok
test agent_scan::index::tests::query_self_heals_appended_plan_submitted_at ... ok
test agent_scan::index::tests::query_skips_rescan_when_signatures_match ... ok
test agent_scan::index::tests::full_history_revalidate_drops_deleted_artifact_instead_of_stale_json ... ok
test agent_scan::index::tests::alias_history_revalidate_refreshes_candidate_rows ... ok
test agent_scan::index::tests::rebuild_indexes_scanner_equivalent_records ... ok
test agent_scan::index::tests::hidden_terminal_retention_prunes_dependents_and_is_idempotent ... ok
test agent_scan::index::tests::query_self_heals_pending_question_creation_and_deletion ... ok
test agent_scan::index::tests::bounded_query_retains_dismissed_clan_declaration_as_context ... ok
test agent_scan::index::tests::alias_history_projection_replaces_and_deletes_rows ... ok
test agent_scan::index::tests::dismissal_reconcile_backfills_dead_family_members_only ... ok
test agent_scan::index::tests::dismissed_replace_diffs_instead_of_rewriting_the_table ... ok
test agent_scan::index::tests::full_history_revalidate_repairs_hidden_toggle_via_dirty_directory ... ok
test agent_scan::index::tests::dismissal_reconcile_uses_dismissed_parent_suffix_when_root_row_deleted ... ok
test agent_scan::index::tests::hidden_inclusive_full_history_can_inspect_dismissed_rows ... ok
test agent_scan::index::tests::migration_recomputes_hidden_for_v1_indexes ... ok
test agent_scan::index::tests::output_variable_projection_backfills_replaces_and_deletes_rows ... ok
test agent_scan::index::tests::recent_completed_rows_remain_visible_when_not_dismissed ... ok
test agent_scan::index::tests::related_artifact_dirs_follow_retry_and_parent_lineage ... ok
test agent_scan::index::tests::terminal_workflow_state_rows_are_recent_completed_rows ... ok
test agent_scan::index::tests::status_reports_freelist_and_file_size ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_skips_fresh_missing_marker_race ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_skips_workspace_claim ... ok
test agent_scan::index::tests::settled_monitor_without_finished_at_stays_in_recent_completed_window ... ok
test agent_scan::index::tests::tier1_active_query_is_bounded_to_newest_incomplete_rows ... ok
test agent_scan::index::tests::wait_completed_records_are_indexed_as_running ... ok
test agent_scan::index::tests::windowed_query_applies_safe_candidate_filter ... ok
test agent_scan::index::tests::tier1_revalidate_with_candidate_filter_does_not_prefilter_all_rows ... ok
test agent_scan::index::tests::windowed_query_preserves_active_rows_and_selects_completed_budget ... ok
test agent_scan::index::tests::windowed_query_selects_completed_budget_when_active_exceeds_limit ... ok
test agent_scan::index::tests::resolve_family_dismissal_lineage_honors_dead_seed_own_dismissal ... ok
test agent_scan::index::tests::resolve_family_dismissal_lineage_follows_parent_to_dismissed_root ... ok
test agent_scan::selector::tests::multiple_selectors_preserve_order_and_dedup ... ok
test agent_scan::selector::tests::hood_and_global_selectors_collapse_repeated_runs ... ok
test agent_scan::selector::tests::hidden_project_limit_and_ambiguity ... ok
test agent_scan::selector::tests::exact_key_wildcard_uses_newest_artifact_only ... ok
test agent_scan::selector::tests::nested_paths_and_failures_are_precise ... ok
test agent_scan::selector::tests::unscoped_and_exact_selectors_use_newest_artifact ... ok
test agent_scan::selector::tests::unscoped_key_wildcard_and_unnamed_rows ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_revalidates_new_running_marker ... ok
test agent_scan::index::tests::upsert_and_delete_one_artifact_row ... ok
test agent_scan::index::tests::windowed_query_decodes_only_selected_candidates ... ok
test agent_scan::index::tests::schema_v19_upgrade_refreshes_record_json_for_model_aliases ... ok
test agent_scan::index::tests::schema_v18_upgrade_adds_xprompts_signature_column ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_hides_abandoned_record ... ok
test agent_scan::index::tests::vacuum_reclaims_freelist_pages_and_preserves_rows ... ok
test agent_scan::index::tests::terminalize_repairs_visible_abandoned_rows ... ok
test agent_scan::index::tests::schema_v29_upgrade_adds_imported_owner_machine_projection ... ok
test agent_scan::index::tests::schema_v30_upgrade_adds_and_backfills_gate_shell_id_projection ... ok
test agent_scan::index::tests::schema_v24_upgrade_backfills_done_outcome_projection ... ok
test agent_scan::index::tests::schema_v21_upgrade_backfills_model_alias_projection ... ok
test agent_scan::index::tests::schema_v27_upgrade_adds_and_backfills_source_machine_projection ... ok
test agent_scan::index::tests::stale_dismissed_suffixes_do_not_consume_active_limit ... ok
test agent_scan::index::tests::hidden_terminal_retention_bounds_rebuild_and_preserves_anchors ... ok
test agent_scan::index::tests::dismissal_reconcile_is_set_based_on_large_fixture ... ok

test result: ok. 138 passed; 0 failed; 0 ignored; 0 measured; 2851 filtered out; finished in 18.45s

     Running tests/agent_scan_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/agent_scan_parity-2d9af2ffec0752ed)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 45 filtered out; finished in 0.00s

     Running tests/artifact_ref_commit_budget.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/artifact_ref_commit_budget-42ef149d4c373c3d)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/bead_event_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/bead_event_parity-9a5aa7ca588385b9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 33 filtered out; finished in 0.00s

     Running tests/bead_read_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/bead_read_parity-454f395a66a2d338)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 15 filtered out; finished in 0.00s

     Running tests/bead_storage_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/bead_storage_parity-d0fb54e7e79bc388)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 8 filtered out; finished in 0.00s

     Running tests/config_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/config_parity-b44ff980ed652b38)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 26 filtered out; finished in 0.00s

     Running tests/continuation_contract.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/continuation_contract-992cb3fbe549447a)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/git_query_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/git_query_parity-acd1954ac59ed68f)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 33 filtered out; finished in 0.00s

     Running tests/golden_corpus_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/golden_corpus_parity-0aa922a8e63f4ac6)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/notification_store_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/notification_store_parity-0f23827ef8276204)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 59 filtered out; finished in 0.00s

     Running tests/plan_validate_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/plan_validate_parity-b9897e6f32889002)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/prompt_stash_store_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/prompt_stash_store_parity-3b33b071722ba5b9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 12 filtered out; finished in 0.00s

     Running tests/python_wire_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/python_wire_parity-4e671417512e9c1c)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 10 filtered out; finished in 0.00s

     Running tests/query_evaluator_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/query_evaluator_parity-69ea96ba9142d0c4)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 17 filtered out; finished in 0.00s

     Running tests/retryability_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/retryability_parity-d48c40a4bf12db1a)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/vcs_log_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/deps/vcs_log_parity-9081d690a91f7967)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 27 filtered out; finished in 0.00s

   Compiling once_cell v1.21.4
   Compiling pin-project-lite v0.2.17
   Compiling bytes v1.11.1
   Compiling futures-core v0.3.32
   Compiling stable_deref_trait v1.2.1
   Compiling target-lexicon v0.12.16
   Compiling log v0.4.29
   Compiling serde_core v1.0.228
   Compiling smallvec v1.15.1
   Compiling litemap v0.8.2
   Compiling untrusted v0.9.0
   Compiling tower-service v0.3.3
   Compiling memchr v2.8.0
   Compiling slab v0.4.12
   Compiling httparse v1.10.1
   Compiling futures-task v0.3.32
   Compiling writeable v0.6.3
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling icu_normalizer_data v2.2.0
   Compiling serde_json v1.0.149
   Compiling fnv v1.0.7
   Compiling httpdate v1.0.3
   Compiling futures-sink v0.3.32
   Compiling rustls v0.21.12
   Compiling percent-encoding v2.3.2
   Compiling powerfmt v0.2.0
   Compiling time-core v0.1.8
   Compiling rustversion v1.0.22
   Compiling try-lock v0.2.5
   Compiling num-conv v0.2.1
   Compiling thiserror v2.0.18
   Compiling tower-layer v0.3.3
   Compiling mime v0.3.17
   Compiling atomic-waker v1.1.2
   Compiling sync_wrapper v1.0.2
   Compiling heck v0.5.0
   Compiling num-traits v0.2.19
   Compiling memoffset v0.9.1
   Compiling base64 v0.21.7
   Compiling base64 v0.22.1
   Compiling iana-time-zone v0.1.65
   Compiling encoding_rs v0.8.35
   Compiling ipnet v2.12.0
   Compiling matchit v0.7.3
   Compiling sync_wrapper v0.1.2
   Compiling ring v0.17.14
   Compiling webpki-roots v0.25.4
   Compiling unindent v0.2.4
   Compiling indoc v2.0.7
   Compiling syn v2.0.117
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling socket2 v0.5.10
   Compiling futures-channel v0.3.32
   Compiling signal-hook-registry v1.4.8
   Compiling tracing-core v0.1.36
   Compiling ahash v0.8.12
   Compiling tempfile v3.27.0
   Compiling http v1.4.0
   Compiling deranged v0.5.8
   Compiling http v0.2.12
   Compiling want v0.3.1
   Compiling form_urlencoded v1.2.2
   Compiling rustls-pemfile v1.0.4
   Compiling futures-util v0.3.32
   Compiling time-macros v0.2.27
   Compiling pyo3-build-config v0.22.6
   Compiling pem v3.0.6
   Compiling hashbrown v0.14.5
   Compiling aho-corasick v1.1.4
   Compiling num-integer v0.1.46
   Compiling chrono v0.4.44
   Compiling tracing v0.1.44
   Compiling num-bigint v0.4.6
   Compiling http-body v1.0.1
error: failed to run custom build command for `pyo3-build-config v0.22.6`

Caused by:
  process didn't exit successfully: `/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-260916_134618/build/debug/build/pyo3-build-config-5edcdccbe2a2ae05/build-script-build` (exit status: 1)
  --- stdout
  cargo:rerun-if-env-changed=PYO3_CONFIG_FILE
  cargo:rerun-if-env-changed=PYO3_NO_PYTHON
  cargo:rerun-if-env-changed=PYO3_ENVIRONMENT_SIGNATURE
  cargo:rerun-if-env-changed=PYO3_PYTHON
  cargo:rerun-if-env-changed=VIRTUAL_ENV
  cargo:rerun-if-env-changed=CONDA_PREFIX
  cargo:rerun-if-env-changed=PATH

  --- stderr
  error: cannot set a minimum Python version 3.12 higher than the interpreter version 3.11 (the minimum Python version is implied by the abi3-py312 feature)
warning: build failed, waiting for other jobs to finish...

