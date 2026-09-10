# Chat History - ace-run (sase-x7.4.r0--mon-4)

- **TIMESTAMP:** 2026-09-07 01:15:54 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** sase-x7.4.r0--mon-4

## Prompt

sase monitor start --command 'python3.14 /tmp/sase-x7.4-verify.py' --reason 'Verify the dispatch config repair, complete Telegram checks, and build and smoke-test the shared pending-action wheel cohort'

## Response

Running host-check-full: ['just', 'check-full']

tests/completion/test_zsh_smoke.py::test_dynamic_slot_fetches_fixture_candidates_and_caches
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask #zz-"ask #zzz-fixture-xprompt"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask %mo-"ask %model"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask @file:e-"ask @file:explicit:abc123"]
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=2625074) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 0 poisoning change(s) across 0 test(s); 52868 warming mutation(s) filtered; 453 cooling mutation(s) filtered; 1549 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.pytest_cache/sase-global-leaks.json -
============================= slowest 20 durations =============================
47.50s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
45.22s call     tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_runner_limit_write_requests_standard_agents_refresh
38.66s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
28.87s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
23.29s call     tests/attachments/test_markdown_pdf_properties.py::test_render_markdown_pdf_properties_smoke_when_tools_available[title: Tale PDF\ntier: tale\ngoal: Verify the card]
19.41s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
19.33s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
19.13s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_opens_preview_modal
18.93s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_skipped_editables_with_wheel_core_open_mixed_preview
18.11s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
15.20s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
14.15s call     tests/test_proc_env_isolation.py::test_sase_ml_file_families_ignore_inherited_live_proc_env
12.84s call     tests/test_global_state_leak_detector.py::test_report_only_mode_keeps_pytest_green_on_poison
11.38s call     tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
10.56s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_raises_and_restores_the_claim_when_the_supervisor_never_acknowledges
10.15s call     tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
10.06s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
9.89s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
9.64s call     tests/test_scratch_tmpdir_leak_regression.py::test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read
9.61s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_releases_a_fresh_numbered_claim_when_the_supervisor_never_acknowledges
========= 38952 passed, 14 skipped, 74 warnings in 2669.08s (0:44:29) ==========
recording: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260907T050504Z-2497558.json
baseline:  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/tests/perf/baselines/test_cost_baseline.json
timings:   /home/bryan/.sase/test-selection/gh_sase-org__sase/timings covers 3555/3556 files total=5885.253s cost-delta=+347.717s (+5.9%)
Test Cost Report
  record: 0bc0bc2a39200fb7
  recorded_at: 2026-09-07T05:05:04.275103+00:00
  host: athena
  mode: cost
  worker_count: 8

Summary
  per-test wall: 6232.971s
  per-test CPU: 3017.415s
  per-test idle: 3215.555s
  collection: 1236.222s
  worker wall: 23257.906s
  worker CPU: 16805.304s
  peak worker RSS KiB: 1,837,776 KiB
  median worker RSS KiB: 704,574 KiB
  post-collection worker RSS KiB: 705,108 KiB
  worker RSS curve: start=166,540 KiB, post_collection=705,108 KiB, median=704,574 KiB, peak=1,837,776 KiB, samples=413
  files: 3556
  nodes: 38965

Diff
  per-test wall: current 6232.971s; baseline 3719.000s; delta +2513.971 (+67.6%)
  per-test CPU: current 3017.415s; baseline n/a; delta n/a
  per-test idle: current 3215.555s; baseline n/a; delta n/a
  collection: current 1236.222s; baseline 27.600s; delta +1208.622 (+4379.1%)
  worker wall: current 23257.906s; baseline n/a; delta n/a
  worker CPU: current 16805.304s; baseline n/a; delta n/a
  peak worker RSS KiB: current 1,837,776 KiB; baseline 1,126,400 KiB; delta +711376.000 (+63.2%)
  median worker RSS KiB: current 704,574 KiB; baseline n/a; delta n/a
  post-collection worker RSS KiB: current 705,108 KiB; baseline n/a; delta n/a

Causes
  AcePage.__aenter__: 1085.435s (711x)  delta +695.435 (+178.3%)
  Textual App.run_test enter: 900.129s (3691x)  delta +478.129 (+113.3%)
  ACE settle_pilot: 552.820s (7399x)  delta n/a
  subprocess.run: 539.468s (41623x)  delta +279.468 (+107.5%)
  Pilot.pause(delay): 477.039s (14867x)  delta n/a
  Textual App.run_test exit: 73.907s (3691x)  delta n/a
  AcePage.__aexit__: 56.831s (709x)  delta n/a
  sase.main.parser.create_parser: 42.799s (1878x)  delta -17.201 (-28.7%)
  Pilot.pause(None): 42.499s (680x)  delta n/a
  YAML load: 24.608s (54700x)  delta -40.392 (-62.1%)
  sase.config.core.load_merged_config: 9.986s (25696x)  delta +9.986
  subprocess.Popen: 0.414s (479x)  delta n/a
  ACE pause_until_cpu_idle: 0.001s (2x)  delta n/a
  gettext.find: 0.000s (7x)  delta +0.000

Top 10 Files
  by wall:
      86.277s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      73.499s  tests/ace/tui/test_config_pane_widget_commit.py
      67.865s  tests/test_check_feature_flags_tool_run.py
      63.446s  tests/test_ace_testing.py
      59.909s  tests/ace/tui/test_plugins_browser_pane_loading.py
      53.794s  tests/ace/tui/test_axe_entry_editor_modal.py
      47.528s  tests/test_contract_manifest.py
      41.518s  tests/ace/tui/test_artifacts_scaffold.py
      38.805s  tests/ace/tui/test_agents_zoom_panel_files.py
      38.333s  tests/ace/tui/test_statistics_view_number_select.py
  by CPU:
      77.227s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      65.769s  tests/test_check_feature_flags_tool_run.py
      61.741s  tests/test_ace_testing.py
      55.467s  tests/ace/tui/test_plugins_browser_pane_loading.py
      51.314s  tests/ace/tui/test_axe_entry_editor_modal.py
      36.713s  tests/ace/tui/test_artifacts_scaffold.py
      36.535s  tests/ace/tui/test_xprompt_browser_load_keymap.py
      35.430s  tests/ace/tui/test_plugins_browser_pane_install.py
      32.776s  tests/ace/tui/test_statistics_view_number_select.py
      31.463s  tests/ace/tui/test_projects_pane.py
  by idle:
      47.509s  tests/test_contract_manifest.py
      45.343s  tests/ace/tui/test_config_pane_widget_commit.py
      34.662s  tests/test_procs_service.py
      34.647s  tests/test_plan_approval_responses.py
      34.513s  tests/monitor/test_monitor_start_ack.py
      26.186s  tests/ace/tui/test_agents_zoom_panel_files.py
      25.856s  tests/attachments/test_markdown_pdf_properties.py
      25.294s  tests/test_agent_names_extract_naming.py
      24.729s  tests/test_plan_gates_execution.py
      24.300s  tests/monitor/test_monitor_supervise_timeout.py
  by AcePage.__aenter__:
      57.558s    10x  tests/ace/tui/test_config_pane_widget_commit.py
      53.568s    37x  tests/test_ace_testing.py
      28.954s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
      27.857s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
      22.668s    15x  tests/ace/tui/test_artifacts_current_project_scope.py
      21.908s    12x  tests/ace/tui/test_projects_pane.py
      19.112s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
      18.900s    12x  tests/ace/tui/test_artifacts_scaffold.py
      18.761s    10x  tests/ace/tui/test_plugins_browser_pane_agent_clis.py
      18.093s    10x  tests/ace/tui/test_xprompt_browser_jump.py
  by Textual App.run_test enter:
      46.091s    10x  tests/ace/tui/test_config_pane_widget_commit.py
      38.497s    40x  tests/test_ace_testing.py
      20.619s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
      19.179s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
      13.042s    10x  tests/ace/tui/test_plugins_browser_pane_agent_clis.py
      12.874s    12x  tests/ace/tui/test_artifacts_scaffold.py
      12.289s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
      11.758s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
      11.331s     8x  tests/ace/tui/test_statistics_pane_filters.py
      11.280s     9x  tests/ace/tui/test_config_edit_modal_editors_widget.py
  by ACE settle_pilot:
      25.619s   143x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      22.225s    29x  tests/ace/tui/test_plugins_browser_pane_sase_update.py
      20.842s    22x  tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py
      15.111s    32x  tests/ace/tui/test_config_pane_widget.py
      15.044s    45x  tests/ace/tui/test_plugins_browser_pane_install.py
      13.537s    41x  tests/ace/tui/test_statistics_view_number_select.py
      12.507s    36x  tests/ace/tui/test_config_pane_widget_commit.py
      12.445s    86x  tests/ace/tui/test_plugins_browser_pane_loading.py
      11.710s    32x  tests/ace/tui/test_plugins_browser_pane_update.py
      11.699s    54x  tests/ace/tui/test_axe_entry_editor_modal.py
  by subprocess.run:
      47.469s     1x  tests/test_contract_manifest.py
      24.615s     4x  tests/attachments/test_markdown_pdf_properties.py
      17.570s     8x  tests/monitor/test_monitor_supervise_timeout.py
      11.571s    18x  tests/test_plan_approval_responses.py
       9.342s    14x  tests/test_plan_gates_execution.py
       6.906s    10x  tests/test_plan_gates_action_api.py
       6.614s    32x  tests/test_suite_gate_scoped_integration.py
       6.544s    11x  tests/test_bead/test_snooze_gate_actions.py
       6.254s    41x  tests/test_fork_workflow.py
       5.766s   916x  tests/sdd_store/test_materialize.py
  by Pilot.pause(delay):
      23.988s   286x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      14.676s    64x  tests/ace/tui/test_config_pane_widget.py
      13.493s    90x  tests/ace/tui/test_plugins_browser_pane_install.py
      12.442s    82x  tests/ace/tui/test_statistics_view_number_select.py
      11.442s   172x  tests/ace/tui/test_plugins_browser_pane_loading.py
      11.220s    72x  tests/ace/tui/test_config_pane_widget_commit.py
      10.864s    64x  tests/ace/tui/test_plugins_browser_pane_update.py
      10.389s    68x  tests/ace/tui/test_config_pane_widget_navigation.py
      10.197s   128x  tests/ace/tui/test_plugin_action_confirm_modal.py
      10.039s   108x  tests/ace/tui/test_axe_entry_editor_modal.py
  by Textual App.run_test exit:
       4.057s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
       3.642s    13x  tests/ace/tui/test_statistics_view_number_select.py
       1.597s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
       1.550s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
       1.501s     8x  tests/ace/tui/test_projects_pane_current_project_seed.py
       1.491s    10x  tests/ace/tui/test_xprompt_browser_jump.py
       1.458s    11x  tests/ace/tui/test_plugins_browser_pane_detail.py
       1.410s     7x  tests/ace/tui/test_config_pane_widget_navigation.py
       1.392s     6x  tests/ace/tui/test_statistics_pane_interactions.py
       1.386s     9x  tests/ace/tui/test_plugins_browser_pane_update.py
  by AcePage.__aexit__:
       4.173s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
       3.647s    13x  tests/ace/tui/test_statistics_view_number_select.py
       1.721s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
       1.609s    11x  tests/ace/tui/test_plugins_browser_pane_detail.py
       1.556s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
       1.528s     8x  tests/ace/tui/test_projects_pane_current_project_seed.py
       1.495s    10x  tests/ace/tui/test_xprompt_browser_jump.py
       1.444s     7x  tests/ace/tui/test_config_pane_widget_navigation.py
       1.394s     6x  tests/ace/tui/test_statistics_pane_interactions.py
       1.393s     9x  tests/ace/tui/test_plugins_browser_pane_update.py
  by sase.main.parser.create_parser:
       2.077s    20x  tests/main/test_parser_monitor.py
       1.784s     6x  tests/test_bead/test_cli_close_epic_symbols.py
       1.689s     9x  tests/main/test_snippet_cli_add.py
       1.574s     2x  tests/test_bead/test_cli_work_multi_target.py
       1.418s     7x  tests/main/test_memory_agent_docs.py
       1.346s    37x  tests/completion/test_update_refresh_soak.py
       1.101s    31x  tests/test_bead/test_cli_show_json.py
       1.058s    29x  tests/test_bead/test_cli_note.py
       0.968s    25x  tests/test_bead/test_cli_show.py
       0.898s    26x  tests/main/test_completion_handler.py
  by Pilot.pause(None):
       4.676s    39x  tests/test_notification_modal_scroll.py
       3.230s    44x  tests/test_models_panel_override_flows.py
       3.182s    67x  tests/test_models_panel_selector_builder.py
       2.474s    39x  tests/test_models_panel_jump.py
       2.154s    29x  tests/test_models_panel_edit.py
       1.896s     4x  tests/test_models_panel_threshold.py
       1.872s    53x  tests/pager/test_app.py
       1.783s    25x  tests/test_models_panel_edit_custom.py
       1.722s    36x  tests/test_command_palette_modal.py
       1.680s    32x  tests/test_model_picker_modal.py
  by YAML load:
       3.805s  5239x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
       1.335s  4914x  tests/main/test_init_skills_sources.py
       0.903s   941x  tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py
       0.740s  3426x  tests/main/test_init_memory_task_types_note.py
       0.724s   897x  tests/test_bead_xprompt_tags.py
       0.505s  2382x  tests/main/test_init_memory_plan.py
       0.469s    19x  tests/test_github_actions_ci_workflow.py
       0.456s   364x  tests/test_pooled_alias_single_consumption.py
       0.435s  2112x  tests/main/test_init_memory_commit.py
       0.406s  1940x  tests/main/test_init_memory_bead_note.py
  by sase.config.core.load_merged_config:
       0.237s     4x  tests/completion/test_emit_bash.py
       0.228s   310x  tests/test_bead/test_cli_show_style.py
       0.100s     4x  tests/completion/test_emit_zsh.py
       0.087s   120x  tests/test_bead/test_cli_show.py
       0.076s    23x  tests/test_plan_search_cli.py
       0.074s   190x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
       0.074s    64x  tests/main/test_parser_proc.py
       0.073s    35x  tests/ace/tui/test_config_pane_widget_navigation.py
       0.070s    44x  tests/ace/tui/test_admin_center_selection_resume.py
       0.069s    23x  tests/test_plan_validate_diagnostics.py
  by subprocess.Popen:
       0.031s    34x  tests/test_procs_service.py
       0.018s     3x  tests/test_axe_chop_preflight_policy.py
       0.017s    22x  tests/test_xprompt_directive_completion_parity.py
       0.012s    12x  tests/llm_provider/test_muse_artifacts.py
       0.011s    13x  tests/main/test_proc_handler_run.py
       0.008s     9x  tests/test_clan_summary_script_execution.py
       0.008s     5x  tests/test_axe_chop_result_protocol.py
       0.008s     9x  tests/ace/tui/test_session_proc_reporter.py
       0.008s    14x  tests/test_fork_workflow.py
       0.008s     4x  tests/test_axe_chop_name_collisions.py
  by ACE pause_until_cpu_idle:
       0.001s     1x  tests/test_ace_wait.py
       0.000s     1x  tests/test_a.py
  by gettext.find:
       0.000s     1x  tests/test_agent_restart_cli.py
       0.000s     1x  tests/agent_clis/test_cli.py
       0.000s     1x  tests/main/test_ace_handler.py
       0.000s     1x  tests/test_ci_bootstrap_sidecars_tool.py
       0.000s     1x  tests/test_run_pytest_contention.py
       0.000s     1x  tests/ace/tui/artifact_file_viewer/test_entrypoint.py
       0.000s     1x  tests/test_mobile_gateway.py
test cost budget regression: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260907T050504Z-2497558.json
budgets: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/tests/perf/baselines/test_cost_budgets.json
- [hard] collection_cpu_seconds (per worker): actual 85.398 exceeds budget 28.000 + 25% tolerance (35.000)
- [hard] total_file_cpu_seconds: actual 3017.415 exceeds budget 2100.000 + 25% tolerance (2625.000)
- [hard] causes.ace_page_enter.cpu: actual 1019.694 exceeds budget 740.000 + 25% tolerance (925.000)
- [hard] causes.ace_settle_pilot.cpu: actual 506.527 exceeds budget 320.000 + 25% tolerance (400.000)
- [hard] causes.pilot_pause_delay.cpu: actual 465.791 exceeds budget 290.000 + 25% tolerance (362.500)
- [hard] causes.subprocess_run.cpu: actual 40.230 exceeds budget 27.000 + 25% tolerance (33.750)
- [hard] causes.textual_app_run_test_enter.cpu: actual 850.438 exceeds budget 610.000 + 25% tolerance (762.500)
test cost budget advisories: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260907T050504Z-2497558.json
wall-clock overages usually mean the host was busy, not that the suite got more expensive; the cpu/count figures alongside each entry are contention-stable, so compare them to tell the two apart.
- [advisory] collection_seconds (per worker): actual 154.528 exceeds budget 60.000 + 15% tolerance (69.000) (cpu=683.183s)
- [advisory] total_file_wall_seconds: actual 6232.971 exceeds budget 4700.000 + 15% tolerance (5405.000) (cpu=3017.415s)
- [advisory] causes.ace_page_enter: actual 1085.435 exceeds budget 540.000 + 15% tolerance (621.000) (cpu=1019.694s, count=711)
- [advisory] causes.ace_settle_pilot: actual 552.820 exceeds budget 340.000 + 15% tolerance (391.000) (cpu=506.527s, count=7399)
- [advisory] causes.pilot_pause_delay: actual 477.039 exceeds budget 230.000 + 15% tolerance (264.500) (cpu=465.791s, count=14867)
- [advisory] causes.textual_app_run_test_enter: actual 900.129 exceeds budget 470.000 + 15% tolerance (540.500) (cpu=850.438s, count=3691)
- [advisory] causes.yaml_load: actual 24.608 exceeds budget 20.000 + 15% tolerance (23.000) (cpu=24.439s, count=54700)
error: recipe `test-cost` failed on line 422 with exit code 1
error: recipe `check-full` failed on line 684 with exit code 1

Running telegram-install: ['just', 'install']
Using CPython 3.14.7
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
uv pip install --python '.venv/bin/python' -e ".[dev]"
Resolved 62 packages in 213ms
   Building sase-telegram @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-telegram
Downloading sase-core-rs (9.6MiB)
 Downloaded sase-core-rs
      Built sase-telegram @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-telegram
Prepared 2 packages in 515ms
Installed 62 packages in 215ms
 + anyio==4.15.1
 + ast-serialize==0.9.0
 + attrs==26.1.0
 + bracex==3.0.1
 + certifi==2026.7.22
 + coverage==7.16.0
 + h11==0.16.0
 + httpcore==1.0.9
 + httpx==0.28.1
 + idna==3.19
 + iniconfig==2.3.0
 + jinja2==3.1.6
 + jsonschema==4.26.0
 + jsonschema-specifications==2025.9.1
 + librt==0.15.0
 + linkify-it-py==2.2.0
 + markdown-it-py==4.2.0
 + markupsafe==3.0.3
 + mdit-py-plugins==0.6.1
 + mdurl==0.1.2
 + mypy==2.3.1
 + mypy-extensions==1.1.0
 + packaging==26.3
 + pathspec==1.1.1
 + pillow==12.3.0
 + platformdirs==4.11.7
 + pluggy==1.6.0
 + pygments==2.21.0
 + pyinstrument==5.1.3
 + pytest==9.1.1
 + pytest-cov==7.1.0
 + pytest-mock==3.15.1
 + python-telegram-bot==22.8
 + pyyaml==6.0.3
 + referencing==0.37.0
 + rich==15.0.0
 + rpds-py==2026.6.3
 + ruamel-yaml==0.19.1
 + ruff==0.16.6
 + sase==0.17.1
 + sase-core-rs==0.32.34
 + sase-telegram==0.4.9 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-telegram)
 + schedule==1.2.2
 + textual==8.2.8
 + tree-sitter==0.26.0
 + tree-sitter-bash==0.25.1
 + tree-sitter-css==0.25.0
 + tree-sitter-go==0.25.0
 + tree-sitter-html==0.23.2
 + tree-sitter-java==0.23.5
 + tree-sitter-javascript==0.25.0
 + tree-sitter-json==0.24.8
 + tree-sitter-markdown==0.5.1
 + tree-sitter-python==0.25.0
 + tree-sitter-regex==0.25.0
 + tree-sitter-rust==0.24.2
 + tree-sitter-sql==0.3.11
 + tree-sitter-toml==0.7.0
 + tree-sitter-xml==0.7.0
 + tree-sitter-yaml==0.7.2
 + typing-extensions==4.16.0
 + wcmatch==11.0.1
just _install-local-sase-core
Resolved 1 package in 88ms
Installed 1 package in 12ms
 + maturin==1.15.0
cd '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-core/crates/sase_core_py' && VIRTUAL_ENV='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-telegram/.venv' PYO3_USE_ABI3_FORWARD_COMPATIBILITY=1 '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-telegram/.venv/bin/maturin' develop --release
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-telegram/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling pyo3-build-config v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
   Compiling pyo3-macros v0.22.6
   Compiling sase_core_py v0.32.33 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 3m 02s
📦 Built wheel for abi3 Python ≥ 3.12 to /tmp/.tmpmYOVuv/sase_core_rs-0.32.33-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.32.33
uv pip install --python '.venv/bin/python' --no-deps -e '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33'
Resolved 1 package in 8ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33
Prepared 1 package in 768ms
Uninstalled 1 package in 143ms
Installed 1 package in 6ms
 - sase==0.17.1
 + sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33)

Running telegram-check: ['just', 'check']
test_inbound.py::TestCustomCommandDispatch::test_registration_puts_sorted_custom_commands_before_builtins PASSED [ 74%]
tests/test_inbound.py::TestCustomCommandDispatch::test_configured_first_order_invalidates_recent_old_fingerprint PASSED [ 74%]
tests/test_inbound.py::TestCustomCommandDelivery::test_message_output_is_formatted_and_sent PASSED [ 74%]
tests/test_inbound.py::TestCustomCommandDelivery::test_nonzero_exit_sends_bounded_expandable_stderr PASSED [ 74%]
tests/test_inbound.py::TestCustomCommandDelivery::test_timeout_reports_configured_duration PASSED [ 74%]
tests/test_inbound.py::TestCustomCommandDelivery::test_empty_stdout_reports_empty_result PASSED [ 75%]
tests/test_inbound.py::TestCustomCommandDelivery::test_pdf_conversion_failure_falls_back_to_markdown PASSED [ 75%]
tests/test_inbound.py::TestCustomCommandDelivery::test_pdf_output_uses_safe_filename_and_truncated_caption PASSED [ 75%]
tests/test_integration.py::TestOutboundIntegration::test_first_run_initializes_without_sending PASSED [ 75%]
tests/test_integration.py::TestOutboundIntegration::test_lock_held_outputs_skip_summary PASSED [ 75%]
tests/test_integration.py::TestOutboundIntegration::test_sends_notification PASSED [ 75%]
tests/test_integration.py::TestOutboundIntegration::test_saves_pending_action_for_plan_approval PASSED [ 76%]
tests/test_integration.py::TestOutboundIntegration::test_saves_pending_action_for_launch_approval PASSED [ 76%]
tests/test_integration.py::TestOutboundIntegration::test_registers_telegram_transport_in_shared_store PASSED [ 76%]
tests/test_integration.py::TestOutboundIntegration::test_advances_high_water_mark_per_notification PASSED [ 76%]
tests/test_integration.py::TestOutboundIntegration::test_failed_send_does_not_advance_high_water_mark PASSED [ 76%]
tests/test_integration.py::TestOutboundIntegration::test_dry_run_prints_without_sending PASSED [ 77%]
tests/test_integration.py::TestInboundIntegration::test_no_updates_exits_cleanly PASSED [ 77%]
tests/test_integration.py::TestInboundIntegration::test_custom_commands_load_once_and_dispatch PASSED [ 77%]
tests/test_integration.py::TestInboundIntegration::test_shared_store_handled_dismisses_keyboard PASSED [ 77%]
tests/test_integration.py::TestInboundIntegration::test_callback_on_already_handled_action_is_rejected PASSED [ 77%]
tests/test_integration.py::TestInboundIntegration::test_saves_offset_after_processing PASSED [ 77%]
tests/test_integration.py::TestInboundIntegration::test_photo_message_downloads_and_launches_agent PASSED [ 78%]
tests/test_integration.py::TestInboundIntegration::test_photo_album_stages_then_flushes_one_launch FAILED [ 78%]
tests/test_justfile.py::test_local_sase_source_override_wins_over_default_candidates PASSED [ 78%]
tests/test_justfile.py::test_ci_dependency_checkout_is_used_when_local_sase_checkouts_are_absent PASSED [ 78%]
tests/test_justfile.py::test_local_sase_core_source_override_wins_over_default_candidates PASSED [ 78%]
tests/test_justfile.py::test_sibling_sase_core_checkout_is_the_default_for_local_development PASSED [ 78%]
tests/test_justfile.py::test_ci_dependency_sase_core_checkout_is_used_when_sibling_is_absent PASSED [ 79%]
tests/test_justfile.py::test_sibling_checkout_is_used_when_ci_checkout_is_absent PASSED [ 79%]
tests/test_justfile.py::test_linked_workspace_checkout_is_the_final_default PASSED [ 79%]
tests/test_justfile.py::test_linked_workspace_checkout_wins_over_ci_dependency_checkout PASSED [ 79%]
tests/test_justfile.py::test_install_dry_run_installs_project_before_local_sase PASSED [ 79%]
tests/test_justfile.py::test_local_sase_core_install_dry_run_uses_maturin_develop PASSED [ 79%]
tests/test_justfile.py::test_setup_dry_run_overlays_local_sase PASSED    [ 80%]
tests/test_justfile.py::test_ci_pins_authenticated_just_setup PASSED     [ 80%]
tests/test_outbound.py::TestGetUnsentNotifications::test_no_file_returns_empty_and_initializes PASSED [ 80%]
tests/test_outbound.py::TestGetUnsentNotifications::test_filters_correctly PASSED [ 80%]
tests/test_outbound.py::TestGetUnsentNotifications::test_filters_silent_notifications PASSED [ 80%]
tests/test_outbound.py::TestMarkSent::test_writes_timestamp PASSED       [ 80%]
tests/test_outbound.py::TestMarkSent::test_empty_list_noop PASSED        [ 81%]
tests/test_outbound.py::test_resurfaced_generation_and_equal_timestamp_ids_use_activity_cursor PASSED [ 81%]
tests/test_outbound.py::TestIsDiffFile::test_diff_extension PASSED       [ 81%]
tests/test_outbound.py::TestIsDiffFile::test_non_diff_extension PASSED   [ 81%]
tests/test_outbound.py::TestIsDiffFile::test_case_insensitive PASSED     [ 81%]
tests/test_outbound.py::TestDisplayFilenames::test_make_response_only_file_humanizes_chat_stem PASSED [ 81%]
tests/test_outbound.py::TestIsImageFile::test_known_extensions PASSED    [ 82%]
tests/test_outbound.py::TestIsImageFile::test_non_image_extension PASSED [ 82%]
tests/test_outbound.py::TestIsAnimationFile::test_gif_extension PASSED   [ 82%]
tests/test_outbound.py::TestIsAnimationFile::test_non_animation_extension PASSED [ 82%]
tests/test_outbound.py::TestIsVideoFile::test_known_extensions PASSED    [ 82%]
tests/test_outbound.py::TestIsVideoFile::test_case_insensitive PASSED    [ 82%]
tests/test_outbound.py::TestIsVideoFile::test_non_video_extension PASSED [ 83%]
tests/test_outbound.py::TestIsPdfFile::test_pdf_extension PASSED         [ 83%]
tests/test_outbound.py::TestIsPdfFile::test_case_insensitive PASSED      [ 83%]
tests/test_outbound.py::TestIsPdfFile::test_non_pdf_extension PASSED     [ 83%]
tests/test_outbound.py::TestAppendDiffToMarkdown::test_appends_diff_content PASSED [ 83%]
tests/test_outbound.py::TestAppendDiffToMarkdown::test_skips_empty_diff PASSED [ 83%]
tests/test_outbound.py::TestAppendDiffToMarkdown::test_skips_nonexistent_diff PASSED [ 84%]
tests/test_outbound.py::TestPrependCommitMessageToMarkdown::test_appends_full_multiline_message PASSED [ 84%]
tests/test_outbound.py::TestPrependCommitMessageToMarkdown::test_uses_fence_longer_than_commit_message_backticks PASSED [ 84%]
tests/test_outbound.py::TestRunOutboundAttachments::test_workflow_complete_pdf_sends_document_without_conversion PASSED [ 84%]
tests/test_outbound.py::TestRunOutboundAttachments::test_plan_pdf_with_unusable_original_name_uses_generated_filename[missing] PASSED [ 84%]
tests/test_outbound.py::TestRunOutboundAttachments::test_plan_pdf_with_unusable_original_name_uses_generated_filename[empty] PASSED [ 85%]
tests/test_outbound.py::TestRunOutboundAttachments::test_plan_pdf_with_unusable_original_name_uses_generated_filename[blank] PASSED [ 85%]
tests/test_outbound.py::TestRunOutboundAttachments::test_plan_pdf_with_unusable_original_name_uses_generated_filename[root] PASSED [ 85%]
tests/test_outbound.py::TestRunOutboundAttachments::test_plan_pdf_with_unusable_original_name_uses_generated_filename[dot] PASSED [ 85%]
tests/test_outbound.py::TestRunOutboundAttachments::test_plan_pdf_with_unusable_original_name_uses_generated_filename[control-character] PASSED [ 85%]
tests/test_outbound.py::TestRunOutboundAttachments::test_workflow_complete_image_sends_photo_not_document PASSED [ 85%]
tests/test_outbound.py::TestRunOutboundAttachments::test_workflow_complete_gif_sends_animation_not_photo PASSED [ 86%]
tests/test_outbound.py::TestRunOutboundAttachments::test_workflow_complete_sends_one_animation_for_each_media_pair PASSED [ 86%]
tests/test_outbound.py::TestRunOutboundAttachments::test_workflow_complete_video_sends_video_not_document PASSED [ 86%]
tests/test_outbound.py::TestRunOutboundAttachments::test_selected_media_failure_falls_back_to_document PASSED [ 86%]
tests/test_outbound.py::TestRunOutboundAttachments::test_mixed_chat_diff_pdf_and_image_sends_expected_attachments PASSED [ 86%]
tests/test_outbound.py::TestRunOutboundAttachments::test_unembedded_diff_uses_humanized_document_filename PASSED [ 86%]
tests/test_outbound.py::TestRunOutboundAttachments::test_chat_pdf_embeds_full_commit_message_before_conversion PASSED [ 87%]
tests/test_outbound.py::TestRunOutboundAttachments::test_dry_run_lists_pdf_attachment_without_research_section PASSED [ 87%]
tests/test_pdf_convert.py::test_md_to_pdf_delegates_to_core_renderer PASSED [ 87%]
tests/test_pdf_convert.py::test_md_to_pdf_routes_launch_preview_to_dedicated_renderer PASSED [ 87%]
tests/test_pdf_convert.py::test_md_to_pdf_returns_none_for_non_markdown PASSED [ 87%]
tests/test_pdf_convert.py::test_md_to_pdf_returns_none_when_core_renderer_fails PASSED [ 87%]
tests/test_pending_actions.py::TestPendingActions::test_add_and_get PASSED [ 88%]
tests/test_pending_actions.py::TestPendingActions::test_get_missing PASSED [ 88%]
tests/test_pending_actions.py::TestPendingActions::test_remove_existing PASSED [ 88%]
tests/test_pending_actions.py::TestPendingActions::test_remove_missing PASSED [ 88%]
tests/test_pending_actions.py::TestPendingActions::test_list_all PASSED  [ 88%]
tests/test_pending_actions.py::TestPendingActions::test_cleanup_stale PASSED [ 88%]
tests/test_question_flow.py::test_single_select_completes_single_question PASSED [ 89%]
tests/test_question_flow.py::test_multi_select_toggles_then_advances_and_completes PASSED [ 89%]
tests/test_question_flow.py::test_save_load_clear_progress_roundtrip PASSED [ 89%]
tests/test_question_flow.py::test_load_progress_initializes_from_request PASSED [ 89%]
tests/test_question_flow.py::test_load_question_request PASSED           [ 89%]
tests/test_question_flow.py::test_neutral_question_paths_project_payload_and_response PASSED [ 89%]
tests/test_rate_limit.py::TestRateLimit::test_allows_under_limit PASSED  [ 90%]
tests/test_rate_limit.py::TestRateLimit::test_blocks_over_limit PASSED   [ 90%]
tests/test_rate_limit.py::TestRateLimit::test_wait_time_zero_when_under_limit PASSED [ 90%]
tests/test_rate_limit.py::TestRateLimit::test_wait_time_positive_when_over_limit PASSED [ 90%]
tests/test_rate_limit.py::TestRateLimit::test_old_timestamps_pruned PASSED [ 90%]
tests/test_rate_limit.py::TestRateLimit::test_custom_config_via_env PASSED [ 90%]
tests/test_show_entities.py::test_forced_tribe_is_casefolded_and_bypasses_other_lookups PASSED [ 91%]
tests/test_show_entities.py::test_invalid_forced_tribe_raises_friendly_domain_error PASSED [ 91%]
tests/test_show_entities.py::test_exact_agent_wins_and_detects_also_a_tribe PASSED [ 91%]
tests/test_show_entities.py::test_exact_entry_fallback_resolves_clan_and_family_members_as_agents PASSED [ 91%]
tests/test_show_entities.py::test_clan_then_family_precedence PASSED     [ 91%]
tests/test_show_entities.py::test_bare_known_tribe_resolves_after_group_lookups PASSED [ 91%]
tests/test_show_entities.py::test_not_found_suggestions_cover_each_kind_and_are_limited PASSED [ 92%]
tests/test_show_entities.py::test_kinship_index_counts_unique_members_and_progress PASSED [ 92%]
tests/test_show_entities.py::test_clan_attribute_wiring_uses_member_metadata PASSED [ 92%]
tests/test_show_format.py::test_detail_rows_prefers_patch_name_and_labels_patch PASSED [ 92%]
tests/test_show_format.py::test_detail_rows_accepts_legacy_changespec_name PASSED [ 92%]
tests/test_show_format.py::test_agent_view_escapes_html_and_includes_kinship_rows_and_jumps PASSED [ 93%]
tests/test_show_format.py::test_agent_view_renders_structured_outputs_inline PASSED [ 93%]
tests/test_show_format.py::test_clan_view_formats_summary_rollup_archived_member_and_complete_fork PASSED [ 93%]
tests/test_show_format.py::test_incomplete_large_clan_omits_fork_and_chunks_with_explicit_truncation PASSED [ 93%]
tests/test_show_format.py::test_family_view_marks_active_member_and_shows_activity_prompt_and_outcome PASSED [ 93%]
tests/test_show_format.py::test_tribe_view_groups_clans_families_and_standalone_agents PASSED [ 93%]
tests/test_show_format.py::test_index_and_not_found_views_produce_mobile_open_specs PASSED [ 94%]
tests/test_show_format.py::test_index_caps_buttons_and_states_the_truncation PASSED [ 94%]
tests/test_snooze_resurface_e2e.py::test_snoozed_before_first_delivery_is_delivered_once_after_resurfacing PASSED [ 94%]
tests/test_snooze_resurface_e2e.py::test_previously_delivered_row_crosses_the_migrated_cursor_once PASSED [ 94%]
tests/test_snooze_resurface_e2e.py::test_dismissed_and_unmuted_snoozes_never_produce_a_new_generation PASSED [ 94%]
tests/test_snooze_resurface_e2e.py::test_simultaneous_resurface_events_are_each_delivered_oldest_first PASSED [ 94%]
tests/test_telegram_client.py::TestSplitMessage::test_short_message_one_chunk PASSED [ 95%]
tests/test_telegram_client.py::TestSplitMessage::test_splits_on_newline PASSED [ 95%]
tests/test_telegram_client.py::TestSplitMessage::test_splits_on_space_when_no_newline PASSED [ 95%]
tests/test_telegram_client.py::TestSplitMessage::test_hard_split_when_no_break_point PASSED [ 95%]
tests/test_telegram_client.py::TestSplitMessage::test_respects_custom_limit PASSED [ 95%]
tests/test_telegram_client.py::TestSplitMessage::test_strips_leading_newlines_after_split PASSED [ 95%]
tests/test_telegram_client.py::TestWithRetry::test_retries_on_retry_after PASSED [ 96%]
tests/test_telegram_client.py::TestWithRetry::test_retries_on_timed_out PASSED [ 96%]
tests/test_telegram_client.py::TestWithRetry::test_retries_on_network_error PASSED [ 96%]
tests/test_telegram_client.py::TestWithRetry::test_does_not_retry_on_bad_request PASSED [ 96%]
tests/test_telegram_client.py::TestWithRetry::test_gives_up_after_max_retries PASSED [ 96%]
tests/test_telegram_client.py::TestWithRetry::test_retry_after_propagates_when_max_exceeded PASSED [ 96%]
tests/test_telegram_client.py::TestSendMessage::test_single_chunk_passes_all_kwargs PASSED [ 97%]
tests/test_telegram_client.py::TestSendMessage::test_long_message_splits_and_attaches_markup_only_to_last PASSED [ 97%]
tests/test_telegram_client.py::TestSendMessage::test_parse_mode_fallback_on_failure PASSED [ 97%]
tests/test_telegram_client.py::TestSendMessage::test_no_fallback_when_parse_mode_unset PASSED [ 97%]
tests/test_telegram_client.py::TestSendDocument::test_delegates_to_bot PASSED [ 97%]
tests/test_telegram_client.py::TestSendDocument::test_delegates_filename_to_bot PASSED [ 97%]
tests/test_telegram_client.py::TestSendPhoto::test_delegates_to_bot PASSED [ 98%]
tests/test_telegram_client.py::TestSendAnimation::test_delegates_to_bot PASSED [ 98%]
tests/test_telegram_client.py::TestSendVideo::test_delegates_to_bot PASSED [ 98%]
tests/test_telegram_client.py::TestGetUpdates::test_delegates_to_bot PASSED [ 98%]
tests/test_telegram_client.py::TestAnswerCallbackQuery::test_delegates_to_bot PASSED [ 98%]
tests/test_telegram_client.py::TestEditMessageReplyMarkup::test_delegates_to_bot PASSED [ 98%]
tests/test_telegram_client.py::TestEditMessageReplyMarkup::test_can_clear_markup PASSED [ 99%]
tests/test_telegram_client.py::TestEditMessageText::test_delegates_to_bot PASSED [ 99%]
tests/test_telegram_client.py::TestEditMessageText::test_parse_mode_fallback_on_failure PASSED [ 99%]
tests/test_telegram_client.py::TestSetMyCommands::test_registers_bot_commands PASSED [ 99%]
tests/test_telegram_client.py::TestSetMyCommands::test_empty_list PASSED [ 99%]
tests/test_telegram_client.py::TestDownloadFile::test_downloads_to_destination PASSED [100%]

=================================== FAILURES ===================================
____ TestInboundIntegration.test_photo_album_stages_then_flushes_one_launch ____

self = <tests.test_integration.TestInboundIntegration object at 0x7f5d59a2d9d0>
mock_tg = <MagicMock name='telegram_client' id='140038639385440'>
mock_launch = <MagicMock name='_launch_agent' id='140038639380736'>

    @patch("sase_telegram.scripts.sase_tg_inbound._launch_agent")
    @patch("sase_telegram.scripts.sase_tg_inbound.telegram_client")
    def test_photo_album_stages_then_flushes_one_launch(
        self,
        mock_tg: MagicMock,
        mock_launch: MagicMock,
    ) -> None:
        """Media-group photos become one later launch containing both paths."""
        from sase_telegram.scripts import sase_tg_inbound as inbound
    
        def _download(_file_id: str, dest: Path) -> None:
            dest.write_text("image")
    
        mock_tg.download_file.side_effect = _download
        first = SimpleNamespace(file_id="album_one_12345678")
        second = SimpleNamespace(file_id="album_two_12345678")
        message1 = SimpleNamespace(
            photo=[first],
            caption="Compare these",
            caption_entities=None,
            media_group_id="album-1",
            message_id=10,
            chat=SimpleNamespace(id=12345),
            text=None,
            document=None,
        )
        message2 = SimpleNamespace(
            photo=[second],
            caption=None,
            caption_entities=None,
            media_group_id="album-1",
            message_id=11,
            chat=SimpleNamespace(id=12345),
            text=None,
            document=None,
        )
        mock_tg.get_updates.return_value = [
            SimpleNamespace(update_id=800, callback_query=None, message=message1),
            SimpleNamespace(update_id=801, callback_query=None, message=message2),
        ]
    
        with (
            patch.object(inbound, "IMAGES_DIR", IMAGES_TEST_DIR),
            patch.object(inbound, "_register_commands_if_needed"),
            patch.object(
                inbound.time,
                "time",
                side_effect=[100.0, 100.5, 100.5, 100.5, 100.5],
            ),
        ):
>           assert inbound_main(["--once"]) == 0
                   ^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_integration.py:762: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase_telegram/scripts/sase_tg_inbound.py:4425: in main
    _flush_ready_media_groups()
src/sase_telegram/scripts/sase_tg_inbound.py:566: in _flush_ready_media_groups
    now = time.time()
          ^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1176: in __call__
    return self._mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1180: in _mock_call
    return self._execute_mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <MagicMock name='time' id='140038639381744'>, args = (), kwargs = {}

    def _execute_mock_call(self, /, *args, **kwargs):
        # separate from _increment_mock_call so that awaited functions are
        # executed separately from their call, also AsyncMock overrides this method
    
        effect = self.side_effect
        if effect is not None:
            if _is_exception(effect):
                raise effect
            elif not _callable(effect):
>               result = next(effect)
                         ^^^^^^^^^^^^
E               StopIteration

/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1243: StopIteration
=============================== warnings summary ===============================
tests/test_telegram_client.py: 11 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-telegram/.venv/lib/python3.14/site-packages/telegram/error.py:243: PTBDeprecationWarning: Deprecated since version v22.2: In a future major version attribute `retry_after` will be of type `datetime.timedelta`. You can opt-in early by setting `PTB_TIMEDELTA=true` or ``PTB_TIMEDELTA=1`` as an environment variable.
    return get_timedelta_value(  # type: ignore[return-value]

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
=========================== short test summary info ============================
FAILED tests/test_integration.py::TestInboundIntegration::test_photo_album_stages_then_flushes_one_launch
============ 1 failed, 586 passed, 11 warnings in 170.86s (0:02:50) ============
error: recipe `test` failed on line 80 with exit code 1

Running core-wheel: ['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/bin/maturin', 'build', '--release', '--interpreter', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/bin/python', '--out', '/tmp/sase-x7.4-verification-r6/wheels']
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling pyo3-build-config v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
   Compiling pyo3-macros v0.22.6
   Compiling sase_core_py v0.32.33 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 3m 03s
📦 Built wheel for abi3 Python ≥ 3.12 to /tmp/sase-x7.4-verification-r6/wheels/sase_core_rs-0.32.33-cp312-abi3-manylinux_2_39_x86_64.whl

Running host-wheel: ['uv', 'build', '--wheel', '--out-dir', '/tmp/sase-x7.4-verification-r6/wheels']
Building wheel...
Successfully built /tmp/sase-x7.4-verification-r6/wheels/sase-0.17.1-py3-none-any.whl

Running telegram-wheel: ['uv', 'build', '--wheel', '--out-dir', '/tmp/sase-x7.4-verification-r6/wheels']
Building wheel...
Successfully built /tmp/sase-x7.4-verification-r6/wheels/sase_telegram-0.4.9-py3-none-any.whl

Running smoke-env-3.12: ['uv', 'venv', '--python', '3.12', '/tmp/sase-x7.4-verification-r6/smoke-3.12']
Using CPython 3.12.13
Creating virtual environment at: /tmp/sase-x7.4-verification-r6/smoke-3.12
Activate with: source /tmp/sase-x7.4-verification-r6/smoke-3.12/bin/activate

Running smoke-install-3.12: ['uv', 'pip', 'install', '--python', '/tmp/sase-x7.4-verification-r6/smoke-3.12/bin/python', '/tmp/sase-x7.4-verification-r6/wheels/sase-0.17.1-py3-none-any.whl', '/tmp/sase-x7.4-verification-r6/wheels/sase_core_rs-0.32.33-cp312-abi3-manylinux_2_39_x86_64.whl', '/tmp/sase-x7.4-verification-r6/wheels/sase_telegram-0.4.9-py3-none-any.whl']
Using Python 3.12.13 environment at: /tmp/sase-x7.4-verification-r6/smoke-3.12
Resolved 51 packages in 11ms
Prepared 3 packages in 403ms
warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
Installed 51 packages in 266ms
 + anyio==4.15.1
 + attrs==26.1.0
 + bracex==3.0.1
 + certifi==2026.7.22
 + h11==0.16.0
 + httpcore==1.0.9
 + httpx==0.28.1
 + idna==3.19
 + jinja2==3.1.6
 + jsonschema==4.26.0
 + jsonschema-specifications==2025.9.1
 + linkify-it-py==2.2.0
 + markdown-it-py==4.2.0
 + markupsafe==3.0.3
 + mdit-py-plugins==0.6.1
 + mdurl==0.1.2
 + packaging==26.3
 + pillow==12.3.0
 + platformdirs==4.11.7
 + pluggy==1.6.0
 + pygments==2.21.0
 + pyinstrument==5.1.3
 + python-telegram-bot==22.8
 + pyyaml==6.0.3
 + referencing==0.37.0
 + rich==15.0.0
 + rpds-py==2026.6.3
 + ruamel-yaml==0.19.1
 + sase==0.17.1 (from file:///tmp/sase-x7.4-verification-r6/wheels/sase-0.17.1-py3-none-any.whl)
 + sase-core-rs==0.32.33 (from file:///tmp/sase-x7.4-verification-r6/wheels/sase_core_rs-0.32.33-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-telegram==0.4.9 (from file:///tmp/sase-x7.4-verification-r6/wheels/sase_telegram-0.4.9-py3-none-any.whl)
 + schedule==1.2.2
 + textual==8.2.8
 + tree-sitter==0.26.0
 + tree-sitter-bash==0.25.1
 + tree-sitter-css==0.25.0
 + tree-sitter-go==0.25.0
 + tree-sitter-html==0.23.2
 + tree-sitter-java==0.23.5
 + tree-sitter-javascript==0.25.0
 + tree-sitter-json==0.24.8
 + tree-sitter-markdown==0.5.1
 + tree-sitter-python==0.25.0
 + tree-sitter-regex==0.25.0
 + tree-sitter-rust==0.24.2
 + tree-sitter-sql==0.3.11
 + tree-sitter-toml==0.7.0
 + tree-sitter-xml==0.7.0
 + tree-sitter-yaml==0.7.2
 + typing-extensions==4.16.0
 + wcmatch==11.0.1

Running wheel-smoke-3.12: ['/tmp/sase-x7.4-verification-r6/smoke-3.12/bin/python', '-I', '/tmp/sase-x7.4-wheel-smoke.py']
{"versions": {"sase": "0.17.1", "sase-core-rs": "0.32.33", "sase-telegram": "0.4.9"}, "modules": {"core": "/tmp/sase-x7.4-verification-r6/smoke-3.12/lib/python3.12/site-packages/sase_core_rs/__init__.py", "host": "/tmp/sase-x7.4-verification-r6/smoke-3.12/lib/python3.12/site-packages/sase/notifications/pending_actions.py", "telegram": "/tmp/sase-x7.4-verification-r6/smoke-3.12/lib/python3.12/site-packages/sase_telegram/pending_actions.py"}, "result": "passed"}

Running smoke-env-3.14: ['uv', 'venv', '--python', '3.14', '/tmp/sase-x7.4-verification-r6/smoke-3.14']
Using CPython 3.14.7
Creating virtual environment at: /tmp/sase-x7.4-verification-r6/smoke-3.14
Activate with: source /tmp/sase-x7.4-verification-r6/smoke-3.14/bin/activate

Running smoke-install-3.14: ['uv', 'pip', 'install', '--python', '/tmp/sase-x7.4-verification-r6/smoke-3.14/bin/python', '/tmp/sase-x7.4-verification-r6/wheels/sase-0.17.1-py3-none-any.whl', '/tmp/sase-x7.4-verification-r6/wheels/sase_core_rs-0.32.33-cp312-abi3-manylinux_2_39_x86_64.whl', '/tmp/sase-x7.4-verification-r6/wheels/sase_telegram-0.4.9-py3-none-any.whl']
Using Python 3.14.7 environment at: /tmp/sase-x7.4-verification-r6/smoke-3.14
Resolved 51 packages in 9ms
warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
Installed 51 packages in 323ms
 + anyio==4.15.1
 + attrs==26.1.0
 + bracex==3.0.1
 + certifi==2026.7.22
 + h11==0.16.0
 + httpcore==1.0.9
 + httpx==0.28.1
 + idna==3.19
 + jinja2==3.1.6
 + jsonschema==4.26.0
 + jsonschema-specifications==2025.9.1
 + linkify-it-py==2.2.0
 + markdown-it-py==4.2.0
 + markupsafe==3.0.3
 + mdit-py-plugins==0.6.1
 + mdurl==0.1.2
 + packaging==26.3
 + pillow==12.3.0
 + platformdirs==4.11.7
 + pluggy==1.6.0
 + pygments==2.21.0
 + pyinstrument==5.1.3
 + python-telegram-bot==22.8
 + pyyaml==6.0.3
 + referencing==0.37.0
 + rich==15.0.0
 + rpds-py==2026.6.3
 + ruamel-yaml==0.19.1
 + sase==0.17.1 (from file:///tmp/sase-x7.4-verification-r6/wheels/sase-0.17.1-py3-none-any.whl)
 + sase-core-rs==0.32.33 (from file:///tmp/sase-x7.4-verification-r6/wheels/sase_core_rs-0.32.33-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-telegram==0.4.9 (from file:///tmp/sase-x7.4-verification-r6/wheels/sase_telegram-0.4.9-py3-none-any.whl)
 + schedule==1.2.2
 + textual==8.2.8
 + tree-sitter==0.26.0
 + tree-sitter-bash==0.25.1
 + tree-sitter-css==0.25.0
 + tree-sitter-go==0.25.0
 + tree-sitter-html==0.23.2
 + tree-sitter-java==0.23.5
 + tree-sitter-javascript==0.25.0
 + tree-sitter-json==0.24.8
 + tree-sitter-markdown==0.5.1
 + tree-sitter-python==0.25.0
 + tree-sitter-regex==0.25.0
 + tree-sitter-rust==0.24.2
 + tree-sitter-sql==0.3.11
 + tree-sitter-toml==0.7.0
 + tree-sitter-xml==0.7.0
 + tree-sitter-yaml==0.7.2
 + typing-extensions==4.16.0
 + wcmatch==11.0.1

Running wheel-smoke-3.14: ['/tmp/sase-x7.4-verification-r6/smoke-3.14/bin/python', '-I', '/tmp/sase-x7.4-wheel-smoke.py']
{"versions": {"sase": "0.17.1", "sase-core-rs": "0.32.33", "sase-telegram": "0.4.9"}, "modules": {"core": "/tmp/sase-x7.4-verification-r6/smoke-3.14/lib/python3.14/site-packages/sase_core_rs/__init__.py", "host": "/tmp/sase-x7.4-verification-r6/smoke-3.14/lib/python3.14/site-packages/sase/notifications/pending_actions.py", "telegram": "/tmp/sase-x7.4-verification-r6/smoke-3.14/lib/python3.14/site-packages/sase_telegram/pending_actions.py"}, "result": "passed"}

Failed steps: ['host-check-full', 'telegram-check']

