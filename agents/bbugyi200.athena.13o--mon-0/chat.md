# Chat History - ace-run (13o--mon-0)

- **TIMESTAMP:** 2026-10-24 08:56:12 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** 13o--mon-0

## Prompt

sase monitor start --command 'cd sase/repos/linked/sase-core && just test -p sase_core autonomy && just test -p sase_core agent_scan && just test -p sase_core_py autonomy && sase tool run check && cd ../../../.. && just rust-dev-install && just fix && sase memory init --no-commit && sase tool run check' --reason 'Verify repaired auto_questions_wait digest and finish Rust/Python/documentation pipeline'

## Response

sase tool run 0836ac4a83f85e49ff0a9400634feef6
./scripts/check.sh test -p sase_core autonomy
   Compiling libc v0.2.186
   Compiling cfg-if v1.0.4
   Compiling proc-macro2 v1.0.106
   Compiling unicode-ident v1.0.24
   Compiling quote v1.0.45
   Compiling memchr v2.8.0
   Compiling zerocopy v0.8.48
   Compiling find-msvc-tools v0.1.9
   Compiling shlex v1.3.0
   Compiling crossbeam-utils v0.8.21
   Compiling regex-syntax v0.8.10
   Compiling serde_core v1.0.228
   Compiling version_check v0.9.5
   Compiling siphasher v1.0.4
   Compiling log v0.4.29
   Compiling autocfg v1.5.0
   Compiling serde v1.0.228
   Compiling crossbeam-epoch v0.9.21
   Compiling once_cell v1.21.4
   Compiling bitflags v2.11.1
   Compiling crossbeam-deque v0.8.8
   Compiling hashbrown v0.17.0
   Compiling zmij v1.0.21
   Compiling equivalent v1.0.2
   Compiling itoa v1.0.18
   Compiling ucd-trie v0.1.7
   Compiling iana-time-zone v0.1.65
   Compiling serde_json v1.0.149
   Compiling same-file v1.0.6
   Compiling libm v0.2.16
   Compiling typenum v1.20.0
   Compiling smallvec v1.15.1
   Compiling pin-project-lite v0.2.17
   Compiling lazy_static v1.5.0
   Compiling deunicode v1.6.2
   Compiling futures-sink v0.3.32
   Compiling futures-core v0.3.32
   Compiling parking_lot_core v0.9.12
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling clap_lex v1.1.1
   Compiling percent-encoding v2.3.2
   Compiling pkg-config v0.3.33
   Compiling scopeguard v1.2.0
   Compiling unicode-segmentation v1.13.3
   Compiling heck v0.5.0
   Compiling vcpkg v0.2.15
   Compiling anstyle v1.0.14
   Compiling bytes v1.11.1
   Compiling thiserror v1.0.69
   Compiling slab v0.4.12
   Compiling rustix v1.1.4
   Compiling winnow v1.0.4
   Compiling futures-io v0.3.32
   Compiling futures-task v0.3.32
   Compiling getrandom v0.4.2
   Compiling winnow v0.7.15
   Compiling home v0.5.12
   Compiling tower-service v0.3.3
   Compiling linux-raw-sys v0.12.1
   Compiling sync_wrapper v1.0.2
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling tower-layer v0.3.3
   Compiling cpufeatures v0.2.17
   Compiling fallible-streaming-iterator v0.1.9
   Compiling ryu v1.0.23
   Compiling tinyvec v1.13.3
   Compiling unsafe-libyaml v0.2.11
   Compiling fallible-iterator v0.3.0
   Compiling fastrand v2.4.1
   Compiling hex v0.4.3
   Compiling unicode-width v0.2.2
   Compiling unicode-casefold v0.2.0
   Compiling colored v2.2.0
   Compiling encoding_rs v0.8.35
   Compiling tracing-core v0.1.36
   Compiling walkdir v2.5.0
   Compiling futures-channel v0.3.32
   Compiling generic-array v0.14.7
   Compiling ahash v0.8.12
   Compiling cc v1.2.61
   Compiling lock_api v0.4.14
   Compiling num-traits v0.2.19
   Compiling itertools v0.11.0
   Compiling slug v0.1.6
   Compiling etcetera v0.8.0
   Compiling indexmap v2.14.0
   Compiling phf_shared v0.11.3
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling grep-matcher v0.1.9
   Compiling clap_builder v4.6.7
   Compiling unicode-normalization v0.1.25
   Compiling crossbeam-channel v0.5.17
   Compiling phf v0.11.3
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling humansize v2.1.3
   Compiling getrandom v0.2.17
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling memmap2 v0.9.11
   Compiling term_size v0.3.2
   Compiling fs2 v0.4.3
   Compiling signal-hook-registry v1.4.8
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling rand_core v0.6.4
   Compiling libsqlite3-sys v0.30.1
   Compiling chrono v0.4.44
   Compiling encoding_rs_io v0.1.8
   Compiling parking_lot v0.12.5
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling grep-searcher v0.1.17
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling digest v0.10.7
   Compiling serde_spanned v1.1.2
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling regex-automata v0.4.14
   Compiling tempfile v3.27.0
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling rayon v1.12.0
   Compiling toml v0.9.12+spec-1.1.0
   Compiling pest v2.9.4
   Compiling ppv-lite86 v0.2.21
   Compiling hashbrown v0.14.5
   Compiling rand_chacha v0.3.1
   Compiling pest_meta v2.9.4
   Compiling hashlink v0.9.1
   Compiling rand v0.8.6
   Compiling phf_generator v0.11.3
   Compiling phf_codegen v0.11.3
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling serde_derive v1.0.228
   Compiling tokio-macros v2.7.0
   Compiling tracing-attributes v0.1.31
   Compiling thiserror-impl v1.0.69
   Compiling futures-macro v0.3.32
   Compiling arbitrary v1.5.0
   Compiling pest_derive v2.9.4
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling tracing v0.1.44
   Compiling clap v4.6.7
   Compiling table_formatter v0.6.1
   Compiling clap-cargo v0.18.3
   Compiling chrono-tz-build v0.3.0
   Compiling chrono-tz v0.9.0
   Compiling globwalk v0.9.1
   Compiling json5 v0.4.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling rusqlite v0.32.1
   Compiling tower v0.5.3
   Compiling tokio-util v0.7.18
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling tokei v15.0.0
   Compiling sase_core v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core)
    Finished `test` profile [unoptimized + debuginfo] target(s) in 2m 35s
     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/sase_core-43193ebbd7b980de)

running 30 tests
test autonomy::tests::digest_golden_is_stable ... ok
test autonomy::tests::ask_value_reports_its_policy_key ... ok
test agent_scan::scanner::tests::agent_meta_wire_omits_absent_autonomy ... ok
test autonomy::tests::decision_echoes_record_identity ... ok
test autonomy::tests::missing_required_option_asks_without_partial_selection ... ok
test agent_scan::scanner::tests::scanner_refreshes_stale_builtin_autonomy_policy ... ok
test autonomy::tests::approve_archive_carries_both_option_ids_in_canonical_order ... ok
test autonomy::tests::decision_sentences_render_both_examples ... ok
test agent_scan::scanner::tests::scanner_derives_legacy_auto_fields_from_autonomy_record ... ok
test autonomy::tests::legacy_translation_matches_resolve_for_canonical_shapes ... ok
test autonomy::tests::legacy_round_trip_is_stable ... ok
test autonomy::tests::explicit_profile_and_overrides_keep_their_policy ... ok
test autonomy::tests::option_order_does_not_change_the_decision ... ok
test autonomy::tests::legacy_translation_covers_every_writer_shape ... ok
test autonomy::tests::inherit_keeps_narrows_or_refuses ... ok
test autonomy::tests::fleet_auto_approved_routes_through_evaluate ... ok
test autonomy::tests::projection_reproduces_writer_output ... ok
test autonomy::tests::resolve_rejects_bad_source_and_actor ... ok
test autonomy::tests::record_wire_round_trips ... ok
test autonomy::tests::resolve_rejects_unknown_spellings_with_invalid_auto ... ok
test autonomy::tests::privileged_and_unknown_kinds_always_ask ... ok
test autonomy::tests::resolve_covers_every_spelling ... ok
test autonomy::tests::mutate_covers_every_status ... ok
test autonomy::tests::stale_builtin_inheritance_and_mutation_use_effective_policy ... ok
test autonomy::tests::unmentioned_value_asks ... ok
test autonomy::tests::decision_log_round_trips_filters_and_rotates ... ok
test autonomy::tests::compat_rows_give_contract_outcomes ... ok
test autonomy::tests::stale_builtin_refresh_preserves_identity_and_plan_outcomes ... ok
test autonomy::tests::value_outside_capabilities_asks_without_partial_selection ... ok
test autonomy::tests::summary_covers_every_profile ... ok

test result: ok. 30 passed; 0 failed; 0 ignored; 0 measured; 5330 filtered out; finished in 0.00s

     Running tests/agent_scan_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/agent_scan_parity-6e4e50e4df8ca6c4)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 45 filtered out; finished in 0.00s

     Running tests/artifact_ref_commit_budget.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/artifact_ref_commit_budget-beb7423c9aaefd2b)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/bead_event_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_event_parity-e2d20336857ba3dc)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 35 filtered out; finished in 0.00s

     Running tests/bead_read_model_mutation_proof.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_read_model_mutation_proof-c93980c5fc6dc804)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 2 filtered out; finished in 0.00s

     Running tests/bead_read_model_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_read_model_parity-cd895a32f5fdd297)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 6 filtered out; finished in 0.00s

     Running tests/bead_read_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_read_parity-814571923369b6d9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 16 filtered out; finished in 0.00s

     Running tests/bead_storage_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_storage_parity-a9d43cbaf144688f)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 8 filtered out; finished in 0.00s

     Running tests/bead_touch_index_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_touch_index_parity-e47bd38000f713c1)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 2 filtered out; finished in 0.00s

     Running tests/command_line_perf.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/command_line_perf-04f3e016abac7fd9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/command_line_resolver.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/command_line_resolver-1fa11de338551ede)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 28 filtered out; finished in 0.00s

     Running tests/config_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/config_parity-bf1bf561b2b8488b)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 36 filtered out; finished in 0.00s

     Running tests/continuation_contract.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/continuation_contract-cfd837526f7dec6c)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/git_query_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/git_query_parity-b1d4cfe74cd9c068)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 33 filtered out; finished in 0.00s

     Running tests/golden_corpus_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/golden_corpus_parity-4a75e1ca41422143)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/hermetic_test_env.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/hermetic_test_env-86a210b3d69bb3a7)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/notification_store_parity/main.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/notification_store_parity-5dbf2f3bedc60f00)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 83 filtered out; finished in 0.00s

     Running tests/plan_validate_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/plan_validate_parity-006ee36469150194)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 2 filtered out; finished in 0.00s

     Running tests/prompt_stash_archive.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/prompt_stash_archive-705c6a458a25a3ec)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 13 filtered out; finished in 0.00s

     Running tests/prompt_stash_store_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/prompt_stash_store_parity-7b1a079e1f1cae07)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 12 filtered out; finished in 0.00s

     Running tests/prompt_stash_trash_lifecycle.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/prompt_stash_trash_lifecycle-d83bbacb091b7472)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 19 filtered out; finished in 0.00s

     Running tests/python_wire_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/python_wire_parity-feaf7ef44e561f42)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 13 filtered out; finished in 0.00s

     Running tests/query_evaluator_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/query_evaluator_parity-06ed341460fc6c04)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 17 filtered out; finished in 0.00s

     Running tests/retryability_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/retryability_parity-7325b31f838e6259)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/vcs_log_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/vcs_log_parity-515d26d4db9b961f)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 27 filtered out; finished in 0.00s

./scripts/check.sh test -p sase_core agent_scan
    Finished `test` profile [unoptimized + debuginfo] target(s) in 0.32s
     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/sase_core-43193ebbd7b980de)

running 199 tests
test agent_scan::index::tests::history::prompt_snippet_truncation_stays_on_utf8_char_boundary ... ok
test agent_scan::index::tests::history::refresh_stale_rows_signature_query_does_not_select_record_json ... ok
test agent_scan::index::tests::checkpoint::checkpoint_skips_missing_wal_without_opening ... ok
test agent_scan::index::tests::readers::aliases_are_empty_when_the_index_is_missing ... ok
test agent_scan::index::tests::readers::schema_version_is_none_when_file_is_missing ... ok
test agent_scan::index::tests::readers::schema_version_is_none_when_file_is_unreadable ... ok
test agent_scan::index::tests::readers::schema_version_is_zero_when_meta_key_is_missing ... ok
test agent_scan::index::tests::readers::schema_version_is_zero_when_meta_table_is_missing ... ok
test agent_scan::index::tests::checkpoint::checkpoint_skips_small_wal ... ok
test agent_scan::index::tests::checkpoint::read_write_open_bounds_wal_and_uses_normal_sync ... ok
test agent_scan::index::tests::history::alias_history_falls_back_to_legacy_first_hop ... ok
test agent_scan::index::tests::clan_context::terminal_workflow_state_rows_are_recent_completed_rows ... ok
test agent_scan::index::tests::history::alias_history_status_counts_projection_rows ... ok
test agent_scan::index::tests::clan_context::recorded_clan_attributes_overlay_index_queries ... ok
test agent_scan::index::tests::history::alias_history_rejects_empty_aliases ... ok
test agent_scan::index::tests::readers::schema_version_read_does_not_create_an_index ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_ignores_inherited_id_on_descendant ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_returns_none_for_unknown_id ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_respects_project_scoping ... ok
test agent_scan::index::tests::history::alias_history_filters_hidden_and_project_keys ... ok
test agent_scan::index::tests::readers::projection_rejects_an_empty_column_list ... ok
test agent_scan::index::tests::lineage::wait_completed_records_are_indexed_as_running ... ok
test agent_scan::index::tests::clan_context::anonymous_appears_as_agent_workflow_is_not_hidden ... ok
test agent_scan::index::tests::readers::projection_rejects_unknown_column_names ... ok
test agent_scan::index::tests::history::alias_history_prefers_canonical_raw_prompt ... ok
test agent_scan::index::tests::history::output_variable_history_filters_groups_and_truncates ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_prefers_newest_real_turn ... ok
test agent_scan::index::tests::history::alias_history_prompt_snippets_strip_collapse_and_truncate ... ok
test agent_scan::index::tests::history::alias_history_preserves_request_order_and_empty_groups ... ok
test agent_scan::index::tests::storage::query_keeps_corrupt_existing_index_strict ... ok
test agent_scan::index::tests::readers::projection_serves_catalog_and_provenance_column_sets ... ok
test agent_scan::index::tests::agent_session_filter::agent_session_candidate_decodes_only_matching_rows ... ok
test agent_scan::index::tests::clan_context::explicit_workflow_state_hidden_is_still_filtered ... ok
test agent_scan::index::tests::storage::replace_unusable_index_file_renames_sidecars ... ok
test agent_scan::index::tests::clan_context::recent_completed_rows_remain_visible_when_not_dismissed ... ok
test agent_scan::index::tests::clan_context::indexed_clan_context_honors_latest_declarations_and_generations ... ok
test agent_scan::index::tests::machine_projection::only_monitors_filters_to_monitor_agent_session_role ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_uses_indexed_lookup_not_full_decode ... ok
test agent_scan::index::tests::terminalization::abandoned_terminalization_prefers_stopped_at_then_directory_mtime ... ok
test agent_scan::index::tests::history::alias_history_truncates_newest_first_and_reports_counts ... ok
test agent_scan::index::tests::machine_projection::machine_candidate_keeps_conflicting_source_and_owner_values ... ok
test agent_scan::index::tests::machine_projection::list_record_shape_projects_only_heavy_leaves ... ok
test agent_scan::index::tests::lineage::related_artifact_dirs_follow_retry_and_parent_lineage ... ok
test agent_scan::index::tests::machine_projection::machine_candidate_includes_mixed_provenance_agent_session_relatives ... ok
test agent_scan::index::tests::machine_projection::machine_candidate_uses_meta_then_done_machine_precedence ... ok
test agent_scan::index::tests::machine_projection::machine_candidate_column_is_populated_and_queryable ... ok
test agent_scan::index::tests::agent_session_filter::agent_session_candidate_selects_only_that_lane ... ok
test agent_scan::index::tests::lineage::resolve_agent_session_dismissal_lineage_honors_dead_seed_own_dismissal ... ok
test agent_scan::index::tests::readers::projection_does_not_migrate_a_stale_index ... ok
test agent_scan::index::tests::history::load_agent_artifact_records_returns_full_records_for_dirs_and_aliases ... ok
test agent_scan::index::tests::readers::schema_version_read_does_not_migrate_a_stale_index ... ok
test agent_scan::index::tests::self_heal::cached_full_history_after_reconcile_reuses_watermark_without_discovery ... ok
test agent_scan::index::tests::checkpoint::checkpoint_truncates_oversized_wal ... ok
test agent_scan::index::tests::history::alias_history_revalidate_refreshes_candidate_rows ... ok
test agent_scan::index::tests::visibility::index_query_wire_round_trips_active_limit ... ok
test agent_scan::index::tests::self_heal::full_history_revalidate_drops_deleted_artifact_instead_of_stale_json ... ok
test agent_scan::index::tests::self_heal::full_history_revalidate_discovers_unindexed_artifact_and_claims_complete ... ok
test agent_scan::index::tests::clan_context::schema_v19_upgrade_refreshes_record_json_for_model_aliases ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_defaults_off ... ok
test agent_scan::index::tests::lineage::resolve_agent_session_dismissal_lineage_follows_parent_to_dismissed_root ... ok
test agent_scan::index::tests::clan_context::schema_v18_upgrade_adds_xprompts_signature_column ... ok
test agent_scan::index::tests::clan_context::schema_v24_upgrade_backfills_done_outcome_projection ... ok
test agent_scan::index::tests::history::alias_history_projection_replaces_and_deletes_rows ... ok
test agent_scan::index::tests::self_heal::query_self_heals_appended_feedback_submitted_at ... ok
test agent_scan::index::tests::self_heal::full_history_revalidate_repairs_hidden_toggle_via_dirty_directory ... ok
test agent_scan::index::tests::storage::read_only_open_falls_back_when_index_missing ... ok
test agent_scan::index::tests::clan_context::bounded_query_retains_dismissed_clan_declaration_as_context ... ok
test agent_scan::index::tests::clan_context::migration_recomputes_hidden_for_v1_indexes ... ok
test agent_scan::index::tests::self_heal::tier1_revalidate_with_candidate_filter_does_not_prefilter_all_rows ... ok
test agent_scan::index::tests::storage::cached_query_does_not_refresh_stale_marker_rows ... ok
test agent_scan::index::tests::storage::cached_query_returns_rebuilt_records_without_revalidation ... ok
test agent_scan::index::tests::self_heal::query_self_heals_appended_plan_submitted_at ... ok
test agent_scan::layout::tests::canonical_ace_run_path_is_day_sharded ... ok
test agent_scan::layout::tests::collect_prefers_sharded_duplicate_timestamp ... ok
test agent_scan::layout::tests::non_ace_run_path_stays_flat ... ok
test agent_scan::layout::tests::parse_accepts_legacy_and_sharded_paths ... ok
test agent_scan::layout::tests::parse_rejects_malformed_shard_paths ... ok
test agent_scan::layout::tests::resolve_legacy_path_to_shard_when_present ... ok
test agent_scan::index::tests::storage::read_only_open_cannot_write ... ok
test agent_scan::scanner::tests::agent_meta_wire_omits_absent_auto_restart ... ok
test agent_scan::scanner::tests::agent_meta_wire_omits_absent_autonomy ... ok
test agent_scan::index::tests::lineage::schema_v33_index_with_both_gate_columns_keeps_legacy_projection ... ok
test agent_scan::scanner::tests::capacity_only_keeps_active_dir_without_running_or_waiting_marker ... ok
test agent_scan::scanner::tests::capacity_only_omits_plan_path_and_used_macros ... ok
test agent_scan::scanner::tests::capacity_only_preserves_capacity_snapshot_fields ... ok
test agent_scan::scanner::tests::scanner_accepts_explicit_zero_queue_weight_but_rejects_implicit_zero ... ok
test agent_scan::scanner::tests::scanner_canonicalizes_agent_tab_and_drops_invalid_values ... ok
test agent_scan::index::tests::self_heal::full_history_revalidate_repairs_several_stale_rows_in_one_pass ... ok
test agent_scan::scanner::tests::scanner_coerces_created_epics_tolerantly ... ok
test agent_scan::scanner::tests::scanner_coerces_wait_epic_follows_tolerantly ... ok
test agent_scan::scanner::tests::scanner_coerces_finalizer_status_tolerantly ... ok
test agent_scan::scanner::tests::scanner_defaults_absent_alias_trail_and_origin ... ok
test agent_scan::scanner::tests::scanner_derives_legacy_auto_fields_from_autonomy_record ... ok
test agent_scan::scanner::tests::scanner_defaults_absent_monitor_next_model ... ok
test agent_scan::scanner::tests::durable_readers_prefer_canonical_macros_and_raw_prompt ... ok
test agent_scan::index::tests::lineage::schema_v30_upgrade_adds_and_backfills_gate_turn_id_projection ... ok
test agent_scan::scanner::tests::scanner_prefers_turn_keys_and_stores_monitor_kind ... ok
test agent_scan::scanner::tests::scanner_distinguishes_absent_valid_and_invalid_queue_weight ... ok
test agent_scan::scanner::tests::scanner_reads_auto_approve_argument ... ok
test agent_scan::scanner::tests::scanner_reads_agent_session_spellings_first ... ok
test agent_scan::scanner::tests::scanner_reads_auto_restart_object ... ok
test agent_scan::scanner::tests::scanner_projects_runner_claim_owner_key_and_ignores_blank ... ok
test agent_scan::scanner::tests::scanner_refreshes_stale_builtin_autonomy_policy ... ok
test agent_scan::scanner::tests::scanner_preserves_canonical_legacy_and_dual_queue_capacity ... ok
test agent_scan::scanner::tests::scanner_reads_valid_queue_capacity_multiplier_from_meta_and_waiting ... ok
test agent_scan::scanner::tests::scanner_round_trips_alias_trail_and_origin ... ok
test agent_scan::scanner::tests::scanner_round_trips_auto_restart_through_snapshot ... ok
test agent_scan::scanner::tests::capacity_only_skips_done_dirs_before_parsing_markers ... ok
test agent_scan::scanner::tests::scanner_round_trips_gate_turn_metadata ... ok
test agent_scan::scanner::tests::scanner_round_trips_monitor_next_model ... ok
test agent_scan::index::tests::machine_projection::schema_v27_upgrade_adds_and_backfills_source_machine_projection ... ok
test agent_scan::index::tests::self_heal::query_self_heals_newly_added_run_started_at ... ok
test agent_scan::index::tests::self_heal::query_self_heals_hidden_to_visible_before_visible_filter ... ok
test agent_scan::selector::tests::parser_rejects_invalid_selectors ... ok
test agent_scan::selector::tests::parser_accepts_nested_and_escaped_paths ... ok
test agent_scan::index::tests::machine_projection::schema_v29_upgrade_adds_imported_owner_machine_projection ... ok
test agent_scan::selector::tests::parser_splits_dotted_names_from_the_right ... ok
test agent_scan::wire::tests::agent_meta_wire_accepts_legacy_spellings_but_emits_canonical ... ok
test agent_scan::wire::tests::agent_meta_wire_accepts_all_three_member_keys_but_emits_canonical ... ok
test agent_scan::wire::tests::agent_meta_wire_defaults_created_epics_empty ... ok
test agent_scan::wire::tests::agent_meta_wire_omits_absent_auto_restart ... ok
test agent_scan::wire::tests::agent_meta_wire_maps_legacy_proc_turn_kind_to_monitor ... ok
test agent_scan::wire::tests::agent_meta_wire_omits_absent_finalizer_status ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_alias_trail_and_origin ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_auto_restart ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_created_epics ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_every_gate_field ... ok
test agent_scan::index::tests::history::schema_v21_upgrade_backfills_model_alias_projection ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_finalizer_status_summary ... ok
test agent_scan::wire::tests::agent_meta_wire_without_gate_fields_still_parses ... ok
test agent_scan::wire::tests::agent_meta_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::done_marker_wire_accepts_all_three_member_keys_but_emits_canonical ... ok
test agent_scan::wire::tests::done_marker_wire_round_trips_every_gate_field ... ok
test agent_scan::wire::tests::done_marker_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::done_marker_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_defaults_absent_alias_trail ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_round_trips_alias_trail_and_origin ... ok
test agent_scan::index::tests::self_heal::query_self_heals_done_creation_before_completed_filter ... ok
test agent_scan::index::tests::storage::bounded_artifact_index_delete_skips_locked_database ... ok
test agent_scan::index::tests::readers::aliases_round_trip_upsert_list_and_delete ... ok
test agent_scan::index::tests::self_heal::query_skips_rescan_when_signatures_match ... ok
test agent_scan::index::tests::self_heal::query_self_heals_running_to_done_transition ... ok
test agent_scan::index::tests::agent_session_filter::legacy_agent_family_column_migrates_in_place ... ok
test agent_scan::index::tests::agent_session_filter::legacy_agent_family_column_beside_agent_session_merges_in_place ... ok
test agent_scan::index::tests::self_heal::query_self_heals_waiting_deletion_to_running ... ok
test agent_scan::index::tests::storage::status_reports_freelist_and_file_size ... ok
test agent_scan::index::tests::terminalization::explicit_done_finished_at_is_not_overridden_by_stopped_at ... ok
test agent_scan::index::tests::terminalization::terminalize_stale_active_rows_skips_workspace_claim ... ok
test agent_scan::index::tests::terminalization::missing_done_finished_at_indexes_from_meta_stopped_at ... ok
test agent_scan::index::tests::storage::rebuild_replaces_corrupt_existing_index ... ok
test agent_scan::index::tests::lineage::schema_v34_upgrade_renames_gate_shell_id_column_in_place ... ok
test agent_scan::index::tests::terminalization::done_marker_without_finished_at_or_stopped_at_indexes_null ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_full_history_skips_non_projectable_records ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_derives_clan_context_from_waiting_only_scalars ... ok
test agent_scan::index::tests::visibility::recent_completed_limit_does_not_bound_active_rows ... ok
test agent_scan::index::tests::visibility::active_limit_prioritizes_waiting_rows_over_newer_stale_rows ... ok
test agent_scan::index::tests::visibility::tier1_active_query_is_bounded_to_newest_incomplete_rows ... ok
test agent_scan::index::tests::terminalization::settled_monitor_without_finished_at_stays_in_recent_completed_window ... ok
test agent_scan::index::tests::terminalization::terminalize_stale_active_rows_skips_fresh_missing_marker_race ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_keeps_home_running_and_workflow_records ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_preserves_agent_session_relative_projectable_extras ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_keeps_noop_done_and_skips_hidden ... ok
test agent_scan::index::tests::self_heal::unchanged_full_history_revalidate_commits_nothing ... ok
test agent_scan::index::tests::storage::late_xprompts_file_refreshes_cached_record ... ok
test agent_scan::index::tests::self_heal::query_self_heals_pending_question_creation_and_deletion ... ok
test agent_scan::index::tests::storage::upsert_and_delete_one_artifact_row ... ok
test agent_scan::index::tests::windowed_query::index_rebuild_preserves_canonical_queue_capacity_without_waiting_marker ... ok
test agent_scan::index::tests::windowed_query::windowed_query_selects_completed_budget_when_active_exceeds_limit ... ok
test agent_scan::index::tests::storage::durable_canonical_selection_refreshes_indexed_record ... ok
test agent_scan::index::tests::terminalization::terminalize_stale_active_rows_revalidates_new_running_marker ... ok
test agent_scan::index::tests::history::output_variable_projection_backfills_replaces_and_deletes_rows ... ok
test agent_scan::index::tests::windowed_query::windowed_query_applies_safe_candidate_filter ... ok
test agent_scan::index::tests::visibility::active_query_excludes_dismissed_identity_after_rebuild ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_skips_marker_only_active_records ... ok
test agent_scan::index::tests::windowed_query::windowed_query_preserves_active_rows_and_selects_completed_budget ... ok
test agent_scan::index::tests::storage::hidden_terminal_retention_prunes_dependents_and_is_idempotent ... ok
test agent_scan::selector::tests::multiple_selectors_preserve_order_and_dedup ... ok
test agent_scan::selector::tests::exact_key_wildcard_uses_newest_artifact_only ... ok
test agent_scan::selector::tests::unscoped_key_wildcard_and_unnamed_rows ... ok
test agent_scan::selector::tests::hood_and_global_selectors_collapse_repeated_runs ... ok
test agent_scan::selector::tests::unscoped_and_exact_selectors_use_newest_artifact ... ok
test agent_scan::selector::tests::hidden_project_limit_and_ambiguity ... ok
test agent_scan::selector::tests::nested_paths_and_failures_are_precise ... ok
test agent_scan::index::tests::checkpoint::checkpoint_reports_busy_instead_of_failing ... ok
test agent_scan::index::tests::windowed_query::windowed_query_decodes_only_selected_candidates ... ok
test agent_scan::index::tests::windowed_query::full_history_query_applies_candidate_filter_before_decoding ... ok
test agent_scan::index::tests::windowed_query::rebuild_indexes_scanner_equivalent_records ... ok
test agent_scan::index::tests::storage::schema_v33_index_migrates_to_current ... ok
test agent_scan::index::tests::terminalization::terminalize_stale_active_rows_hides_abandoned_record ... ok
test agent_scan::index::tests::visibility::dismissed_replace_diffs_instead_of_rewriting_the_table ... ok
test agent_scan::index::tests::storage::vacuum_reclaims_freelist_pages_and_preserves_rows ... ok
test agent_scan::index::tests::visibility::hidden_inclusive_full_history_can_inspect_dismissed_rows ... ok
test agent_scan::index::tests::visibility::dismissal_reconcile_backfills_dead_agent_session_members_only ... ok
test agent_scan::index::tests::terminalization::terminalize_repairs_visible_abandoned_rows ... ok
test agent_scan::index::tests::visibility::dismissal_reconcile_uses_dismissed_parent_suffix_when_root_row_deleted ... ok
test agent_scan::index::tests::visibility::stale_dismissed_suffixes_do_not_consume_active_limit ... ok
test agent_scan::index::tests::storage::hidden_terminal_retention_bounds_rebuild_and_preserves_anchors ... ok
test agent_scan::index::tests::visibility::dismissal_reconcile_is_set_based_on_large_fixture ... ok

test result: ok. 199 passed; 0 failed; 0 ignored; 0 measured; 5161 filtered out; finished in 15.73s

     Running tests/agent_scan_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/agent_scan_parity-6e4e50e4df8ca6c4)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 45 filtered out; finished in 0.00s

     Running tests/artifact_ref_commit_budget.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/artifact_ref_commit_budget-beb7423c9aaefd2b)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/bead_event_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_event_parity-e2d20336857ba3dc)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 35 filtered out; finished in 0.00s

     Running tests/bead_read_model_mutation_proof.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_read_model_mutation_proof-c93980c5fc6dc804)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 2 filtered out; finished in 0.00s

     Running tests/bead_read_model_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_read_model_parity-cd895a32f5fdd297)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 6 filtered out; finished in 0.00s

     Running tests/bead_read_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_read_parity-814571923369b6d9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 16 filtered out; finished in 0.00s

     Running tests/bead_storage_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_storage_parity-a9d43cbaf144688f)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 8 filtered out; finished in 0.00s

     Running tests/bead_touch_index_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/bead_touch_index_parity-e47bd38000f713c1)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 2 filtered out; finished in 0.00s

     Running tests/command_line_perf.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/command_line_perf-04f3e016abac7fd9)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/command_line_resolver.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/command_line_resolver-1fa11de338551ede)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 28 filtered out; finished in 0.00s

     Running tests/config_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/config_parity-bf1bf561b2b8488b)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 36 filtered out; finished in 0.00s

     Running tests/continuation_contract.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/continuation_contract-cfd837526f7dec6c)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/git_query_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/git_query_parity-b1d4cfe74cd9c068)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 33 filtered out; finished in 0.00s

     Running tests/golden_corpus_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/golden_corpus_parity-4a75e1ca41422143)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/hermetic_test_env.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/hermetic_test_env-86a210b3d69bb3a7)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 1 filtered out; finished in 0.00s

     Running tests/notification_store_parity/main.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/notification_store_parity-5dbf2f3bedc60f00)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 83 filtered out; finished in 0.00s

     Running tests/plan_validate_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/plan_validate_parity-006ee36469150194)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 2 filtered out; finished in 0.00s

     Running tests/prompt_stash_archive.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/prompt_stash_archive-705c6a458a25a3ec)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 13 filtered out; finished in 0.00s

     Running tests/prompt_stash_store_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/prompt_stash_store_parity-7b1a079e1f1cae07)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 12 filtered out; finished in 0.00s

     Running tests/prompt_stash_trash_lifecycle.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/prompt_stash_trash_lifecycle-d83bbacb091b7472)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 19 filtered out; finished in 0.00s

     Running tests/python_wire_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/python_wire_parity-feaf7ef44e561f42)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 13 filtered out; finished in 0.00s

     Running tests/query_evaluator_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/query_evaluator_parity-06ed341460fc6c04)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 17 filtered out; finished in 0.00s

     Running tests/retryability_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/retryability_parity-7325b31f838e6259)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 3 filtered out; finished in 0.00s

     Running tests/vcs_log_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_083849/build/debug/deps/vcs_log_parity-515d26d4db9b961f)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 27 filtered out; finished in 0.00s

./scripts/check.sh test -p sase_core_py autonomy
   Compiling target-lexicon v0.12.16
   Compiling stable_deref_trait v1.2.1
   Compiling percent-encoding v2.3.2
   Compiling litemap v0.8.2
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling untrusted v0.9.0
   Compiling icu_normalizer_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling fnv v1.0.7
   Compiling httpdate v1.0.3
   Compiling rustls v0.21.12
   Compiling http v1.4.0
   Compiling rustversion v1.0.22
   Compiling num-conv v0.2.1
   Compiling try-lock v0.2.5
   Compiling time-core v0.1.8
   Compiling powerfmt v0.2.0
   Compiling thiserror v2.0.18
   Compiling mime v0.3.17
   Compiling ring v0.17.14
   Compiling atomic-waker v1.1.2
   Compiling memoffset v0.9.1
   Compiling base64 v0.22.1
   Compiling base64 v0.21.7
   Compiling tracing-log v0.2.0
   Compiling thread_local v1.1.9
   Compiling sharded-slab v0.1.7
   Compiling nu-ansi-term v0.50.3
   Compiling matchit v0.7.3
   Compiling ipnet v2.12.0
   Compiling webpki-roots v0.25.4
   Compiling sync_wrapper v0.1.2
   Compiling socket2 v0.5.10
   Compiling serde_path_to_error v0.1.20
   Compiling synstructure v0.13.2
   Compiling zerovec-derive v0.11.3
   Compiling displaydoc v0.2.5
   Compiling thiserror-impl v2.0.18
   Compiling num-integer v0.1.46
   Compiling async-trait v0.1.89
   Compiling async-stream-impl v0.3.6
   Compiling matchers v0.2.0
   Compiling unindent v0.2.4
   Compiling indoc v2.0.7
   Compiling tera v1.20.1
   Compiling form_urlencoded v1.2.2
   Compiling async-stream v0.3.6
   Compiling http v0.2.12
   Compiling deranged v0.5.8
   Compiling want v0.3.1
   Compiling num-bigint v0.4.6
   Compiling tracing-subscriber v0.3.23
   Compiling http-body v1.0.1
   Compiling time-macros v0.2.27
   Compiling rustls-pemfile v1.0.4
   Compiling pem v3.0.6
   Compiling pyo3-build-config v0.22.6
   Compiling serde_urlencoded v0.7.1
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling http-body-util v0.1.3
   Compiling hyper v1.9.0
   Compiling http-body v0.4.6
   Compiling h2 v0.3.27
   Compiling zerofrom v0.1.7
   Compiling time v0.3.47
   Compiling yoke v0.8.2
   Compiling axum-core v0.4.5
   Compiling tower-http v0.5.2
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling hyper-util v0.1.20
   Compiling tokei v15.0.0
   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling icu_collections v2.2.0
   Compiling icu_locale_core v2.2.0
   Compiling simple_asn1 v0.6.4
   Compiling axum v0.7.9
   Compiling jsonwebtoken v9.3.1
   Compiling icu_provider v2.2.0
   Compiling pyo3-macros v0.22.6
   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling sase_core v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core)
   Compiling hyper v0.14.32
   Compiling tokio-rustls v0.24.1
   Compiling idna_adapter v1.2.2
   Compiling idna v1.1.0
   Compiling url v2.5.8
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling sase_gateway v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core_py)
error[E0599]: no associated function or constant named `new` found for struct `pyo3::types::PyModule` in the current scope
   --> crates/sase_core_py/src/autonomy/tests.rs:326:32
    |
326 |         let module = PyModule::new(py, "autonomy_test").unwrap();
    |                                ^^^ associated function or constant not found in `pyo3::types::PyModule`

For more information about this error, try `rustc --explain E0599`.
error: could not compile `sase_core_py` (lib test) due to 1 previous error
error: recipe `test` failed on line 23 with exit code 101
failed  exit=101  duration=319489ms

