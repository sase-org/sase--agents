#gh:gh_sase-org__sase It looks like the `just test` command is failing (see the output below). Can you help me diagnose the root cause of this issue and fix it? #plan #m_opus 
```
=============================================================================== slowest 20 durations ===============================================================================
151.95s call     tests/test_dismissed_bundle_persistence.py::test_save_dismissed_bundle_is_fast_with_many_existing_bundles
64.52s call     tests/test_suite_gate_integration.py::test_scaled_suite_runs_share_capacity_and_release_after_sigkill
42.58s call     tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout
38.17s call     tests/test_dismissed_bundle_persistence.py::test_bundle_no_limit
14.38s call     tests/agents_sync/test_cross_machine_e2e.py::test_three_identities_converge_and_localize_through_non_fast_forward_race
11.12s call     tests/test_markdown_pdf.py::test_render_launch_preview_pdf_smoke_when_tools_available
11.01s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
8.62s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
8.40s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
8.15s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
8.14s call     tests/ace/tui/test_agents_zoom_panel_search.py::test_zoom_search_structural_key_exits_and_then_pages_file
7.97s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
7.91s call     tests/test_mobile_helper_beads.py::test_beads_list_bridge_uses_remembered_device_project_context
7.80s call     tests/fakey/test_runner_slots_e2e.py::test_fakey_agents_respect_cap_and_release_in_fifo_order
7.57s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
7.30s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot
7.24s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
6.92s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
6.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_clan_tree_fold_levels_png_snapshots
6.45s setup    tests/test_bead/test_cli_show_compact.py::test_show_compact_color_modes_override_non_tty
============================================================================= short test summary info ==============================================================================
FAILED tests/test_suite_gate_integration.py::test_scaled_suite_runs_share_capacity_and_release_after_sigkill - subprocess.TimeoutExpired: Command '['/home/bryan/projects/github/sase-org/sase/.venv/bin/python', '/home/bryan/projects/github/sase-org/sase/tools/run_pytest', 'fast', '/var/...
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_family_bead_and_plan_context_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/projects/github/sase-org/sase/tests/ace/tui/visual/snapshots/png/agents_phase_bead_and_plan_context_120x40.png
======================================================= 2 failed, 25389 passed, 7 skipped, 64 warnings in 255.16s (0:04:15) ========================================================
error: recipe `test` failed on line 327 with exit code 1
```