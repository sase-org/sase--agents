# Chat History - ace-run (toobig-a1.test_artifacts_beads_filtering.0--mon)

- **TIMESTAMP:** 2026-11-18 01:57:37 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** toobig-a1.test_artifacts_beads_filtering.0--mon

## Prompt

sase monitor start --command 'just check' --reason 'Verify the Artifacts Beads test split before host completion'

## Response

sase tool run 999625eff2d18fbc6455f3ab362b5f38
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ epic-symbol freshness
✓ fmt (python)
✓ fmt (markdown)
✓ fmt (generated docs)
✓ fmt (sase-backed docs)
✓ model policy
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (eager annotations)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (docs contract)
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.44.2 is missing 39 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] agent_artifact_list_wire_schema_version: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_decide: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] agent_hijack_eligibility_wire_schema_version: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] agent_hijack_latch_observe: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_latch_wire_schema_version: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_select_occupant: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] apply_chop_batch_transition: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] artifact_file_association_query: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); no release tag contains it yet.
[core-floor-probe] artifact_file_association_query_wire_schema_version: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); no release tag contains it yet.
[core-floor-probe] artifact_read_audit_query: first appears in sase-core 3992fce (feat(audit-query): query artifact-read audit logs); no release tag contains it yet.
[core-floor-probe] artifact_read_audit_query_wire_schema_version: first appears in sase-core 3992fce (feat(audit-query): query artifact-read audit logs); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query_wire_schema_version: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_view_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] decide_local_command_trust: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] digest_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] filter_trusted_local_layer: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] hijack_latch_force_eligibility: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] hijack_latch_reconcile: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] local_command_trust_store_allow: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); no release tag contains it yet.
[core-floor-probe] local_command_trust_store_get: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); no release tag contains it yet.
[core-floor-probe] local_command_trust_store_revoke: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); no release tag contains it yet.
[core-floor-probe] local_command_trust_wire_schema_version: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] lookup_agent_artifacts: first appears in sase-core a4b1c84 (feat(agent-scan): add read-only indexed artifact identity lookups); no release tag contains it yet.
[core-floor-probe] lookup_named_dismissed_bundle: first appears in sase-core d201086 (feat(agent-scan): add bounded named lookup selection); no release tag contains it yet.
[core-floor-probe] memory_audit_query: first appears in sase-core c5e60d7 (feat(audit-query): add targeted memory audit query over JSONL); no release tag contains it yet.
[core-floor-probe] memory_audit_query_wire_schema_version: first appears in sase-core c5e60d7 (feat(audit-query): add targeted memory audit query over JSONL); no release tag contains it yet.
[core-floor-probe] plan_prompt_command_substitution: first appears in sase-core 1191f9a (feat: add prompt command-substitution source policy); no release tag contains it yet.
[core-floor-probe] project_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] prompt_command_substitution_wire_schema_version: first appears in sase-core 1191f9a (feat: add prompt command-substitution source policy); no release tag contains it yet.
[core-floor-probe] query_agent_artifact_index_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] reconcile_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] scan_agent_artifact_dir_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] scan_agent_artifact_dirs_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] scan_agent_artifacts_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] select_agent_artifact_group: first appears in sase-core b9f33b0 (feat(agent-scan): select indexed session and clan generations); no release tag contains it yet.
[core-floor-probe] select_named_agent: first appears in sase-core d201086 (feat(agent-scan): add bounded named lookup selection); no release tag contains it yet.
[core-floor-probe] summarize_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] validate_chop_batch_manifest: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "8cedd45", "name": "agent_artifact_list_wire_schema_version", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "9940715", "name": "agent_hijack_decide", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "9940715", "name": "agent_hijack_eligibility_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_observe", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "9940715", "name": "agent_hijack_select_occupant", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "6cd9a0c", "name": "apply_chop_batch_transition", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "19b89ac", "name": "artifact_file_association_query", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "19b89ac", "name": "artifact_file_association_query_wire_schema_version", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "3992fce", "name": "artifact_read_audit_query", "release": null, "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "3992fce", "name": "artifact_read_audit_query_wire_schema_version", "release": null, "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "9f9341e", "name": "bead_touch_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "9f9341e", "name": "bead_touch_member_query_wire_schema_version", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "9f9341e", "name": "bead_view_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "e7647bf", "name": "decide_local_command_trust", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "digest_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "filter_trusted_local_layer", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e9b1cf0", "name": "hijack_latch_force_eligibility", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "hijack_latch_reconcile", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "233cb41", "name": "local_command_trust_store_allow", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_get", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_revoke", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "e7647bf", "name": "local_command_trust_wire_schema_version", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "a4b1c84", "name": "lookup_agent_artifacts", "release": null, "subject": "feat(agent-scan): add read-only indexed artifact identity lookups"}, {"commit": "d201086", "name": "lookup_named_dismissed_bundle", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "c5e60d7", "name": "memory_audit_query", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "c5e60d7", "name": "memory_audit_query_wire_schema_version", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "1191f9a", "name": "plan_prompt_command_substitution", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "e7647bf", "name": "project_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "1191f9a", "name": "prompt_command_substitution_wire_schema_version", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "8cedd45", "name": "query_agent_artifact_index_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "6cd9a0c", "name": "reconcile_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "8cedd45", "name": "scan_agent_artifact_dir_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "8cedd45", "name": "scan_agent_artifact_dirs_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "8cedd45", "name": "scan_agent_artifacts_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "b9f33b0", "name": "select_agent_artifact_group", "release": null, "subject": "feat(agent-scan): select indexed session and clan generations"}, {"commit": "d201086", "name": "select_named_agent", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "6cd9a0c", "name": "summarize_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "6cd9a0c", "name": "validate_chop_batch_manifest", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}], "declared_floor": "0.44.2", "exit_code": 4, "message": "sase-core-rs==0.44.2 is missing 39 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
selected 93 of 5785 test files (rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost)
coverage contexts: baseline 96183d71b3ef (stale, 5293 commits behind HEAD) matched 0 changed file(s) and contributed 0 test file(s)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.13.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 1173 items

tests/ace/tui/test_artifacts_beads_filtering_queries.py ..E.........     [  1%]
tests/ace/tui/test_artifacts_beads_filtering_stranded.py ..              [  1%]
tests/ace/tui/test_artifacts_beads_filtering_ui.py ......                [  1%]
tests/ace/tui/test_visual_fixture_host_paths.py .                        [  1%]
tests/test_agent_session_terminology.py ..                               [  1%]
tests/test_agent_stop_hook_config.py .                                   [  2%]
tests/test_agent_tribe_terminology.py ..                                 [  2%]
tests/test_check_sase_core_rs_bindings_tool.py ..........                [  3%]
tests/test_ci_bootstrap_sidecars_tool.py ..................              [  4%]
tests/test_commit_type_tag_contract.py ..                                [  4%]
tests/test_config_schema.py ................                             [  6%]
tests/test_config_schema_ace.py .......................                  [  8%]
tests/test_config_schema_beads.py ...................                    [  9%]
tests/test_config_schema_extensions.py ................................. [ 12%]
.............                                                            [ 13%]
tests/test_config_schema_gate_turn.py .....                              [ 14%]
tests/test_config_schema_keymaps.py .................                    [ 15%]
tests/test_config_schema_runtime_limits.py .........................     [ 17%]
tests/test_core_finalizer_facade.py .........                            [ 18%]
tests/test_demo_media_postprocessor.py ............                      [ 19%]
tests/test_exercise_release.py .......................                   [ 21%]
tests/test_gemini_active_surface_guard.py ..                             [ 21%]
tests/test_github_actions_build_core.py .............                    [ 22%]
tests/test_github_actions_ci_master_gate.py ............................ [ 25%]
.......                                                                  [ 25%]
tests/test_github_actions_ci_workflow.py ............................... [ 28%]
                                                                         [ 28%]
tests/test_github_actions_install_smoke.py ...................           [ 29%]
tests/test_github_actions_publish.py .....                               [ 30%]
tests/test_github_actions_release.py ..............................      [ 32%]
tests/test_github_actions_release_steward.py ..........                  [ 33%]
tests/test_github_actions_setup_sase.py ............                     [ 34%]
tests/test_github_actions_testpypi_drill.py .........                    [ 35%]
tests/test_justfile_lint_check.py ...........................            [ 37%]
tests/test_justfile_lint_lint.py .................                       [ 39%]
tests/test_justfile_lint_setup.py .....................                  [ 41%]
tests/test_justfile_sase_core_dir.py ...............................     [ 43%]
tests/test_macro_terminology.py ..........                               [ 44%]
tests/test_patch_stitch_terminology_audit.py ..................          [ 46%]
tests/test_probe_core_floor_tool.py ........                             [ 46%]
tests/test_project_display_presentation_audit.py .........               [ 47%]
tests/test_prompt_prediction_replay_sources.py ......                    [ 48%]
tests/test_ratchet_core_pin_source_normalization.py ..........           [ 48%]
tests/test_ratchet_core_pin_tool_core.py .                               [ 49%]
tests/test_ratchet_core_pin_tool_guardrails.py .......                   [ 49%]
tests/test_ratchet_core_pin_tool_modes.py ........                       [ 50%]
tests/test_ratchet_core_pin_tool_reconciliation.py .......               [ 50%]
tests/test_ratchet_core_pin_tool_ref.py ....                             [ 51%]
tests/test_ratchet_core_revision_tool.py ...........                     [ 52%]
tests/test_release_candidate_inventory.py .............................. [ 54%]
.............                                                            [ 55%]
tests/test_release_candidate_publish.py ........                         [ 56%]
tests/test_release_candidate_published_core.py ....................      [ 58%]
tests/test_release_candidate_qualify_red.py ...                          [ 58%]
tests/test_release_candidate_rerun.py ...........                        [ 59%]
tests/test_release_candidate_seal.py ...........................         [ 61%]
tests/test_release_core.py ........................................      [ 65%]
tests/test_require_tool_run.py .................                         [ 66%]
tests/test_ruff_config.py .                                              [ 66%]
tests/test_run_pytest_command.py ................................        [ 69%]
tests/test_run_pytest_contention.py ..................................   [ 72%]
tests/test_run_pytest_health.py .....                                    [ 72%]
tests/test_run_pytest_main.py .............                              [ 73%]
tests/test_run_pytest_scoped.py ..............                           [ 75%]
tests/test_run_pytest_tmpdir.py ...................                      [ 76%]
tests/test_run_pytest_workers.py ...................                     [ 78%]
tests/test_rust_install_cleanup.py ..                                    [ 78%]
tests/test_sase_bead_tool.py ....                                        [ 78%]
tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py ..          [ 78%]
tests/test_sase_core_rs_bead_resolution_smoke_tool.py .                  [ 79%]
tests/test_sase_core_rs_feature_flag_state_smoke_tool.py ..              [ 79%]
tests/test_sase_core_rs_glossary_line_break_smoke_tool.py ..             [ 79%]
tests/test_sase_core_rs_plan_header_smoke_tool.py ..                     [ 79%]
tests/test_sase_core_rs_telemetry_smoke_tool.py .....                    [ 79%]
tests/test_sase_core_wheel_cache_tool.py ...........                     [ 80%]
tests/test_sase_migrate_statuses.py ...                                  [ 81%]
tests/test_sase_turn_terminology.py ...                                  [ 81%]
tests/test_sdd_canonical_layout.py ..                                    [ 81%]
tests/test_setup_required_plugins_tool.py ...................            [ 83%]
tests/test_suite_gate.py .................                               [ 84%]
tests/test_suite_gate_budget.py ...............                          [ 85%]
tests/test_suite_gate_lease.py ............                              [ 86%]
tests/test_suite_gate_reclaim.py ................                        [ 88%]
tests/test_timezone_display_guard.py .                                   [ 88%]
tests/test_tool_adoption_report_tool.py .........................        [ 90%]
tests/test_validate_changelog_tool.py ......                             [ 91%]
tests/test_validate_dependency_group_tool.py ...                         [ 91%]
tests/test_validate_sase_core_rs_contracts_fleet_tool.py ....            [ 91%]
tests/test_validate_sase_core_rs_contracts_provider_tool.py ...          [ 91%]
tests/test_validate_sase_core_rs_contracts_tool.py ..........            [ 92%]
tests/test_validate_sase_core_rs_environment_tool.py ........            [ 93%]
tests/test_validate_sase_core_rs_prompt_tool.py .....                    [ 93%]
tests/test_validate_sase_core_rs_runtime_tool.py ..................      [ 95%]
tests/test_validate_sase_core_rs_tool.py ....................            [ 97%]
tests/test_validate_sase_core_rs_version_tool.py ..............          [ 98%]
tests/test_validate_test_environment_tool.py ....................        [100%]

==================================== ERRORS ====================================
________ ERROR at setup of test_invalid_bead_filter_tokens_are_rejected ________
file /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/test_artifacts_beads_filtering_queries.py, line 99
  def test_invalid_bead_filter_tokens_are_rejected(query: str) -> None:
E       fixture 'query' not found
>       available fixtures: LineMatcher, _asyncio_loop_factory, _class_scoped_runner, _clear_agent_env_vars, _clear_config_caches, _clear_console_color_override_env_vars, _config_for_test, _configure_test_git_identity, _confine_agent_termination_to_test_children, _default_test_llm_cli, _disable_detach_scope_by_default, _disable_plugin_commands_by_default, _event_driven_bare_pilot_pause, _forbid_bare_git_sdd_init_in_repo_checkout, _freeze_model_alias_defaults, _function_scoped_runner, _isolate_capacity_report_feed, _isolate_commits_current_project, _isolate_commits_project_display_inventory, _isolate_default_llm_effort, _isolate_git_remote_probe, _isolate_memory_history_warmup, _isolate_plugin_config, _isolate_runner_limit_override, _isolate_sase_home, _mock_system_clipboard, _module_scoped_runner, _package_scoped_runner, _pin_configured_timezone, _pin_terminal_environment, _publish_pytest_sandbox, _pytest, _reset_ace_shutdown_signal, _reset_link_follow_outcome_counts, _reset_project_tag_catalog_cache, _restore_workflow_metadata_derived_caches, _restore_working_directory, _sandbox_session_home, _scrub_ambient_tui_profiling_env, _session_scoped_runner, _sys_snapshot, _test_llm_bin, _use_placeholder_directory_map_assets, allow_axe_lifecycle_in_tests, cache, capfd, capfdbinary, caplog, capsys, capsysbinary, capteesys, class_mocker, cov, doctest_namespace, event_loop_policy, fake_plugin_commands, files_pane_enabled, gate_home, linecomp, log_dir, make_changespec, make_patch, mocker, module_mocker, monkeypatch, no_cover, package_mocker, platformdirs_isolated, project_display_case, pytestconfig, pytester, real_directory_map_assets, real_model_alias_defaults, real_plugin_config, record_property, record_testsuite_property, record_xml_attribute, recwarn, session_mocker, snapshot_check, subtests, testdir, testrun_uid, tmp_path, tmp_path_factory, tmpdir, tmpdir_factory, tz_divergence, unused_tcp_port, unused_tcp_port_factory, unused_udp_port, unused_udp_port_factory, worker_id
>       use 'pytest --fixtures [testpath]' for help on them.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/test_artifacts_beads_filtering_queries.py:99
============================= slowest 20 durations =============================
21.34s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
20.66s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
9.55s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
7.32s call     tests/test_project_display_presentation_audit.py::test_path_label_exemptions_name_existing_sites_and_rationales
7.16s call     tests/test_project_display_presentation_audit.py::test_project_labels_never_derive_from_paths
5.74s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
4.49s call     tests/test_gemini_active_surface_guard.py::test_no_gemini_cli_provider_surface_in_active_tree
3.16s call     tests/ace/tui/test_artifacts_beads_filtering_ui.py::test_bead_bar_geometry_is_unchanged_between_idle_and_editing
2.39s call     tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms
2.36s call     tests/ace/tui/test_artifacts_beads_filtering_ui.py::test_hide_closed_default_is_visible_and_clearable
2.22s call     tests/test_macro_terminology.py::test_macro_imports_avoid_xprompt_modules
2.19s call     tests/ace/tui/test_artifacts_beads_filtering_ui.py::test_changing_project_scope_keeps_idle_bead_bar_in_sync
2.09s call     tests/test_sase_turn_terminology.py::test_current_source_avoids_shell_concept_identifiers
2.01s call     tests/ace/tui/test_artifacts_beads_filtering_ui.py::test_committing_bead_query_updates_idle_bar
1.99s call     tests/test_macro_terminology.py::test_macro_source_avoids_xprompt_identifiers
1.84s call     tests/test_sase_turn_terminology.py::test_current_source_avoids_stale_shell_concept_phrases
1.80s call     tests/test_run_pytest_contention.py::test_only_the_controller_registers_the_recorder
1.78s call     tests/ace/tui/test_artifacts_beads_filtering_ui.py::test_clicking_idle_bead_bar_opens_the_filter_session
1.51s call     tests/test_agent_session_terminology.py::test_current_source_avoids_agent_family_identifiers
1.47s call     tests/test_agent_tribe_terminology.py::test_current_source_avoids_agent_tag_identifiers
=========================== short test summary info ============================
ERROR tests/ace/tui/test_artifacts_beads_filtering_queries.py::test_invalid_bead_filter_tokens_are_rejected
================== 1172 passed, 1 error in 191.98s (0:03:11) ===================
error: recipe `test-scoped` failed on line 712 with exit code 1
error: recipe `check` failed on line 993 with exit code 1
failed  exit=1  duration=575026ms
unattrib  24.8s
triage test (scoped): 1 NEW stopped
NEW test (scoped): ERROR tests/ace/tui/test_artifacts_beads_filtering_queries.py::test_invalid_bead_filter_tokens_are_rejected — recorded evidence; no owner
verdict: new_failures — 1 NEW; exit 1

