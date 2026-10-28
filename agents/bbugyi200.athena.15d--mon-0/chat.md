# Chat History - ace-run (15d--mon-0)

- **TIMESTAMP:** 2026-10-28 17:26:01 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 15d--mon-0

## Prompt

sase monitor start --command 'just check' --reason 'Verify before host completion'

## Response

sase tool run 2e31706de10c162e38d73dcd1905c3eb
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
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
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (docs contract)
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.42.7 is missing 34 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] agent_publication_protection_wire_schema_version: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] agent_stats_query_macro_usage: first appears in sase-core 31deb0d (feat(stats): add query_macro_usage and accept config via); no release tag contains it yet.
[core-floor-probe] artifact_link_collision_partition: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_collision_wire_schema_version: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_quarantine_record_canonical_json: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_quarantine_record_path: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_quarantine_record_validate: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_quarantine_wire_schema_version: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] assess_repository_landing_proof: first appears in sase-core 800caef (fix(beads): recover every eligible failed-run close in one mutation); release v0.43.0 contains it.
[core-floor-probe] bead_recover_failed_closes: first appears in sase-core 4f17b72 (feat(beads): recover failed-run closes atomically); release v0.43.0 contains it.
[core-floor-probe] classify_sidecar_publication_push_result: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] footprint_card: first appears in sase-core 83b010d (feat(footprint): add lens engine, evidence states, and review decisions); no release tag contains it yet.
[core-floor-probe] footprint_catalog_status: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_clear: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_decide: first appears in sase-core 83b010d (feat(footprint): add lens engine, evidence states, and review decisions); no release tag contains it yet.
[core-floor-probe] footprint_export: first appears in sase-core 65546fd (feat(footprint): add identity-free weekly export and replace-all import); no release tag contains it yet.
[core-floor-probe] footprint_fold: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_import: first appears in sase-core 65546fd (feat(footprint): add identity-free weekly export and replace-all import); no release tag contains it yet.
[core-floor-probe] footprint_ingest_catalog: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_prune: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_report: first appears in sase-core 83b010d (feat(footprint): add lens engine, evidence states, and review decisions); no release tag contains it yet.
[core-floor-probe] footprint_status: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_upsert_derived: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_validate_overlay: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_wire_schema_version: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] publication_protection_ledger_empty: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_ledger_validate: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_lookup: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_rejection: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_scan: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_resolve_verified_clean: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_retry_allowed: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_upsert: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_scan_disposition: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
{"cache_hit": true, "capabilities": [{"commit": "416db28", "name": "agent_publication_protection_wire_schema_version", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "31deb0d", "name": "agent_stats_query_macro_usage", "release": null, "subject": "feat(stats): add query_macro_usage and accept config via"}, {"commit": "6613c9b", "name": "artifact_link_collision_partition", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_collision_wire_schema_version", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_canonical_json", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_path", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_validate", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_wire_schema_version", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "800caef", "name": "assess_repository_landing_proof", "release": "v0.43.0", "subject": "fix(beads): recover every eligible failed-run close in one mutation"}, {"commit": "4f17b72", "name": "bead_recover_failed_closes", "release": "v0.43.0", "subject": "feat(beads): recover failed-run closes atomically"}, {"commit": "416db28", "name": "classify_sidecar_publication_push_result", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "83b010d", "name": "footprint_card", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_catalog_status", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_clear", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_decide", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "65546fd", "name": "footprint_export", "release": null, "subject": "feat(footprint): add identity-free weekly export and replace-all import"}, {"commit": "2d0b62e", "name": "footprint_fold", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "65546fd", "name": "footprint_import", "release": null, "subject": "feat(footprint): add identity-free weekly export and replace-all import"}, {"commit": "2d0b62e", "name": "footprint_ingest_catalog", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_prune", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_report", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_status", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_upsert_derived", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_validate_overlay", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_wire_schema_version", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "416db28", "name": "publication_protection_ledger_empty", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_ledger_validate", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_lookup", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_rejection", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_scan", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_resolve_verified_clean", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_retry_allowed", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_upsert", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_scan_disposition", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}], "declared_floor": "0.42.7", "exit_code": 4, "message": "sase-core-rs==0.42.7 is missing 34 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✓ docs (build + links)
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
selected 864 of 5453 test files (rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost)
coverage contexts: baseline 96183d71b3ef (stale, 4784 commits behind HEAD) matched 2 changed file(s) and contributed 8 test file(s)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.13.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 9148 items

tests/ace/test_scope_token.py .............................              [  0%]
tests/ace/tui/actions/test_agent_archive_shelf.py .............          [  0%]
tests/ace/tui/actions/test_axe_stop_quit.py ......................       [  0%]
tests/ace/tui/actions/test_live_watch_coverage.py .....                  [  0%]
tests/ace/tui/actions/test_pr_unmirrored_counts_cache.py ...             [  0%]
tests/ace/tui/actions/test_prompt_save_mini_macro_pane.py ........       [  0%]
tests/ace/tui/actions/test_prompt_snippet_location_flow.py ...........   [  0%]
tests/ace/tui/actions/test_service_host_keys.py ......                   [  1%]
tests/ace/tui/actions/test_view_agent_metadata.py .........              [  1%]
tests/ace/tui/artifacts_contract/test_contract_compiler.py ............. [  1%]
..........                                                               [  1%]
tests/ace/tui/artifacts_contract/test_pane_declarations.py ......        [  1%]
tests/ace/tui/artifacts_contract/test_provider_contract_validation.py .. [  1%]
..............                                                           [  1%]
tests/ace/tui/artifacts_contract/test_query_conformance.py ............. [  1%]
.................                                                        [  1%]
tests/ace/tui/artifacts_contract/test_relation_goldens.py ..             [  2%]
tests/ace/tui/artifacts_contract/test_synthetic_provider.py ....         [  2%]
tests/ace/tui/command_line/test_chrome_layout.py ....................... [  2%]
.                                                                        [  2%]
tests/ace/tui/modals/test_agent_run_log_contracts.py ..                  [  2%]
tests/ace/tui/modals/test_artifact_links_panel_modal.py .......          [  2%]
tests/ace/tui/modals/test_init_plan_modal.py .........                   [  2%]
tests/ace/tui/modals/test_new_project_apply_pane_integration.py ....     [  2%]
tests/ace/tui/modals/test_notification_hint_footer.py .........          [  2%]
tests/ace/tui/modals/test_notification_image_files.py ........           [  2%]
tests/ace/tui/models/test_artifact_groups.py .........                   [  2%]
tests/ace/tui/test_admin_center_selection_resume.py ........             [  2%]
tests/ace/tui/test_agent_archive_actions_guards.py ...........           [  3%]
tests/ace/tui/test_agent_archive_actions_marks.py ...........            [  3%]
tests/ace/tui/test_agent_archive_actions_readers.py .........            [  3%]
tests/ace/tui/test_agent_archive_column_actions_interaction.py ........  [  3%]
tests/ace/tui/test_agent_archive_column_actions_lifecycle.py .........   [  3%]
tests/ace/tui/test_agent_archive_column_app.py ......                    [  3%]
tests/ace/tui/test_agent_archive_column_real_corpus.py ......            [  3%]
tests/ace/tui/test_agent_archive_controller_generations.py ...........   [  3%]
tests/ace/tui/test_agent_archive_controller_lookup.py .........          [  3%]
tests/ace/tui/test_agent_archive_controller_prewarm.py .......           [  3%]
tests/ace/tui/test_agent_archive_proof.py ..................             [  4%]
tests/ace/tui/test_agent_archive_remaining_proof.py ...........          [  4%]
tests/ace/tui/test_agent_archive_restore_copy.py .............           [  4%]
tests/ace/tui/test_agent_archive_restore_proof.py ..........             [  4%]
tests/ace/tui/test_agent_archive_shelf_panel_cycle.py .                  [  4%]
tests/ace/tui/test_agent_bulk_ack_scope_undo.py ......                   [  4%]
tests/ace/tui/test_agent_bulk_chat_edit.py .........                     [  4%]
tests/ace/tui/test_agent_bulk_kill_edit.py ............                  [  4%]
tests/ace/tui/test_agent_clan_dismiss_cascade.py .                       [  4%]
tests/ace/tui/test_agent_cleanup_live_monitor_kill.py ...                [  4%]
tests/ace/tui/test_agent_cleanup_procs.py .......                        [  4%]
tests/ace/tui/test_agent_enter_targets_agent_session.py .............    [  5%]
tests/ace/tui/test_agent_enter_targets_clan.py ..........                [  5%]
tests/ace/tui/test_agent_enter_targets_executor.py ...........           [  5%]
tests/ace/tui/test_agent_enter_targets_legacy.py ....................... [  5%]
.                                                                        [  5%]
tests/ace/tui/test_agent_enter_targets_scope.py ...................      [  5%]
tests/ace/tui/test_agent_enter_targets_stranded.py .......               [  5%]
tests/ace/tui/test_agent_enter_wire.py ....................              [  6%]
tests/ace/tui/test_agent_fold_persistence.py ...........                 [  6%]
tests/ace/tui/test_agent_fold_transitions_llm_calls.py ....              [  6%]
tests/ace/tui/test_agent_jump_clan_members.py .............              [  6%]
tests/ace/tui/test_agent_kill_focus_visible_order.py .........           [  6%]
tests/ace/tui/test_agent_member_scope_kill.py ..........                 [  6%]
tests/ace/tui/test_agent_metadata_search.py ...........                  [  6%]
tests/ace/tui/test_agent_notification_status_overrides.py .........      [  6%]
tests/ace/tui/test_agent_panel_first_selection.py ...................... [  6%]
                                                                         [  6%]
tests/ace/tui/test_agent_panel_hint_folding.py ..............            [  7%]
tests/ace/tui/test_agent_session_member_relaunch.py ........             [  7%]
tests/ace/tui/test_agent_session_status_convergence_repro.py ...         [  7%]
tests/ace/tui/test_agent_settlement_notification_match.py .........      [  7%]
tests/ace/tui/test_agent_stopped_navigation.py ...........               [  7%]
tests/ace/tui/test_agent_stopped_navigation_clans.py ......              [  7%]
tests/ace/tui/test_agent_stranded_detail.py ....                         [  7%]
tests/ace/tui/test_agent_tab_cross_nav.py ..................             [  7%]
tests/ace/tui/test_agent_tab_cross_nav_entry_points.py ..............    [  7%]
tests/ace/tui/test_agent_tab_cross_nav_modals.py ....                    [  7%]
tests/ace/tui/test_agent_tab_scope.py ..................                 [  8%]
tests/ace/tui/test_agent_tab_scope_honesty.py ..............             [  8%]
tests/ace/tui/test_agent_tab_strip_machine.py .................          [  8%]
tests/ace/tui/test_agent_unread_chrome.py ......                         [  8%]
tests/ace/tui/test_agent_unread_done_navigation.py ..........            [  8%]
tests/ace/tui/test_agent_unread_done_navigation_folds.py ............    [  8%]
tests/ace/tui/test_agent_unread_done_navigation_panels.py ......         [  8%]
tests/ace/tui/test_agent_unread_finalizer.py ..............              [  9%]
tests/ace/tui/test_agent_unread_jump_fast_path.py .....                  [  9%]
tests/ace/tui/test_agent_unread_projection.py .......................... [  9%]
..                                                                       [  9%]
tests/ace/tui/test_agent_unread_selection.py ................            [  9%]
tests/ace/tui/test_agent_unread_toggle.py ......................         [  9%]
tests/ace/tui/test_agent_wait_resume_targets.py ........................ [ 10%]
.............                                                            [ 10%]
tests/ace/tui/test_agents_diff_badge_deferred.py ....................... [ 10%]
..                                                                       [ 10%]
tests/ace/tui/test_agents_filter_bar_session.py ...............          [ 10%]
tests/ace/tui/test_agents_fleet_refresh_coalescing.py .....              [ 10%]
tests/ace/tui/test_agents_fleet_refresh_laziness_projection.py ......... [ 10%]
                                                                         [ 10%]
tests/ace/tui/test_agents_fleet_refresh_laziness_refresh.py .....        [ 10%]
tests/ace/tui/test_agents_fleet_refresh_off_loop.py .....                [ 10%]
tests/ace/tui/test_agents_info_metrics_generations.py ....               [ 10%]
tests/ace/tui/test_agents_live_hint_refresh.py ........................  [ 11%]
tests/ace/tui/test_agents_navigation_hydration.py .....                  [ 11%]
tests/ace/tui/test_agents_non_run_toggle_keys.py ....                    [ 11%]
tests/ace/tui/test_agents_onboarding.py ................                 [ 11%]
tests/ace/tui/test_agents_pane_detail_relations.py .........             [ 11%]
tests/ace/tui/test_agents_panel_focus_follows_selection.py ............. [ 11%]
                                                                         [ 11%]
tests/ace/tui/test_agents_panel_fold_mounted.py .                        [ 11%]
tests/ace/tui/test_agents_roster_generation.py .......                   [ 11%]
tests/ace/tui/test_agents_tab_completion_dismiss_e2e.py ...............  [ 11%]
tests/ace/tui/test_agents_view_hint_survives_refresh.py ..........       [ 12%]
tests/ace/tui/test_apply_path_index_maintenance_offthread.py .....       [ 12%]
tests/ace/tui/test_archive_arrivals.py .....                             [ 12%]
tests/ace/tui/test_artifact_entry_target.py .........................    [ 12%]
tests/ace/tui/test_artifact_index_maintenance_scheduler.py ......        [ 12%]
tests/ace/tui/test_artifact_links_ref_kind.py .........                  [ 12%]
tests/ace/tui/test_artifacts_agents_loading.py .                         [ 12%]
tests/ace/tui/test_artifacts_agents_revival.py .....                     [ 12%]
tests/ace/tui/test_artifacts_beads_filtering.py ........................ [ 12%]
                                                                         [ 12%]
tests/ace/tui/test_artifacts_beads_loading.py ...........                [ 13%]
tests/ace/tui/test_artifacts_beads_mutations.py ..........               [ 13%]
tests/ace/tui/test_artifacts_beads_navigation.py ....                    [ 13%]
tests/ace/tui/test_artifacts_copy_mode.py ...........................    [ 13%]
tests/ace/tui/test_artifacts_copy_references.py ......                   [ 13%]
tests/ace/tui/test_artifacts_current_project_scope.py .................. [ 13%]
......                                                                   [ 13%]
tests/ace/tui/test_artifacts_files_filtering.py ..............           [ 14%]
tests/ace/tui/test_artifacts_files_grouping.py ...                       [ 14%]
tests/ace/tui/test_artifacts_files_loading.py ........                   [ 14%]
tests/ace/tui/test_artifacts_files_open.py ....................          [ 14%]
tests/ace/tui/test_artifacts_files_pane_flag.py .....                    [ 14%]
tests/ace/tui/test_artifacts_list_navigation.py .....                    [ 14%]
tests/ace/tui/test_artifacts_marking.py .........                        [ 14%]
tests/ace/tui/test_artifacts_pane_descriptions.py .......                [ 14%]
tests/ace/tui/test_artifacts_pane_state.py ....                          [ 14%]
tests/ace/tui/test_artifacts_patches_navigator.py .............          [ 14%]
tests/ace/tui/test_artifacts_plans_data.py ....                          [ 14%]
tests/ace/tui/test_artifacts_plans_filtering.py ........                 [ 14%]
tests/ace/tui/test_artifacts_plans_interactions.py ....                  [ 14%]
tests/ace/tui/test_artifacts_plans_loading.py ..                         [ 15%]
tests/ace/tui/test_artifacts_provider_pane.py ....                       [ 15%]
tests/ace/tui/test_artifacts_query_history.py ...                        [ 15%]
tests/ace/tui/test_artifacts_relation_collapse.py ........               [ 15%]
tests/ace/tui/test_artifacts_relation_collapse_interactions.py .......   [ 15%]
tests/ace/tui/test_artifacts_relation_key_resolution.py ...........      [ 15%]
tests/ace/tui/test_artifacts_relation_navigation.py ....                 [ 15%]
tests/ace/tui/test_artifacts_relation_sources_artifact_links.py ........ [ 15%]
..                                                                       [ 15%]
tests/ace/tui/test_artifacts_relation_sources_beads.py .                 [ 15%]
tests/ace/tui/test_artifacts_relation_sources_documents.py .             [ 15%]
tests/ace/tui/test_artifacts_relation_sources_files.py .                 [ 15%]
tests/ace/tui/test_artifacts_relation_sources_patches.py .               [ 15%]
tests/ace/tui/test_artifacts_relation_sources_provider.py .              [ 15%]
tests/ace/tui/test_artifacts_relation_sources_stitches.py .              [ 15%]
tests/ace/tui/test_artifacts_relation_wiring.py .....                    [ 15%]
tests/ace/tui/test_artifacts_scaffold.py .............                   [ 15%]
tests/ace/tui/test_artifacts_shell.py .....................              [ 16%]
tests/ace/tui/test_axe_chop_output_edit.py .......                       [ 16%]
tests/ace/tui/test_axe_chop_run_nav.py ................                  [ 16%]
tests/ace/tui/test_axe_chop_selection.py ....                            [ 16%]
tests/ace/tui/test_axe_navigation.py ........                            [ 16%]
tests/ace/tui/test_axe_panels.py ...............                         [ 16%]
tests/ace/tui/test_axe_selection_identity.py ..........                  [ 16%]
tests/ace/tui/test_axe_startup_host_lifecycle.py ..........              [ 16%]
tests/ace/tui/test_axe_worker_status_completion.py .....                 [ 16%]
tests/ace/tui/test_capacity_inspector_openers.py ....                    [ 16%]
tests/ace/tui/test_changespec_detail_only_refresh.py ..........          [ 16%]
tests/ace/tui/test_changespec_graph_index.py ...                         [ 17%]
tests/ace/tui/test_changespec_grouped_navigation.py .................    [ 17%]
tests/ace/tui/test_changespec_jk_navigation.py ...                       [ 17%]
tests/ace/tui/test_changespec_query_corpus_routing.py ......             [ 17%]
tests/ace/tui/test_commits_config.py .........................           [ 17%]
tests/ace/tui/test_commits_pane_filters.py ........                      [ 17%]
tests/ace/tui/test_commits_pane_grouping.py ....                         [ 17%]
tests/ace/tui/test_comprehensive_update_preview.py ...................   [ 17%]
tests/ace/tui/test_config_center_tabs.py ................                [ 18%]
tests/ace/tui/test_config_hub_catalog.py .......                         [ 18%]
tests/ace/tui/test_copy_as_palette_contexts.py ......................... [ 18%]
                                                                         [ 18%]
tests/ace/tui/test_copy_targets.py ................                      [ 18%]
tests/ace/tui/test_disabled_provider_launch_panel.py ................    [ 18%]
tests/ace/tui/test_entry_points_vcs_prefix_persistence.py .....          [ 18%]
tests/ace/tui/test_entry_points_vcs_prefix_selection.py ............     [ 18%]
tests/ace/tui/test_gate_debug_modal.py ...........                       [ 19%]
tests/ace/tui/test_gate_failure_recovery.py ........                     [ 19%]
tests/ace/tui/test_gate_retry_choice.py .....                            [ 19%]
tests/ace/tui/test_jk_reliability.py ........                            [ 19%]
tests/ace/tui/test_jump_to_changespec.py .....................           [ 19%]
tests/ace/tui/test_jump_to_entry_history.py .............                [ 19%]
tests/ace/tui/test_jump_to_mentor_review.py ......                       [ 19%]
tests/ace/tui/test_kill_and_edit_inflight.py ...........                 [ 19%]
tests/ace/tui/test_kill_and_edit_last_launch_bulk.py ....                [ 19%]
tests/ace/tui/test_kill_and_edit_last_launch_dispatch.py ...........     [ 20%]
tests/ace/tui/test_kill_and_edit_last_launch_join.py ....                [ 20%]
tests/ace/tui/test_kill_and_edit_last_launch_single.py ......            [ 20%]
tests/ace/tui/test_kill_and_edit_launch_barrier_hold.py .......          [ 20%]
tests/ace/tui/test_kill_and_edit_launch_barrier_mount.py ......          [ 20%]
tests/ace/tui/test_launch_failure_logging.py ......                      [ 20%]
tests/ace/tui/test_launch_proc_handle_rekey.py ..                        [ 20%]
tests/ace/tui/test_launchable_mru.py ..................                  [ 20%]
tests/ace/tui/test_leader_keybinding_footer.py ........................  [ 20%]
tests/ace/tui/test_leader_keymap_dispatch.py ........................... [ 21%]
....................                                                     [ 21%]
tests/ace/tui/test_link_follow.py ......................                 [ 21%]
tests/ace/tui/test_link_follow_bounded_panes.py .........                [ 21%]
tests/ace/tui/test_link_follow_entry_points.py .................         [ 21%]
tests/ace/tui/test_link_follow_flat_panes.py ...............             [ 22%]
tests/ace/tui/test_link_follow_hydration.py .........                    [ 22%]
tests/ace/tui/test_link_follow_ladder.py .........                       [ 22%]
tests/ace/tui/test_link_follow_planner.py ......                         [ 22%]
tests/ace/tui/test_link_follow_seam.py .................                 [ 22%]
tests/ace/tui/test_link_follow_toast.py .............                    [ 22%]
tests/ace/tui/test_link_index_cache.py ......                            [ 22%]
tests/ace/tui/test_link_index_chips.py ......................            [ 22%]
tests/ace/tui/test_link_index_parity.py .......                          [ 23%]
tests/ace/tui/test_link_index_targets.py ................                [ 23%]
tests/ace/tui/test_link_rail.py ..............                           [ 23%]
tests/ace/tui/test_link_rail_mount.py ..                                 [ 23%]
tests/ace/tui/test_link_subject.py .............                         [ 23%]
tests/ace/tui/test_link_subject_mixin.py ......                          [ 23%]
tests/ace/tui/test_link_trail.py .................                       [ 23%]
tests/ace/tui/test_live_reply_follow_mounted_reply.py .                  [ 23%]
tests/ace/tui/test_live_reply_follow_mounted_session.py .                [ 23%]
tests/ace/tui/test_live_reply_follow_mounted_workflow.py ..              [ 23%]
tests/ace/tui/test_loader_cleanup_decoupling.py ......                   [ 23%]
tests/ace/tui/test_log_panel_keymap.py .......................           [ 24%]
tests/ace/tui/test_macro_browser_load_keymap.py ..............           [ 24%]
tests/ace/tui/test_main_deck_reply_steal_recovery.py .                   [ 24%]
tests/ace/tui/test_member_jump_lane_targets.py .....                     [ 24%]
tests/ace/tui/test_named_proc_dismissal.py ..........                    [ 24%]
tests/ace/tui/test_node_finder_e2e.py .....                              [ 24%]
tests/ace/tui/test_notification_backlog_access.py ...................... [ 24%]
.                                                                        [ 24%]
tests/ace/tui/test_notification_completion_arrival_overlay.py .....      [ 24%]
tests/ace/tui/test_notification_custom_gate.py ..............            [ 24%]
tests/ace/tui/test_notification_custom_gate_execution.py ....            [ 25%]
tests/ace/tui/test_notification_custom_gate_loader.py .......            [ 25%]
tests/ace/tui/test_notification_deadline_coordinator.py .......          [ 25%]
tests/ace/tui/test_notification_dispatch.py ...........................  [ 25%]
tests/ace/tui/test_notification_gate_pane.py ................            [ 25%]
tests/ace/tui/test_notification_jump_to_agent_reveal.py .........        [ 25%]
tests/ace/tui/test_notification_plan_gate.py .................           [ 25%]
tests/ace/tui/test_notification_report_pane.py ...........               [ 26%]
tests/ace/tui/test_notification_sudo.py ...........                      [ 26%]
tests/ace/tui/test_open_launch_control_notification.py ..                [ 26%]
tests/ace/tui/test_panel_scoped_bulk.py ................                 [ 26%]
tests/ace/tui/test_panel_tab_strip_compact.py ..........                 [ 26%]
tests/ace/tui/test_patch_relation_index.py ....................          [ 26%]
tests/ace/tui/test_pending_ack_fence.py ........                         [ 26%]
tests/ace/tui/test_pending_launch.py ...................                 [ 26%]
tests/ace/tui/test_plan_decision_ace_render_state.py .....               [ 27%]
tests/ace/tui/test_plan_decision_ace_stale.py ...                        [ 27%]
tests/ace/tui/test_plans_navigation_hydration.py ....                    [ 27%]
tests/ace/tui/test_plugin_action_confirm_modal.py ................       [ 27%]
tests/ace/tui/test_plugins_browser_loading_cache_only.py .....           [ 27%]
tests/ace/tui/test_plugins_browser_loading_freshness.py .....            [ 27%]
tests/ace/tui/test_plugins_browser_pane_agent_clis.py ............       [ 27%]
tests/ace/tui/test_plugins_browser_pane_agent_clis_history.py .......... [ 27%]
...                                                                      [ 27%]
tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py .......... [ 27%]
.....                                                                    [ 27%]
tests/ace/tui/test_plugins_browser_pane_agent_clis_install_combined.py . [ 27%]
......                                                                   [ 27%]
tests/ace/tui/test_plugins_browser_pane_all_current.py ............      [ 28%]
tests/ace/tui/test_plugins_browser_pane_cached_open.py ...........       [ 28%]
tests/ace/tui/test_plugins_browser_pane_comprehensive_update.py ........ [ 28%]
....                                                                     [ 28%]
tests/ace/tui/test_plugins_browser_pane_detail.py .............          [ 28%]
tests/ace/tui/test_plugins_browser_pane_install.py .............         [ 28%]
tests/ace/tui/test_plugins_browser_pane_inventory.py ..........          [ 28%]
tests/ace/tui/test_plugins_browser_pane_jump.py .......                  [ 28%]
tests/ace/tui/test_plugins_browser_pane_loading.py ....................  [ 28%]
tests/ace/tui/test_plugins_browser_pane_marks.py .................       [ 29%]
tests/ace/tui/test_plugins_browser_pane_sase_update.py ............      [ 29%]
tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py ..........    [ 29%]
tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py .....       [ 29%]
tests/ace/tui/test_plugins_browser_pane_uninstall.py ........            [ 29%]
tests/ace/tui/test_plugins_browser_pane_update.py .........              [ 29%]
tests/ace/tui/test_plugins_catalog_scale_fixture.py .                    [ 29%]
tests/ace/tui/test_post_open_quiet.py ....                               [ 29%]
tests/ace/tui/test_prompt_active_explicit_state.py ........              [ 29%]
tests/ace/tui/test_prompt_bar_stack_submit_handlers.py .............     [ 29%]
tests/ace/tui/test_quit_prompt_stash.py .........                        [ 30%]
tests/ace/tui/test_refresh_panel_dispatch.py ...............             [ 30%]
tests/ace/tui/test_relation_cache_bounds.py .......                      [ 30%]
tests/ace/tui/test_relation_reveal_navigation.py ...                     [ 30%]
tests/ace/tui/test_reload_and_reposition.py .......                      [ 30%]
tests/ace/tui/test_remote_lifecycle_actions.py ......................    [ 30%]
tests/ace/tui/test_resolve_ref_from_prompt.py .                          [ 30%]
tests/ace/tui/test_resolve_vcs_tag.py .................                  [ 30%]
tests/ace/tui/test_show_agent_run_log_keymap.py .......                  [ 30%]
tests/ace/tui/test_starting_agent_poll.py ................               [ 31%]
tests/ace/tui/test_startup_stopwatch_live_update.py .................... [ 31%]
...........                                                              [ 31%]
tests/ace/tui/test_statistics_footprint.py ...............               [ 31%]
tests/ace/tui/test_statistics_help_modal.py ........                     [ 31%]
tests/ace/tui/test_statistics_legends_states.py ............             [ 31%]
tests/ace/tui/test_statistics_macro_picker_modal.py ...                  [ 31%]
tests/ace/tui/test_statistics_pane_bindings.py ....                      [ 31%]
tests/ace/tui/test_statistics_pane_current_project_seed.py ....          [ 31%]
tests/ace/tui/test_statistics_pane_filters.py .........                  [ 32%]
tests/ace/tui/test_statistics_pane_interactions.py .......               [ 32%]
tests/ace/tui/test_statistics_pane_loading.py .........                  [ 32%]
tests/ace/tui/test_statistics_pane_projects.py ..................        [ 32%]
tests/ace/tui/test_statistics_pane_rendering.py .................        [ 32%]
tests/ace/tui/test_statistics_pane_view_navigation.py ........           [ 32%]
tests/ace/tui/test_statistics_perf.py .............                      [ 32%]
tests/ace/tui/test_statistics_runners.py ........                        [ 32%]
tests/ace/tui/test_statistics_scope_header.py .........                  [ 32%]
tests/ace/tui/test_statistics_view_number_select.py .............        [ 33%]
tests/ace/tui/test_tool_run_actions.py .....................             [ 33%]
tests/ace/tui/test_tool_runs_deck_cards_availability.py .........        [ 33%]
tests/ace/tui/test_tool_runs_deck_cards_document.py ..........           [ 33%]
tests/ace/tui/test_tool_runs_glance.py .......................           [ 33%]
tests/ace/tui/test_tool_runs_pane.py ..............                      [ 33%]
tests/ace/tui/test_tool_runs_run_links.py ....................           [ 34%]
tests/ace/tui/test_tribe_panel_flicker_debounced.py .....                [ 34%]
tests/ace/tui/test_tribe_panel_flicker_display.py ...                    [ 34%]
tests/ace/tui/test_tui_provenance.py .........                           [ 34%]
tests/ace/tui/test_unread_ack_pipeline.py ....                           [ 34%]
tests/ace/tui/test_unread_trace_spans.py .....                           [ 34%]
tests/ace/tui/test_update_run_actions.py .....................           [ 34%]
tests/ace/tui/test_visual_fixture_host_paths.py .                        [ 34%]
tests/ace/tui/test_y_keymap_non_blocking.py ....                         [ 34%]
tests/ace/tui/widgets/artifacts/test_agents_query.py .........           [ 34%]
tests/ace/tui/widgets/artifacts/test_query_session.py .                  [ 34%]
tests/ace/tui/widgets/decks/final/test_final_run_blocks.py ............. [ 35%]
.                                                                        [ 35%]
tests/ace/tui/widgets/decks/test_deck_card_block_keys.py ............... [ 35%]
..                                                                       [ 35%]
tests/ace/tui/widgets/decks/test_deck_document_scroll_pilot.py ...       [ 35%]
tests/ace/tui/widgets/decks/test_deck_files_probe.py ..................  [ 35%]
tests/ace/tui/widgets/decks/test_deck_spec.py .......                    [ 35%]
tests/ace/tui/widgets/decks/test_deck_split_keys.py ......               [ 35%]
tests/ace/tui/widgets/decks/test_deck_three_panels.py .................. [ 35%]
.....                                                                    [ 35%]
tests/ace/tui/widgets/decks/test_deck_view_keys.py ...................   [ 36%]
tests/ace/tui/widgets/decks/test_deck_zoom_chrome.py ...                 [ 36%]
tests/ace/tui/widgets/decks/test_final_deck_shell.py ................... [ 36%]
......                                                                   [ 36%]
tests/ace/tui/widgets/decks/test_record_deck_archive_rows.py .......     [ 36%]
tests/ace/tui/widgets/decks/test_record_deck_shell.py .................. [ 36%]
...........                                                              [ 36%]
tests/ace/tui/widgets/decks/test_record_relations.py ......              [ 36%]
tests/ace/tui/widgets/decks/test_spread_scroll_landing.py ...........    [ 36%]
tests/ace/tui/widgets/test_agent_artifact_reads.py ..........            [ 37%]
tests/ace/tui/widgets/test_agent_bead_touch_rows_basic.py ..........     [ 37%]
tests/ace/tui/widgets/test_agent_bead_touch_rows_closed.py ...........   [ 37%]
tests/ace/tui/widgets/test_agent_bead_touch_rows_glyphs.py .....         [ 37%]
tests/ace/tui/widgets/test_agent_bead_touch_rows_lane.py ........        [ 37%]
tests/ace/tui/widgets/test_agent_bead_touch_rows_notes.py .........      [ 37%]
tests/ace/tui/widgets/test_agent_bead_touches_wiring.py ....             [ 37%]
tests/ace/tui/widgets/test_agent_context_lanes.py ..............         [ 37%]
tests/ace/tui/widgets/test_agent_context_ordering.py .......             [ 37%]
tests/ace/tui/widgets/test_agent_context_presentation.py ....            [ 37%]
tests/ace/tui/widgets/test_agent_display_header_enrichment_async.py .... [ 37%]
...                                                                      [ 37%]
tests/ace/tui/widgets/test_agent_display_header_summary_lanes.py ....... [ 37%]
...                                                                      [ 38%]
tests/ace/tui/widgets/test_agent_display_header_summary_trace.py ...     [ 38%]
tests/ace/tui/widgets/test_agent_display_plan_section.py ............... [ 38%]
......                                                                   [ 38%]
tests/ace/tui/widgets/test_agent_display_plan_summary.py ........        [ 38%]
tests/ace/tui/widgets/test_agent_display_raw_prompt_highlight.py ....... [ 38%]
                                                                         [ 38%]
tests/ace/tui/widgets/test_agent_display_workflow_async.py ........      [ 38%]
tests/ace/tui/widgets/test_agent_glossary_reads.py ..............        [ 38%]
tests/ace/tui/widgets/test_agent_header_panel_basic.py ............      [ 38%]
tests/ace/tui/widgets/test_agent_header_panel_preview.py ............... [ 38%]
.                                                                        [ 38%]
tests/ace/tui/widgets/test_agent_jump_panel_expansion.py ......          [ 39%]
tests/ace/tui/widgets/test_agent_jump_panel_numbers.py ....              [ 39%]
tests/ace/tui/widgets/test_agent_jump_panel_scroll.py ..........         [ 39%]
tests/ace/tui/widgets/test_agent_memory_reads_basic.py ............      [ 39%]
tests/ace/tui/widgets/test_agent_memory_reads_summary.py ............... [ 39%]
.                                                                        [ 39%]
tests/ace/tui/widgets/test_agent_prompt_panel_gate.py ...............    [ 39%]
tests/ace/tui/widgets/test_agent_prompt_panel_macros.py .........        [ 39%]
tests/ace/tui/widgets/test_agent_prompt_panel_monitor.py ............... [ 39%]
.....                                                                    [ 39%]
tests/ace/tui/widgets/test_agent_prompt_panel_steps.py ........          [ 40%]
tests/ace/tui/widgets/test_agent_skill_uses.py .........                 [ 40%]
tests/ace/tui/widgets/test_agent_slow_tool_tick.py ....                  [ 40%]
tests/ace/tui/widgets/test_agent_slow_tools.py ..............            [ 40%]
tests/ace/tui/widgets/test_agent_slow_tools_detail.py .................. [ 40%]
.                                                                        [ 40%]
tests/ace/tui/widgets/test_agent_slow_tools_hints.py ...                 [ 40%]
tests/ace/tui/widgets/test_agent_tribe_clan_summaries.py ..............  [ 40%]
tests/ace/tui/widgets/test_agent_tribe_prompts.py ....................   [ 40%]
tests/ace/tui/widgets/test_agent_tribe_summary.py ..                     [ 41%]
tests/ace/tui/widgets/test_artifact_ref_completion_catalog.py .......    [ 41%]
tests/ace/tui/widgets/test_artifact_ref_completion_widget.py ........... [ 41%]
.............                                                            [ 41%]
tests/ace/tui/widgets/test_filter_bar_persistent.py .........            [ 41%]
tests/ace/tui/widgets/test_filter_bar_profile.py .....                   [ 41%]
tests/ace/tui/widgets/test_identity_header.py ........................   [ 41%]
tests/ace/tui/widgets/test_keybinding_footer_llm_calls_detail.py ....... [ 41%]
.............                                                            [ 41%]
tests/ace/tui/widgets/test_llm_calls_panel_cache.py .....                [ 42%]
tests/ace/tui/widgets/test_llm_calls_panel_event_loop.py ...             [ 42%]
tests/ace/tui/widgets/test_llm_calls_panel_subject_guard.py ...          [ 42%]
tests/ace/tui/widgets/test_llm_calls_panel_timeline.py ................. [ 42%]
.                                                                        [ 42%]
tests/ace/tui/widgets/test_member_jump_sections.py ..................... [ 42%]
                                                                         [ 42%]
tests/ace/tui/widgets/test_prompt_mount_dedup.py .........               [ 42%]
tests/ace/tui/widgets/test_prompt_panel_header.py .........              [ 42%]
tests/ace/tui/widgets/test_prompt_panel_section_navigation_cache.py .... [ 42%]
.....                                                                    [ 42%]
tests/ace/tui/widgets/test_prompt_panel_section_navigation_rendering.py . [ 42%]
.....                                                                    [ 42%]
tests/ace/tui/widgets/test_prompt_panel_section_navigation_state.py .... [ 42%]
.                                                                        [ 42%]
tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py .. [ 42%]
.......                                                                  [ 43%]
tests/agents_sync/test_commit_publication_bounded_drain.py ......        [ 43%]
tests/agents_sync/test_commit_publication_drain_accounting.py .......... [ 43%]
                                                                         [ 43%]
tests/agents_sync/test_commit_publication_queue.py ........              [ 43%]
tests/agents_sync/test_deferred_prompt_archive.py ....                   [ 43%]
tests/agents_sync/test_git_sync.py ........................              [ 43%]
tests/agents_sync/test_git_sync_outbox/test_bounded_retry.py ...         [ 43%]
tests/agents_sync/test_git_sync_outbox/test_retry_retired.py .......     [ 43%]
tests/agents_sync/test_git_sync_outbox/test_sync.py .....                [ 43%]
tests/agents_sync/test_prompt_archive.py ......                          [ 43%]
tests/agents_sync/test_prompt_archive_migration.py ....                  [ 43%]
tests/agents_sync/test_prompt_archive_objects.py ........                [ 43%]
tests/agents_sync/test_prompt_archive_protection.py ...........          [ 44%]
tests/agents_sync/test_prompt_archive_publish.py .....                   [ 44%]
tests/agents_sync/test_publication_drain_measure.py .................... [ 44%]
.........                                                                [ 44%]
tests/agents_sync/test_publication_recovery/test_push_paths.py ........  [ 44%]
tests/agents_sync/test_referenced_by_publication.py ..                   [ 44%]
tests/artifact_links/test_link_suggest.py ....                           [ 44%]
tests/artifact_refs/test_aliases.py ......                               [ 44%]
tests/artifact_refs/test_preprocessing_effects.py .................      [ 44%]
tests/artifact_refs/test_preprocessing_expansion.py ................     [ 45%]
tests/autonomy_contract/test_landing_gaps_gates.py .......               [ 45%]
tests/core/test_agent_archive_corpus_facade.py ...........               [ 45%]
tests/core/test_artifact_row_resolution_facade.py ..                     [ 45%]
tests/core/test_created_artifacts_variable.py .........                  [ 45%]
tests/doctor/test_checks_agent_holds.py .......                          [ 45%]
tests/doctor/test_checks_agent_index.py ..                               [ 45%]
tests/doctor/test_checks_agent_publication.py ......                     [ 45%]
tests/doctor/test_checks_agent_publication_digest.py ..                  [ 45%]
tests/doctor/test_checks_agent_publication_protection.py ..              [ 45%]
tests/doctor/test_checks_agents_sidecar.py ..                            [ 45%]
tests/doctor/test_checks_artifact_links.py ...............               [ 45%]
tests/doctor/test_checks_axe.py ....                                     [ 45%]
tests/doctor/test_checks_bead_pages.py ...                               [ 45%]
tests/doctor/test_checks_changespec_refs.py ...                          [ 45%]
tests/doctor/test_checks_completion.py .............                     [ 45%]
tests/doctor/test_checks_config_file_hooks.py ...                        [ 46%]
tests/doctor/test_checks_config_init.py ....                             [ 46%]
tests/doctor/test_checks_config_macro_definitions.py ..                  [ 46%]
tests/doctor/test_checks_config_macro_directives.py ...                  [ 46%]
tests/doctor/test_checks_config_macro_input_types.py .....               [ 46%]
tests/doctor/test_checks_config_model_macros.py ...........              [ 46%]
tests/doctor/test_checks_config_notification_rules.py .................. [ 46%]
................                                                         [ 46%]
tests/doctor/test_checks_config_notification_tabs.py .....               [ 46%]
tests/doctor/test_checks_config_retired.py ...                           [ 46%]
tests/doctor/test_checks_config_sdd.py .................                 [ 46%]
tests/doctor/test_checks_deep.py ....................                    [ 47%]
tests/doctor/test_checks_external_mirror.py .......                      [ 47%]
tests/doctor/test_checks_external_pr_mirror.py ...                       [ 47%]
tests/doctor/test_checks_flags.py ...............                        [ 47%]
tests/doctor/test_checks_integrations.py .................               [ 47%]
tests/doctor/test_checks_plugins.py ..........                           [ 47%]
tests/doctor/test_checks_project.py ............                         [ 47%]
tests/doctor/test_checks_project_spec_duplicates.py ....                 [ 47%]
tests/doctor/test_checks_providers.py .......                            [ 47%]
tests/doctor/test_checks_providers_auth.py .....                         [ 48%]
tests/doctor/test_checks_providers_default.py .....                      [ 48%]
tests/doctor/test_checks_providers_usage.py ......                       [ 48%]
tests/doctor/test_checks_referenced_by.py ....                           [ 48%]
tests/doctor/test_checks_resources.py ...................                [ 48%]
tests/doctor/test_checks_runtime.py ..............                       [ 48%]
tests/doctor/test_checks_sidecar_visibility.py ........                  [ 48%]
tests/doctor/test_checks_tools.py ...........                            [ 48%]
tests/doctor/test_checks_workspace.py ............                       [ 48%]
tests/doctor/test_config_memory_webs.py .....                            [ 48%]
tests/fakey/test_gate_capacity_plan_e2e.py ...                           [ 48%]
tests/feature_flags/test_cli_journeys.py .....                           [ 49%]
tests/file_hook_engine/test_artifact.py ....                             [ 49%]
tests/file_hook_engine/test_commit.py ........                           [ 49%]
tests/footprint/test_catalog.py ....................                     [ 49%]
tests/footprint/test_derived.py .......                                  [ 49%]
tests/footprint/test_export.py .....                                     [ 49%]
tests/footprint/test_fold.py ........                                    [ 49%]
tests/footprint/test_housekeeping.py ....                                [ 49%]
tests/footprint/test_report.py .....................                     [ 49%]
tests/footprint/test_status.py .....                                     [ 49%]
tests/goals/test_goal_artifact_kind.py ................                  [ 50%]
tests/goals/test_goal_ledger_root.py ....................                [ 50%]
tests/goals/test_goal_publish_sync.py .........................          [ 50%]
tests/instructions/test_render_parity.py ...........                     [ 50%]
tests/instructions/test_scoreboard_conformance.py ..........             [ 50%]
tests/instructions/test_scoreboard_doctor.py ....                        [ 50%]
tests/instructions/test_scoreboard_foreign.py .......                    [ 50%]
tests/instructions/test_verify_cli.py ..................                 [ 51%]
tests/llm_provider/test_claude_helper_channel.py .........s..            [ 51%]
tests/llm_provider/test_commit_finalizer_auto_artifact_links_executor.py . [ 51%]
..                                                                       [ 51%]
tests/llm_provider/test_commit_finalizer_auto_artifact_links_reconciliation.py . [ 51%]
.....                                                                    [ 51%]
tests/llm_provider/test_commit_finalizer_transient_beads_sidecar.py ...  [ 51%]
tests/macro/test_plugin_input_types.py .........                         [ 51%]
tests/main/test_amd_memory_units.py ............                         [ 51%]
tests/main/test_artifact_cli_link_add.py .......                         [ 51%]
tests/main/test_artifact_cli_link_commit.py .......                      [ 51%]
tests/main/test_artifact_cli_link_health_doctor.py ...                   [ 51%]
tests/main/test_artifact_cli_link_health_inspect.py .......              [ 51%]
tests/main/test_artifact_cli_link_health_refs.py ..                      [ 51%]
tests/main/test_artifact_cli_link_health_rename.py ..                    [ 51%]
tests/main/test_artifact_cli_link_health_stale_tables.py ....            [ 52%]
tests/main/test_artifact_cli_link_import.py ..                           [ 52%]
tests/main/test_artifact_cli_link_list.py ...                            [ 52%]
tests/main/test_artifact_cli_link_relation.py .........                  [ 52%]
tests/main/test_artifact_cli_list_doctor.py .......                      [ 52%]
tests/main/test_artifact_cli_open.py .........                           [ 52%]
tests/main/test_artifact_cli_read.py .............                       [ 52%]
tests/main/test_artifact_cli_show.py .....                               [ 52%]
tests/main/test_artifact_handler.py ................                     [ 52%]
tests/main/test_artifact_link_outbox_drain.py .......                    [ 52%]
tests/main/test_artifact_link_outbox_io.py ..........                    [ 52%]
tests/main/test_artifact_link_outbox_read.py ..                          [ 52%]
tests/main/test_artifact_pane.py ......                                  [ 52%]
tests/main/test_bead_entry_sdd_materialization_error.py .                [ 52%]
tests/main/test_bead_fast_path.py .................                      [ 53%]
tests/main/test_bead_fast_path_mutations.py ......                       [ 53%]
tests/main/test_completion_fast_path.py ................................ [ 53%]
.......                                                                  [ 53%]
tests/main/test_default_list_notice_entry.py ..                          [ 53%]
tests/main/test_doctor_command.py ..........                             [ 53%]
tests/main/test_doctor_tools.py .....                                    [ 53%]
tests/main/test_init_memory_bead_note.py ....                            [ 53%]
tests/main/test_init_memory_committed_drift.py ...                       [ 53%]
tests/main/test_init_memory_markdown_templates.py .....................  [ 54%]
tests/main/test_init_memory_task_types_snapshot.py .....                 [ 54%]
tests/main/test_init_onboarding_entry.py ........                        [ 54%]
tests/main/test_memory_parser_handler.py .........                       [ 54%]
tests/main/test_monitor_handler_start_validation.py ..............       [ 54%]
tests/main/test_parser_machine.py ..................                     [ 54%]
tests/main/test_parser_narrowing.py .................................... [ 55%]
..                                                                       [ 55%]
tests/main/test_plan_links_handler.py .......                            [ 55%]
tests/main/test_print_command.py ..............................          [ 55%]
tests/main/test_proc_handler_list.py ...............                     [ 55%]
tests/main/test_screenshot_command.py ..............                     [ 55%]
tests/main/test_skills_handler.py ...................                    [ 56%]
tests/main/test_stitch_create_cli.py ................................... [ 56%]
...................                                                      [ 56%]
tests/main/test_stitch_create_cli_resume_flag.py .....                   [ 56%]
tests/main/test_validate_handler.py .........                            [ 56%]
tests/main/test_workspace_handler_cleanup_repair.py .............        [ 56%]
tests/memory/test_mutation_generated.py .........                        [ 57%]
tests/monitor/test_no_new_receipt_host.py .......                        [ 57%]
tests/notification_store/test_snooze_e2e_matrix.py ..........            [ 57%]
tests/notification_store/test_unread_completion_index.py ..              [ 57%]
tests/pager/test_cold_path_import_cost.py ........                       [ 57%]
tests/pager/test_rail_parity.py .............                            [ 57%]
tests/perf/test_artifact_link_index_bench.py ......                      [ 57%]
tests/plan_chain_golden/test_plan_approval_response_golden.py .......... [ 57%]
.....                                                                    [ 57%]
tests/sdd/test_artifact_link_backfill.py .........                       [ 57%]
tests/sdd/test_artifact_link_beads.py ....                               [ 57%]
tests/sdd/test_artifact_link_conflict_resolver.py ...........            [ 58%]
tests/sdd/test_artifact_link_copy_skew_store.py .                        [ 58%]
tests/sdd/test_artifact_link_derivation.py ..........                    [ 58%]
tests/sdd/test_artifact_link_event_acceptance_convergence.py .           [ 58%]
tests/sdd/test_artifact_link_event_acceptance_mutation_paths.py ....     [ 58%]
tests/sdd/test_artifact_link_event_acceptance_outbox.py .                [ 58%]
tests/sdd/test_artifact_link_event_acceptance_process_death.py .         [ 58%]
tests/sdd/test_artifact_link_event_acceptance_projection.py ....         [ 58%]
tests/sdd/test_artifact_link_event_projection_batch.py ......            [ 58%]
tests/sdd/test_artifact_link_event_projection_endpoints.py .....         [ 58%]
tests/sdd/test_artifact_link_event_publisher.py .........                [ 58%]
tests/sdd/test_artifact_link_event_quarantine_io.py ..............       [ 58%]
tests/sdd/test_artifact_link_event_quarantine_paths.py ........          [ 58%]
tests/sdd/test_artifact_link_event_store_core.py ..........              [ 58%]
tests/sdd/test_artifact_link_event_store_health.py ......                [ 58%]
tests/sdd/test_artifact_link_event_store_quarantine.py ......            [ 58%]
tests/sdd/test_artifact_link_event_store_snapshot.py ...                 [ 58%]
tests/sdd/test_artifact_link_files.py ..............                     [ 59%]
tests/sdd/test_artifact_link_hidden_clone_e2e.py ..                      [ 59%]
tests/sdd/test_artifact_link_import_indexes.py ........                  [ 59%]
tests/sdd/test_artifact_link_machine_authorize.py .........              [ 59%]
tests/sdd/test_artifact_link_machine_store.py .................          [ 59%]
tests/sdd/test_artifact_link_migrate_notes.py ....                       [ 59%]
tests/sdd/test_artifact_link_neighborhood.py .......                     [ 59%]
tests/sdd/test_artifact_link_outbox_parked.py .....                      [ 59%]
tests/sdd/test_artifact_link_production_acceptance.py .                  [ 59%]
tests/sdd/test_artifact_link_projection.py .                             [ 59%]
tests/sdd/test_artifact_link_publication_retry.py ......                 [ 59%]
tests/sdd/test_artifact_link_quarantine_outbox_recovery.py .             [ 59%]
tests/sdd/test_artifact_link_quarantine_replay_history.py .....          [ 59%]
tests/sdd/test_artifact_link_quarantine_replay_outbox.py ...             [ 59%]
tests/sdd/test_artifact_link_quarantine_replay_records.py ....           [ 59%]
tests/sdd/test_artifact_link_reconcile.py .......                        [ 60%]
tests/sdd/test_artifact_link_rename_repair.py .......                    [ 60%]
tests/sdd/test_artifact_link_store_aggregate.py .........                [ 60%]
tests/sdd/test_artifact_link_store_bead_rows.py ........                 [ 60%]
tests/sdd/test_artifact_link_store_link_index.py ..                      [ 60%]
tests/sdd/test_artifact_link_store_project_key.py .....                  [ 60%]
tests/sdd/test_artifact_link_store_projected.py ...............          [ 60%]
tests/sdd/test_artifact_link_store_reconcile.py ...                      [ 60%]
tests/sdd/test_artifact_link_store_reconcile_durable.py .....            [ 60%]
tests/sdd/test_artifact_link_store_reconcile_preview.py ....             [ 60%]
tests/sdd/test_artifact_link_store_rows.py .........                     [ 60%]
tests/sdd/test_artifact_link_store_sidecar.py ...                        [ 60%]
tests/sdd/test_commit_store_artifact_link_derivation.py ...              [ 60%]
tests/sdd/test_plan_header_conflict_resolver.py ......                   [ 60%]
tests/sdd/test_referenced_by_refresh.py .....                            [ 60%]
tests/sdd_store/test_artifact_link_ignore.py ....                        [ 60%]
tests/sdd_store/test_sidecar_clone_remote_matching.py ......             [ 61%]
tests/sdd_store/test_sidecar_clone_retry_staging.py .........            [ 61%]
tests/sdd_store/test_sidecar_clone_retry_timeouts.py ........            [ 61%]
tests/sdd_store/test_store_maintenance.py ..............                 [ 61%]
tests/sdd_store/test_workspace_clone.py ..........                       [ 61%]
tests/stats/test_cli.py .............                                    [ 61%]
tests/stats/test_footprint_loader.py ..                                  [ 61%]
tests/stats/test_perf_query.py .........                                 [ 61%]
tests/stats/test_registry.py .......                                     [ 61%]
tests/test_ace_testing.py ........................................       [ 62%]
tests/test_agent_dismiss_in_memory.py ...............                    [ 62%]
tests/test_agent_kill.py ....                                            [ 62%]
tests/test_agent_kill_bulk.py .......                                    [ 62%]
tests/test_agent_kill_dismiss_fast_path.py ...............               [ 62%]
tests/test_agent_kill_phase1_async_io.py ......                          [ 62%]
tests/test_agent_kill_phase2_kill_all.py ....                            [ 62%]
tests/test_agent_kill_single_actions.py ......                           [ 62%]
tests/test_agent_kill_single_execution.py ....                           [ 62%]
tests/test_agent_kill_single_persistence.py ...                          [ 62%]
tests/test_agent_loader_self_heal_cleanup.py ........                    [ 63%]
tests/test_agent_monitor_stop_action.py ........                         [ 63%]
tests/test_agent_search_cli.py .................                         [ 63%]
tests/test_agent_session_terminology.py ..                               [ 63%]
tests/test_agent_stop_hook_config.py .                                   [ 63%]
tests/test_agent_tribe_terminology.py ..                                 [ 63%]
tests/test_ancestors_children_panel.py ..                                [ 63%]
tests/test_approval_projection.py .....................                  [ 63%]
tests/test_artifact_create_bead_attachment.py .....                      [ 63%]
tests/test_artifact_file_e2e.py ....                                     [ 63%]
tests/test_artifact_ref_uses.py .....                                    [ 63%]
tests/test_axe_chop_artifact_link_backfill_budgets.py ......             [ 63%]
tests/test_axe_chop_artifact_link_backfill_selection.py ......           [ 63%]
tests/test_axe_chop_artifact_link_backfill_sweep.py .....                [ 63%]
tests/test_axe_chop_doctor.py .....................                      [ 64%]
tests/test_axe_chop_external_issue_mirror.py ..........                  [ 64%]
tests/test_axe_chop_sidecar_auto_sync_backoff.py .......                 [ 64%]
tests/test_axe_chop_sidecar_auto_sync_maintenance.py ..........          [ 64%]
tests/test_axe_chop_sidecar_auto_sync_targets.py ........                [ 64%]
tests/test_axe_chop_wait_checks_beads.py ...........                     [ 64%]
tests/test_axe_default_chop_triggers.py ................................ [ 65%]
.....                                                                    [ 65%]
tests/test_axe_run_agent_exec_plan_followup_metadata.py ................ [ 65%]
                                                                         [ 65%]
tests/test_axe_runner_workspace_reclone.py ..............                [ 65%]
tests/test_axe_runner_workspace_repo_rescue.py .........                 [ 65%]
tests/test_axe_runner_workspace_self_heal.py ................            [ 65%]
tests/test_bare_git_init_e2e.py .............                            [ 65%]
tests/test_bare_git_ref.py ...............                               [ 66%]
tests/test_bead/test_attachment_fetch_doctor.py .....                    [ 66%]
tests/test_bead/test_background_store.py ..........                      [ 66%]
tests/test_bead/test_bead_page_publication.py ........                   [ 66%]
tests/test_bead/test_bead_publication_verification.py ..............     [ 66%]
tests/test_bead/test_bead_read.py .............                          [ 66%]
tests/test_bead/test_bead_show_agent_guard.py .....                      [ 66%]
tests/test_bead/test_bead_show_links.py .......                          [ 66%]
tests/test_bead/test_claimed_status.py .........                         [ 66%]
tests/test_bead/test_cli_at_path_values.py ....................          [ 66%]
tests/test_bead/test_cli_auto_commit.py ..................               [ 67%]
tests/test_bead/test_cli_close_history.py ......................         [ 67%]
tests/test_bead/test_cli_command_routing.py ........                     [ 67%]
tests/test_bead/test_cli_creation_reason_surface.py ......               [ 67%]
tests/test_bead/test_cli_golden.py ..................................... [ 67%]
....                                                                     [ 68%]
tests/test_bead/test_cli_mutation_push.py ..........                     [ 68%]
tests/test_bead/test_cli_plus_one.py ...............                     [ 68%]
tests/test_bead/test_cli_read_only_store.py ........                     [ 68%]
tests/test_bead/test_cli_read_single_store.py ...                        [ 68%]
tests/test_bead/test_cli_resolution.py .....................             [ 68%]
tests/test_bead/test_cli_search.py ..........................            [ 68%]
tests/test_bead/test_cli_show_artifact_links.py .....                    [ 68%]
tests/test_bead/test_cli_store_read_counts.py .............              [ 69%]
tests/test_bead/test_cli_work_from_plan_concurrency.py ..                [ 69%]
tests/test_bead/test_cli_work_from_plan_publication_flow.py ...          [ 69%]
tests/test_bead/test_cli_work_from_plan_publication_sidecars.py ..       [ 69%]
tests/test_bead/test_cli_work_from_plan_publication_store.py ......      [ 69%]
tests/test_bead/test_cli_work_from_plan_resume_rollback.py ....          [ 69%]
tests/test_bead/test_cli_work_from_plan_store.py .........               [ 69%]
tests/test_bead/test_operation_context.py ........                       [ 69%]
tests/test_bead/test_plan_archive_doctor.py ...                          [ 69%]
tests/test_bead/test_show_images.py ...........                          [ 69%]
tests/test_bead/test_snooze_surfaces.py ..........                       [ 69%]
tests/test_bead/test_stream_integrity.py ...................             [ 69%]
tests/test_bead/test_sync_conflict_replay.py ...                         [ 70%]
tests/test_bead/test_sync_workspace_prepare_regressions.py ....          [ 70%]
tests/test_bead/test_task_launch.py ............                         [ 70%]
tests/test_bead/test_task_type_end_to_end.py .....                       [ 70%]
tests/test_bead/test_workspace_sidecar_eviction_beads.py ........        [ 70%]
tests/test_bead_flag_presentation.py .........                           [ 70%]
tests/test_bead_time_surface_coverage.py ..................              [ 70%]
tests/test_check_sase_core_rs_bindings_tool.py ..........                [ 70%]
tests/test_ci_bootstrap_sidecars_tool.py ..................              [ 70%]
tests/test_commit_publication_inline.py .                                [ 70%]
tests/test_commit_runtime_tags_workflow.py ...                           [ 70%]
tests/test_commit_type_tag_contract.py ..                                [ 70%]
tests/test_commit_workflow_changespec.py .......................         [ 71%]
tests/test_commit_workflow_checkpointing.py ..................           [ 71%]
tests/test_commit_workflow_dispatch.py ......................            [ 71%]
tests/test_commit_workflow_hooks.py .....                                [ 71%]
tests/test_commit_workflow_publication_outcomes.py ..........            [ 71%]
tests/test_commit_workflow_publication_step.py .....                     [ 71%]
tests/test_commit_workflow_resume.py ...............                     [ 72%]
tests/test_commit_workflow_resume_recovery.py ...........                [ 72%]
tests/test_commit_workflow_resume_tracking.py ......                     [ 72%]
tests/test_config_schema.py ................                             [ 72%]
tests/test_config_schema_ace.py .......................                  [ 72%]
tests/test_config_schema_beads.py ...................                    [ 72%]
tests/test_config_schema_extensions.py ................................. [ 73%]
.............                                                            [ 73%]
tests/test_config_schema_gate_turn.py .....                              [ 73%]
tests/test_config_schema_keymaps.py .................                    [ 73%]
tests/test_config_schema_runtime_limits.py .........................     [ 73%]
tests/test_core_facade/test_bead_read.py ............                    [ 74%]
tests/test_core_finalizer_facade.py .........                            [ 74%]
tests/test_core_health.py .................                              [ 74%]
tests/test_demo_media_postprocessor.py ............                      [ 74%]
tests/test_dismissed_agent_lifecycle.py ...                              [ 74%]
tests/test_embedded_workflows_per_step.py .                              [ 74%]
tests/test_exercise_release.py .......................                   [ 74%]
tests/test_external_mirror_issues_lease.py .......                       [ 74%]
tests/test_file_hook_dispatch_regression.py ......s.                     [ 74%]
tests/test_finalizer_owned_turn_handoffs.py .............                [ 75%]
tests/test_finalizers_failed_close_recovery_close.py ...                 [ 75%]
tests/test_finalizers_failed_close_recovery_controls.py ....             [ 75%]
tests/test_finalizers_failed_close_recovery_handoff.py .....             [ 75%]
tests/test_finalizers_failed_close_recovery_landing.py ....              [ 75%]
tests/test_finalizers_failed_close_recovery_retry.py .....               [ 75%]
tests/test_finalizers_failed_close_recovery_snapshots.py ....            [ 75%]
tests/test_finalizers_step_channel_live_sink.py ........................ [ 75%]
                                                                         [ 75%]
tests/test_gate_finish_gaps_exec.py ..............                       [ 75%]
tests/test_gate_finish_gaps_routes.py ...............                    [ 75%]
tests/test_gemini_active_surface_guard.py ..                             [ 75%]
tests/test_github_actions_build_core.py .............                    [ 76%]
tests/test_github_actions_ci_master_gate.py ............................ [ 76%]
.......                                                                  [ 76%]
tests/test_github_actions_ci_workflow.py ............................... [ 76%]
                                                                         [ 76%]
tests/test_github_actions_install_smoke.py ...................           [ 77%]
tests/test_github_actions_publish.py ....                                [ 77%]
tests/test_github_actions_release.py .............................       [ 77%]
tests/test_github_actions_release_steward.py ..........                  [ 77%]
tests/test_github_actions_setup_sase.py ............                     [ 77%]
tests/test_github_actions_testpypi_drill.py .........                    [ 77%]
tests/test_justfile_lint_check.py ..........................             [ 77%]
tests/test_justfile_lint_lint.py ...............                         [ 78%]
tests/test_justfile_lint_setup.py ....................                   [ 78%]
tests/test_justfile_sase_core_dir.py ...............................     [ 78%]
tests/test_kill_durable_termination.py ....................              [ 78%]
tests/test_launch_approval_tui.py .......                                [ 79%]
tests/test_launch_condition_workspace.py ...                             [ 79%]
tests/test_launch_condition_workspace_admission_failures.py ......       [ 79%]
tests/test_linked_repo_workspaces.py ..............                      [ 79%]
tests/test_macro_terminology.py ..........                               [ 79%]
tests/test_notification_agent_targeting.py ............                  [ 79%]
tests/test_notification_completion_arrival.py ..............             [ 79%]
tests/test_notification_disappeared_review_refresh.py .....              [ 79%]
tests/test_notification_modal_action_bindings.py ....................    [ 79%]
tests/test_notification_modal_dismiss_actions.py .........               [ 80%]
tests/test_notification_modal_jump.py ..............                     [ 80%]
tests/test_notification_modal_mark_and_tabs.py ................          [ 80%]
tests/test_notification_modal_mute_snooze.py ........................... [ 80%]
                                                                         [ 80%]
tests/test_notification_modal_plus_ones.py .............                 [ 80%]
tests/test_notification_modal_question_pane.py ......                    [ 80%]
tests/test_notification_modal_read_tab.py ..................             [ 81%]
tests/test_notification_modal_scroll.py ..........                       [ 81%]
tests/test_notification_modal_section_toggle.py ......                   [ 81%]
tests/test_notification_modal_sections.py ...............                [ 81%]
tests/test_notification_modal_sent_at.py ..............                  [ 81%]
tests/test_notification_modal_snooze_status.py .....................     [ 81%]
tests/test_notification_modal_tab_order.py .........                     [ 81%]
tests/test_notification_modal_tab_routing.py ................            [ 82%]
tests/test_notification_modal_tag_strip.py ..................            [ 82%]
tests/test_notification_modal_undismiss_actions.py ........              [ 82%]
tests/test_notification_pending_gate_refresh.py .....                    [ 82%]
tests/test_notification_sections.py ......                               [ 82%]
tests/test_notification_toast_polling.py .................               [ 82%]
tests/test_notification_toast_polling_concurrency.py ...                 [ 82%]
tests/test_notification_toast_polling_delivery.py .....................  [ 82%]
tests/test_notification_toast_polling_snooze.py ......                   [ 82%]
tests/test_notification_toasts.py ...................................... [ 83%]
..............                                                           [ 83%]
tests/test_patch_stitch_terminology_audit.py ..................          [ 83%]
tests/test_plan_approval_actions_archive.py ...........                  [ 83%]
tests/test_plan_approval_actions_epic.py ..............                  [ 83%]
tests/test_plan_approval_archive_project_resolution.py .........         [ 84%]
tests/test_plan_approval_launch_reliability_epic_launch.py ..            [ 84%]
tests/test_plan_approval_launch_reliability_integration.py .........     [ 84%]
tests/test_plan_approval_responses.py .....................              [ 84%]
tests/test_plan_approve_cli.py ......................                    [ 84%]
tests/test_plan_archive_approval_recovery.py ....                        [ 84%]
tests/test_plan_command_handler.py .............                         [ 84%]
tests/test_plan_command_handler_formatting.py ........                   [ 84%]
tests/test_plan_command_handler_metadata.py ...........                  [ 85%]
tests/test_plan_decisions_handoff_bead.py ......                         [ 85%]
tests/test_plan_decisions_handoff_epic.py ....                           [ 85%]
tests/test_plan_direct_approval_run.py ..............                    [ 85%]
tests/test_plan_gates_execution.py ...............................       [ 85%]
tests/test_plan_propose_derivation.py .                                  [ 85%]
tests/test_plan_reject_cli.py ........                                   [ 85%]
tests/test_plan_rejection_response.py ........                           [ 85%]
tests/test_plan_search_cli.py ...........................                [ 86%]
tests/test_plan_validate.py ...................................          [ 86%]
tests/test_plugin_commands_help_doctor.py .................              [ 86%]
tests/test_plugin_commands_mount.py ...................................  [ 87%]
tests/test_pr_tags.py ....................................               [ 87%]
tests/test_probe_core_floor_tool.py ........                             [ 87%]
tests/test_profile_highlighting.py ..................................... [ 87%]
....                                                                     [ 88%]
tests/test_project_display_presentation_audit.py .........               [ 88%]
tests/test_project_pr_prefix.py .............                            [ 88%]
tests/test_project_tag_launch.py ................                        [ 88%]
tests/test_prompt_panel_meta.py ....                                     [ 88%]
tests/test_prompt_prediction_replay_sources.py ......                    [ 88%]
tests/test_query_profile_corpus_facade_index.py .....                    [ 88%]
tests/test_query_profile_corpus_facade_parity.py ...............         [ 88%]
tests/test_query_profile_corpus_facade_parse.py ........................ [ 89%]
...                                                                      [ 89%]
tests/test_query_profile_reference.py .................................. [ 89%]
.                                                                        [ 89%]
tests/test_queue_capacity_multiplier_edits.py .........                  [ 89%]
tests/test_ratchet_core_revision_tool.py ...........                     [ 89%]
tests/test_ratchet_core_window_source_normalization.py ..........        [ 89%]
tests/test_ratchet_core_window_tool_core.py .                            [ 89%]
tests/test_ratchet_core_window_tool_guardrails.py .......                [ 89%]
tests/test_ratchet_core_window_tool_modes.py ........                    [ 89%]
tests/test_ratchet_core_window_tool_reconciliation.py .......            [ 90%]
tests/test_release_candidate_inventory.py .............................. [ 90%]
.....                                                                    [ 90%]
tests/test_release_candidate_publish.py ........                         [ 90%]
tests/test_release_candidate_published_core.py ...................       [ 90%]
tests/test_release_candidate_qualify_red.py ...                          [ 90%]
tests/test_release_candidate_rerun.py ...........                        [ 90%]
tests/test_release_candidate_seal.py ...................                 [ 91%]
tests/test_release_core.py .......................                       [ 91%]
tests/test_require_tool_run.py .................                         [ 91%]
tests/test_ruff_config.py .                                              [ 91%]
tests/test_run_pytest_command.py ................................        [ 91%]
tests/test_run_pytest_contention.py ...................                  [ 92%]
tests/test_run_pytest_health.py .....                                    [ 92%]
tests/test_run_pytest_main.py .............                              [ 92%]
tests/test_run_pytest_scoped.py ..............                           [ 92%]
tests/test_run_pytest_tmpdir.py ...................                      [ 92%]
tests/test_run_pytest_workers.py ...................                     [ 92%]
tests/test_runtime_workspace_managed_roots.py .........                  [ 92%]
tests/test_rust_install_cleanup.py ..                                    [ 92%]
tests/test_sase_bead_tool.py ....                                        [ 93%]
tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py ..          [ 93%]
tests/test_sase_core_rs_bead_resolution_smoke_tool.py .                  [ 93%]
tests/test_sase_core_rs_feature_flag_state_smoke_tool.py ..              [ 93%]
tests/test_sase_core_rs_glossary_line_break_smoke_tool.py ..             [ 93%]
tests/test_sase_core_rs_plan_header_smoke_tool.py ..                     [ 93%]
tests/test_sase_core_rs_telemetry_smoke_tool.py .....                    [ 93%]
tests/test_sase_core_wheel_cache_tool.py ...........                     [ 93%]
tests/test_sase_migrate_statuses.py ...                                  [ 93%]
tests/test_sase_turn_terminology.py ...                                  [ 93%]
tests/test_sdd_beads.py ....                                             [ 93%]
tests/test_sdd_canonical_layout.py ..                                    [ 93%]
tests/test_sdd_commit_store.py .............                             [ 93%]
tests/test_sdd_git_contention.py ...................                     [ 93%]
tests/test_sdd_initialization.py ............                            [ 93%]
tests/test_setup_required_plugins_tool.py ...................            [ 94%]
tests/test_special_cases.py ...........                                  [ 94%]
tests/test_suite_gate.py .................                               [ 94%]
tests/test_suite_gate_budget.py ...............                          [ 94%]
tests/test_suite_gate_lease.py ...........                               [ 94%]
tests/test_suite_gate_reclaim.py ..............                          [ 94%]
tests/test_task_type_gate_surfaces.py ..                                 [ 94%]
tests/test_thinking_parser.py ...................                        [ 95%]
tests/test_timezone_display_guard.py .                                   [ 95%]
tests/test_timezone_display_tui.py .........                             [ 95%]
tests/test_tool_adoption_report_tool.py .........................        [ 95%]
tests/test_tui_plan_approval_archive.py ....                             [ 95%]
tests/test_tui_plan_epic_approval.py ....                                [ 95%]
tests/test_user_question_response.py .......                             [ 95%]
tests/test_validate_changelog_tool.py ......                             [ 95%]
tests/test_validate_dependency_group_tool.py ...                         [ 95%]
tests/test_validate_sase_core_rs_contracts_fleet_tool.py ....            [ 95%]
tests/test_validate_sase_core_rs_contracts_provider_tool.py ...          [ 95%]
tests/test_validate_sase_core_rs_contracts_tool.py ..........            [ 95%]
tests/test_validate_sase_core_rs_environment_tool.py ........            [ 95%]
tests/test_validate_sase_core_rs_prompt_tool.py .....                    [ 96%]
tests/test_validate_sase_core_rs_runtime_tool.py ..................      [ 96%]
tests/test_validate_sase_core_rs_tool.py .................               [ 96%]
tests/test_validate_sase_core_rs_version_tool.py ..............          [ 96%]
tests/test_validate_test_environment_tool.py ....................        [ 96%]
tests/test_vcs_log_resolve.py ...................                        [ 97%]
tests/test_wait_epic_follow_surfaces.py .........                        [ 97%]
tests/workflows/test_commit_add.py ................                      [ 97%]
tests/workflows/test_commit_duration.py .......                          [ 97%]
tests/workflows/test_commit_utils_modifiers.py .......                   [ 97%]
tests/workflows/test_commit_workflow.py ........ssss..................   [ 97%]
tests/workflows/test_commit_workflow_message_gate.py .........           [ 97%]
tests/workspace_provider/test_git_object_sharing.py ..............       [ 98%]
tests/workspace_provider/test_ownership_invariant_audit.py ............. [ 98%]
..                                                                       [ 98%]
tests/workspace_provider/test_rescue/test_bundles.py ...                 [ 98%]
tests/workspace_provider/test_rescue/test_nested_preservation.py ....... [ 98%]
.....                                                                    [ 98%]
tests/workspace_provider/test_rescue/test_snapshot.py F.F.F............. [ 98%]
...FF                                                                    [ 98%]
tests/workspace_provider/test_rescue/test_store.py ...                   [ 98%]
tests/workspace_provider/test_rescue/test_tags.py ......                 [ 98%]
tests/workspace_provider/test_rescue/test_worktree.py ....               [ 98%]
tests/workspace_provider/test_reset_replay.py .......................... [ 99%]
.........                                                                [ 99%]
tests/workspace_provider/test_utils.py ............                      [ 99%]
tests/workspace_provider/test_utils_git_clone.py .......                 [ 99%]
tests/workspace_provider/test_utils_git_clone_origin.py .........        [ 99%]
tests/workspace_provider/test_utils_workspace_checkout.py .........      [ 99%]
tests/workspace_provider/test_workspace_lease_acquire.py ...........     [ 99%]
tests/workspace_provider/test_workspace_lease_prepare.py ............... [ 99%]
..........                                                               [ 99%]
tests/workspace_provider/test_workspace_lease_submit.py .......          [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.



=================================== FAILURES ===================================
________ test_published_snapshot_carries_local_commits_and_dirty_edits _________

tmp_path = PosixPath('/var/tmp/sase-cf079551/pytest-of-bryan/pytest-28/test_published_snapshot_carrie0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8f1f2dac10>

    def test_published_snapshot_carries_local_commits_and_dirty_edits(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        redirect_state(tmp_path, monkeypatch)
        workspace, clone, remote = seed_remote_clone(tmp_path)
        pushed_tip = head(clone)
        commit_file(clone, "local-commit.txt", "local commit\n", "unpushed commit")
        (clone / "local-commit.txt").write_text("working edit\n", encoding="utf-8")
        (clone / "staged.txt").write_text("staged edit\n", encoding="utf-8")
        git(clone, "add", "--", "staged.txt")
>       before = source_probe(clone)
                 ^^^^^^^^^^^^
E       NameError: name 'source_probe' is not defined

tests/workspace_provider/test_rescue/_snapshot_capture_tests.py:156: NameError
___ test_published_snapshot_thins_a_large_checkout_and_restores_exact_state ____

tmp_path = PosixPath('/var/tmp/sase-cf079551/pytest-of-bryan/pytest-28/test_published_snapshot_thins_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8f1f1f0520>

    def test_published_snapshot_thins_a_large_checkout_and_restores_exact_state(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        redirect_state(tmp_path, monkeypatch)
        workspace, clone, remote = seed_remote_clone(tmp_path)
        commit_file(clone, "modified.txt", "before\n", "modified base")
        commit_file(clone, "staged.txt", "staged base\n", "staged base")
        (clone / "large.bin").write_bytes(b"large-published-content" * (256 * 1024 // 23))
        git(clone, "add", "--", "large.bin")
        git(clone, "commit", "-m", "large published file")
        git(clone, "push")
    
        (clone / "modified.txt").write_text("modified locally\n", encoding="utf-8")
        (clone / "staged.txt").write_text("staged locally\n", encoding="utf-8")
        git(clone, "add", "--", "staged.txt")
        (clone / "untracked.txt").write_bytes(b"new local bytes\x00\xff")
>       before = source_probe(clone)
                 ^^^^^^^^^^^^
E       NameError: name 'source_probe' is not defined

tests/workspace_provider/test_rescue/_snapshot_capture_tests.py:113: NameError
_________________ test_snapshot_restores_tracked_and_untracked _________________

tmp_path = PosixPath('/var/tmp/sase-cf079551/pytest-of-bryan/pytest-28/test_snapshot_restores_tracked0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8f1f2da580>

    def test_snapshot_restores_tracked_and_untracked(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        redirect_state(tmp_path, monkeypatch)
        workspace, clone, _remote = seed_remote_clone(tmp_path)
        make_dirty_wiring(clone)
        (clone / "docs" / "naïve file.txt").parent.mkdir(parents=True, exist_ok=True)
        (clone / "docs" / "naïve file.txt").write_text("unusual\n", encoding="utf-8")
>       before = source_probe(clone)
                 ^^^^^^^^^^^^
E       NameError: name 'source_probe' is not defined

tests/workspace_provider/test_rescue/_snapshot_capture_tests.py:70: NameError
__________ test_snapshot_restores_deletion_binary_and_tracked_ignored __________

tmp_path = PosixPath('/var/tmp/sase-cf079551/pytest-of-bryan/pytest-28/test_snapshot_restores_deletio0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8f1f2d9da0>

    def test_snapshot_restores_deletion_binary_and_tracked_ignored(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        redirect_state(tmp_path, monkeypatch)
        workspace, clone, _remote = seed_remote_clone(tmp_path)
        commit_file(clone, "keep.txt", "keep\n", "keep")
        commit_file(clone, "delete-me.txt", "gone-soon\n", "to delete")
        commit_file(clone, "build/out.bin", "tracked-ignored\n", "tracked build")
        git(clone, "push")
        (clone / ".gitignore").write_text("build/\n", encoding="utf-8")
        git(clone, "add", "--", ".gitignore")
        git(clone, "commit", "-m", "ignore build")
        git(clone, "push")
        (clone / "delete-me.txt").unlink()
        git(clone, "add", "--", "delete-me.txt")
        (clone / "keep.txt").unlink()
        (clone / "build" / "out.bin").write_bytes(b"tracked-ignored-dirty\x00\xff")
        (clone / "payload.bin").write_bytes(b"\x00\xffbinary-untracked")
>       before = source_probe(clone)
                 ^^^^^^^^^^^^
E       NameError: name 'source_probe' is not defined

tests/workspace_provider/test_rescue/_snapshot_index_tests.py:163: NameError
___________ test_snapshot_restores_staged_only_and_distinct_versions ___________

tmp_path = PosixPath('/var/tmp/sase-cf079551/pytest-of-bryan/pytest-28/test_snapshot_restores_staged_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8f1f2d9be0>

    def test_snapshot_restores_staged_only_and_distinct_versions(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        redirect_state(tmp_path, monkeypatch)
        workspace, clone, _remote = seed_remote_clone(tmp_path)
        commit_file(clone, "tracked.txt", "head-bytes\n", "base tracked")
        git(clone, "push")
        (clone / "tracked.txt").write_text("staged-bytes\n", encoding="utf-8")
        git(clone, "add", "--", "tracked.txt")
        (clone / "tracked.txt").write_text("head-bytes\n", encoding="utf-8")
        staged_only = git(clone, "diff", "--cached", "--binary", "HEAD").stdout
        worktree_after_stage = (clone / "tracked.txt").read_text(encoding="utf-8")
        assert worktree_after_stage == "head-bytes\n"
        assert "staged-bytes" in staged_only
>       before = source_probe(clone)
                 ^^^^^^^^^^^^
E       NameError: name 'source_probe' is not defined

tests/workspace_provider/test_rescue/_snapshot_index_tests.py:123: NameError
=============================== warnings summary ===============================
tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/_agent_archive_column_helpers.py:80: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    seen: set[str] = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_lookup.py::test_lookup_owner_of_workflow_child_is_typed
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/dataclasses.py:1789: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    for f in getattr(self, _FIELDS).values():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_prewarm.py::test_prompt_typing_defers_idle_requery
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agents/_archive_shelf.py:129: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    def request_archive_shelf_refresh(owner: Any) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=1899054) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
23.30s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
21.53s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
18.93s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_noop_closes_without_restart
17.05s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
14.15s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
10.42s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
10.36s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
10.30s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
10.12s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
9.99s call     tests/footprint/test_catalog.py::test_generator_is_deterministic
9.48s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
9.38s call     tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
9.13s call     tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
9.12s call     tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
8.91s call     tests/ace/tui/test_agent_archive_shelf_panel_cycle.py::test_jk_wrap_tribe_panels_past_the_visible_archive_shelf
8.68s call     tests/test_project_display_presentation_audit.py::test_path_label_exemptions_name_existing_sites_and_rationales
8.45s call     tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
7.91s call     tests/ace/tui/test_agents_filter_bar_session.py::test_slash_opens_the_bar_and_commits_like_f
7.90s call     tests/ace/tui/test_agents_filter_bar_session.py::test_escape_restores_the_prior_committed_query
7.89s call     tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
=========================== short test summary info ============================
FAILED tests/workspace_provider/test_rescue/test_snapshot.py::test_published_snapshot_carries_local_commits_and_dirty_edits - NameError: name 'source_probe' is not defined
FAILED tests/workspace_provider/test_rescue/test_snapshot.py::test_published_snapshot_thins_a_large_checkout_and_restores_exact_state - NameError: name 'source_probe' is not defined
FAILED tests/workspace_provider/test_rescue/test_snapshot.py::test_snapshot_restores_tracked_and_untracked - NameError: name 'source_probe' is not defined
FAILED tests/workspace_provider/test_rescue/test_snapshot.py::test_snapshot_restores_deletion_binary_and_tracked_ignored - NameError: name 'source_probe' is not defined
FAILED tests/workspace_provider/test_rescue/test_snapshot.py::test_snapshot_restores_staged_only_and_distinct_versions - NameError: name 'source_probe' is not defined
====== 5 failed, 9137 passed, 6 skipped, 8 warnings in 2836.57s (0:47:16) ======
error: recipe `test-scoped` failed on line 624 with exit code 1
scoped: selected 864 of 5453 test files (15.8%; rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost); contexts baseline stale
✗ 1 stage(s) failed; continued past them (first exit 1)
error: recipe `check` failed on line 892 with exit code 1
failed  exit=1  duration=3242724ms
unattrib  21.4s
triage test (scoped): 5 KNOWN continued
KNOWN test (scoped): FAILED tests/workspace_provider/test_rescue/test_snapshot.py::test_published_snapshot_thins_a_large_checkout_and_restores_exact_state - NameError: name 'source_probe' is not defined — witness 22bfd6827fb1ab3efcc70f0a3214bef3; no owner
KNOWN test (scoped): FAILED tests/workspace_provider/test_rescue/test_snapshot.py::test_snapshot_restores_deletion_binary_and_tracked_ignored - NameError: name 'source_probe' is not defined — witness 22bfd6827fb1ab3efcc70f0a3214bef3; no owner
KNOWN test (scoped): FAILED tests/workspace_provider/test_rescue/test_snapshot.py::test_published_snapshot_carries_local_commits_and_dirty_edits - NameError: name 'source_probe' is not defined — witness 22bfd6827fb1ab3efcc70f0a3214bef3; no owner
verdict: no_new_failures — 5 KNOWN; exit 1

