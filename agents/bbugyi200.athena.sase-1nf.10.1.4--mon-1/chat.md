# Chat History - ace-run (sase-1nf.10.1.4--mon-1)

- **TIMESTAMP:** 2026-10-20 21:30:03 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1nf.10.1.4--mon-1

## Prompt

sase monitor start --command 'just check' --reason 'Verify scoped inventory before host completion'

## Response

sase tool run dbc89a0f21c3a783654503218efeba04
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.42.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.42.0 is missing 3 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] classify_publication_error: first appears in sase-core f9aa563 (feat(publication-recovery): add failure accounting and bounded drain selection); no release tag contains it yet.
[core-floor-probe] decide_publication_failure_accounting: first appears in sase-core f9aa563 (feat(publication-recovery): add failure accounting and bounded drain selection); no release tag contains it yet.
[core-floor-probe] select_publication_drain: first appears in sase-core f9aa563 (feat(publication-recovery): add failure accounting and bounded drain selection); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "f9aa563", "name": "classify_publication_error", "release": null, "subject": "feat(publication-recovery): add failure accounting and bounded drain selection"}, {"commit": "f9aa563", "name": "decide_publication_failure_accounting", "release": null, "subject": "feat(publication-recovery): add failure accounting and bounded drain selection"}, {"commit": "f9aa563", "name": "select_publication_drain", "release": null, "subject": "feat(publication-recovery): add failure accounting and bounded drain selection"}], "declared_floor": "0.42.0", "exit_code": 4, "message": "sase-core-rs==0.42.0 is missing 3 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.42.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
selected 169 of 5325 test files (rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost)
coverage contexts: baseline 96183d71b3ef (stale, 4594 commits behind HEAD) matched 4 changed file(s) and contributed 9 test file(s)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 1940 items

tests/ace/tui/test_agents_sync_actions.py .                              [  0%]
tests/ace/tui/test_visual_fixture_host_paths.py .                        [  0%]
tests/agents_sync/test_cli.py ........................                   [  1%]
tests/agents_sync/test_commit_publication.py ....                        [  1%]
tests/agents_sync/test_commit_publication_bounded_drain.py ......        [  1%]
tests/agents_sync/test_commit_publication_drain_accounting.py .....      [  2%]
tests/agents_sync/test_commit_publication_queue.py ......                [  2%]
tests/agents_sync/test_commit_publication_target_resolution.py ......    [  2%]
tests/agents_sync/test_committed_plan_header.py ..                       [  2%]
tests/agents_sync/test_created_epic_ids.py .....                         [  3%]
tests/agents_sync/test_deferred_prompt_archive.py ...                    [  3%]
tests/agents_sync/test_git_sync.py ........................              [  4%]
tests/agents_sync/test_git_sync_outbox.py ............                   [  5%]
tests/agents_sync/test_inventory.py ............                         [  5%]
tests/agents_sync/test_inventory_history.py ........                     [  6%]
tests/agents_sync/test_inventory_scope.py .........                      [  6%]
tests/agents_sync/test_prompt_archive.py ......                          [  6%]
tests/agents_sync/test_prompt_archive_migration.py ....                  [  7%]
tests/agents_sync/test_prompt_archive_objects.py ........                [  7%]
tests/agents_sync/test_prompt_archive_publish.py .....                   [  7%]
tests/agents_sync/test_prompt_archive_validation.py ..........           [  8%]
tests/agents_sync/test_publication.py .......                            [  8%]
tests/agents_sync/test_publication_drain_measure.py .................... [  9%]
.........                                                                [ 10%]
tests/agents_sync/test_publication_manifest.py ..........                [ 10%]
tests/agents_sync/test_publication_reconciliation.py ....                [ 10%]
tests/agents_sync/test_publication_repair.py ..........                  [ 11%]
tests/agents_sync/test_publication_repair_git.py ..                      [ 11%]
tests/agents_sync/test_revival_input_publication.py ....                 [ 11%]
tests/agents_sync/test_status.py .............                           [ 12%]
tests/agents_sync/test_v2_io_apply.py .....                              [ 12%]
tests/agents_sync/test_v2_io_manifest.py .......                         [ 12%]
tests/agents_sync/test_v2_io_run_payload.py ..............               [ 13%]
tests/agents_sync/test_wait_for_beads.py ......                          [ 14%]
tests/core/test_agent_publication_recovery.py ...........                [ 14%]
tests/doctor/test_checks_agent_publication_digest.py ..                  [ 14%]
tests/file_hook_engine/test_commit.py ........                           [ 15%]
tests/llm_provider/test_commit_finalizer_auto_artifact_links_executor.py . [ 15%]
..                                                                       [ 15%]
tests/llm_provider/test_commit_finalizer_auto_bead_reprojection.py ..... [ 15%]
....                                                                     [ 15%]
tests/llm_provider/test_commit_finalizer_auto_sdd_qa.py ............     [ 16%]
tests/llm_provider/test_commit_finalizer_auto_sdd_status.py ..........   [ 16%]
tests/llm_provider/test_commit_finalizer_baseline.py ................... [ 17%]
......                                                                   [ 18%]
tests/llm_provider/test_commit_finalizer_bead_publication.py ....        [ 18%]
tests/llm_provider/test_commit_finalizer_dirty_repo_dedupe.py ..         [ 18%]
tests/llm_provider/test_commit_finalizer_hidden_agents_sidecar.py ...... [ 18%]
                                                                         [ 18%]
tests/llm_provider/test_commit_finalizer_raw_commits.py ................ [ 19%]
..................                                                       [ 20%]
tests/llm_provider/test_commit_finalizer_reserved_paths.py .....         [ 20%]
tests/llm_provider/test_commit_finalizer_sdd_publication_exempt.py ....  [ 20%]
tests/llm_provider/test_commit_finalizer_shared_clone_audit.py ......... [ 21%]
.....                                                                    [ 21%]
tests/llm_provider/test_commit_finalizer_transient_beads_sidecar.py ...  [ 21%]
tests/main/test_agent_prompts_handler.py ...........                     [ 22%]
tests/main/test_agents_dispatch_handler.py ....................          [ 23%]
tests/main/test_default_list_notice_entry.py ..                          [ 23%]
tests/main/test_print_command.py ..............................          [ 25%]
tests/main/test_stitch_create_cli.py ................................... [ 26%]
...................                                                      [ 27%]
tests/main/test_stitch_create_cli_resume_flag.py .....                   [ 28%]
tests/sdd_store/test_sdd_git_streaming.py .....                          [ 28%]
tests/test_agent_session_terminology.py ..                               [ 28%]
tests/test_agent_stop_hook_config.py .                                   [ 28%]
tests/test_agent_tribe_terminology.py ..                                 [ 28%]
tests/test_axe_review_runner_finalization.py ..                          [ 28%]
tests/test_bead/test_bead_page_publication.py ........                   [ 29%]
tests/test_check_sase_core_rs_bindings_tool.py ..........                [ 29%]
tests/test_ci_bootstrap_sidecars_tool.py ..................              [ 30%]
tests/test_commit_publication_inline.py F                                [ 30%]
tests/test_commit_runtime_tags_workflow.py ...                           [ 30%]
tests/test_commit_type_tag_contract.py ..                                [ 30%]
tests/test_commit_workflow_changespec.py .......................         [ 32%]
tests/test_commit_workflow_checkpointing.py .................            [ 32%]
tests/test_commit_workflow_dispatch.py ......................            [ 34%]
tests/test_commit_workflow_hooks.py .....                                [ 34%]
tests/test_commit_workflow_publication.py ............                   [ 35%]
tests/test_commit_workflow_resume.py ...............                     [ 35%]
tests/test_commit_workflow_resume_recovery.py ...........                [ 36%]
tests/test_commit_workflow_resume_tracking.py ......                     [ 36%]
tests/test_config_schema.py ................                             [ 37%]
tests/test_config_schema_ace.py .......................                  [ 38%]
tests/test_config_schema_beads.py ...................                    [ 39%]
tests/test_config_schema_extensions.py ................................. [ 41%]
.............                                                            [ 42%]
tests/test_config_schema_gate_turn.py .....                              [ 42%]
tests/test_config_schema_keymaps.py .................                    [ 43%]
tests/test_config_schema_runtime_limits.py .........................     [ 44%]
tests/test_core_finalizer_facade.py ........                             [ 44%]
tests/test_demo_media_postprocessor.py ............                      [ 45%]
tests/test_exercise_release.py .............                             [ 46%]
tests/test_file_hook_dispatch_regression.py ......s.                     [ 46%]
tests/test_final_prepare.py ................                             [ 47%]
tests/test_finalizer_declaration_channel_recovery.py ........            [ 47%]
tests/test_finalizer_declaration_recovery_evidence.py ........           [ 48%]
tests/test_finalizers_commit_beads_residual.py ......                    [ 48%]
tests/test_finalizers_discard_guard_before_head.py .............         [ 49%]
tests/test_finalizers_live_e2e.py ..............                         [ 49%]
tests/test_finalizers_live_e2e_cycles.py .......                         [ 50%]
tests/test_finalizers_step_channel_live_sink.py ........................ [ 51%]
                                                                         [ 51%]
tests/test_gemini_active_surface_guard.py ..                             [ 51%]
tests/test_github_actions_build_core.py ...........                      [ 52%]
tests/test_github_actions_ci_master_gate.py ............................ [ 53%]
.......                                                                  [ 53%]
tests/test_github_actions_ci_workflow.py ............................... [ 55%]
                                                                         [ 55%]
tests/test_github_actions_install_smoke.py ...................           [ 56%]
tests/test_github_actions_publish.py .....                               [ 56%]
tests/test_github_actions_release.py ..........................          [ 58%]
tests/test_github_actions_release_steward.py .........                   [ 58%]
tests/test_github_actions_setup_sase.py ............                     [ 59%]
tests/test_github_actions_testpypi_drill.py .........                    [ 59%]
tests/test_justfile_lint_check.py ..........................             [ 61%]
tests/test_justfile_lint_lint.py ...............                         [ 61%]
tests/test_justfile_lint_setup.py ....................                   [ 62%]
tests/test_justfile_sase_core_dir.py .....................               [ 63%]
tests/test_macro_terminology.py ..........                               [ 64%]
tests/test_patch_stitch_terminology_audit.py ..................          [ 65%]
tests/test_pr_tags.py ....................................               [ 67%]
tests/test_probe_core_floor_tool.py ........                             [ 67%]
tests/test_project_display_presentation_audit.py .........               [ 68%]
tests/test_project_pr_prefix.py .............                            [ 68%]
tests/test_prompt_prediction_replay_sources.py ......                    [ 69%]
tests/test_ratchet_core_revision_tool.py ...........                     [ 69%]
tests/test_ratchet_core_window_source_normalization.py ..........        [ 70%]
tests/test_ratchet_core_window_tool_core.py .                            [ 70%]
tests/test_ratchet_core_window_tool_guardrails.py .......                [ 70%]
tests/test_ratchet_core_window_tool_modes.py ........                    [ 70%]
tests/test_ratchet_core_window_tool_reconciliation.py .......            [ 71%]
tests/test_release_candidate_inventory.py .............................. [ 72%]
.....                                                                    [ 73%]
tests/test_release_candidate_published_core.py ...................       [ 74%]
tests/test_release_candidate_qualify_red.py ...                          [ 74%]
tests/test_release_candidate_rerun.py ...........                        [ 74%]
tests/test_release_candidate_seal.py ...................                 [ 75%]
tests/test_release_core.py .......................                       [ 77%]
tests/test_require_tool_run.py .................                         [ 77%]
tests/test_ruff_config.py .                                              [ 77%]
tests/test_run_pytest_command.py ................................        [ 79%]
tests/test_run_pytest_contention.py ...................                  [ 80%]
tests/test_run_pytest_health.py .....                                    [ 80%]
tests/test_run_pytest_main.py .............                              [ 81%]
tests/test_run_pytest_scoped.py ..............                           [ 82%]
tests/test_run_pytest_tmpdir.py ...................                      [ 83%]
tests/test_run_pytest_workers.py ...................                     [ 84%]
tests/test_rust_install_cleanup.py ..                                    [ 84%]
tests/test_sase_bead_tool.py ....                                        [ 84%]
tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py ..          [ 84%]
tests/test_sase_core_rs_bead_resolution_smoke_tool.py .                  [ 84%]
tests/test_sase_core_rs_feature_flag_state_smoke_tool.py ..              [ 84%]
tests/test_sase_core_rs_glossary_line_break_smoke_tool.py ..             [ 84%]
tests/test_sase_core_rs_plan_header_smoke_tool.py ..                     [ 84%]
tests/test_sase_core_rs_telemetry_smoke_tool.py .....                    [ 85%]
tests/test_sase_core_wheel_cache_tool.py ...........                     [ 85%]
tests/test_sase_migrate_statuses.py ...                                  [ 85%]
tests/test_sase_turn_terminology.py ...                                  [ 86%]
tests/test_sdd_canonical_layout.py ..                                    [ 86%]
tests/test_setup_required_plugins_tool.py ...................            [ 87%]
tests/test_suite_gate.py .................                               [ 88%]
tests/test_suite_gate_budget.py ...............                          [ 88%]
tests/test_suite_gate_lease.py ...........                               [ 89%]
tests/test_suite_gate_reclaim.py ..............                          [ 90%]
tests/test_timezone_display_guard.py .                                   [ 90%]
tests/test_timezone_runtime_consistency.py ......................        [ 91%]
tests/test_tool_adoption_report_tool.py .........................        [ 92%]
tests/test_validate_changelog_tool.py ......                             [ 92%]
tests/test_validate_dependency_group_tool.py ...                         [ 93%]
tests/test_validate_sase_core_rs_contracts_fleet_tool.py ....            [ 93%]
tests/test_validate_sase_core_rs_contracts_provider_tool.py ...          [ 93%]
tests/test_validate_sase_core_rs_contracts_tool.py ..........            [ 93%]
tests/test_validate_sase_core_rs_environment_tool.py ........            [ 94%]
tests/test_validate_sase_core_rs_prompt_tool.py .....                    [ 94%]
tests/test_validate_sase_core_rs_runtime_tool.py ...............         [ 95%]
tests/test_validate_sase_core_rs_tool.py .................               [ 96%]
tests/test_validate_sase_core_rs_version_tool.py ..............          [ 96%]
tests/test_validate_test_environment_tool.py ....................        [ 97%]
tests/workflows/test_commit_workflow.py ........ssss..................   [ 99%]
tests/workflows/test_commit_workflow_message_gate.py .........           [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.



=================================== FAILURES ===================================
____ test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning ____

inline_publication = _Fixture(primary=PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-12/test_tagged_commit_publishes_a0/primary')...h=PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-12/test_tagged_commit_publishes_a0/plans/202608/inline.md'))

    def test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning(
        inline_publication: _Fixture,
    ) -> None:
        fixture = inline_publication
        cp = CommitCheckpoint(
            method="create_commit",
            payload={"message": _MESSAGE},
            cwd=str(fixture.primary),
            primary_revision=_REVISION,
            publication_agent=_AGENT,
        )
    
        assert run_agent_publication_step(
            cp,
            "create_commit",
            checkpoint_save=lambda _cp: None,
            get_vcs_provider=lambda _cwd: pytest.fail("revision is already resolved"),
        )
    
        # The beads sidecar holds the rendered lineage, pushed to its remote.
        beads_remote_paths = _remote_paths(fixture.beads_remote)
        assert "pages/sase-fa/README.md" in beads_remote_paths
        assert "pages/sase-fa/sase-fa.1.md" in beads_remote_paths
    
        # The plan header was rewritten and pushed.
        plans_remote_paths = _remote_paths(fixture.plans_remote)
        assert "202608/inline.md" in plans_remote_paths
    
        # The agent hood and its prompt archive reached the agents remote, so the
        # footer URL written into this commit resolves immediately.
        agents_remote_paths = _remote_paths(fixture.agents_remote)
        assert "agents/alice.athena.worker/README.md" in agents_remote_paths
        assert "prompts/202608/inline.md" in agents_remote_paths
    
        # Nothing was deferred to a background lane.
>       assert list_agent_publications("proj") == ()
E       AssertionError: assert (AgentPublica...016.3632627),) == ()
E         
E         Left contains one more item: AgentPublicationOutboxItem(project_key='proj', project='Project', local_agent='worker', global_agent='alice.athena.wor...uarantined_at=None, terminal=False, terminal_reason=None, created_at=1792546016.1245878, updated_at=1792546016.3632627)
E         
E         Full diff:
E         - ()
E         + (
E         +     AgentPublicationOutboxItem(
E         +         project_key='proj',
E         +         project='Project',
E         +         local_agent='worker',
E         +         global_agent='alice.athena.worker',
E         +         primary_revision='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa',
E         +         local_hood='worker',
E         +         hood_digest='dddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddd',
E         +         attempts=1,
E         +         last_error='could not restore deferred prompt archive for '
E         +                    'alice.athena.worker@aaaaaaaaaaaa: prompt archive is '
E         +                    'unresolved and a missing local source does not prove there '
E         +                    'was no prompt obligation',
E         +         quarantined=False,
E         +         quarantined_at=None,
E         +         terminal=False,
E         +         terminal_reason=None,
E         +         created_at=1792546016.1245878,
E         +         updated_at=1792546016.3632627,
E         +     ),
E         + )

tests/test_commit_publication_inline.py:326: AssertionError
----------------------------- Captured stdout call -----------------------------
⚠️ Primary commit succeeded; agent-hood publication is queued and will retry 
automatically. Last error: could not restore deferred prompt archive for 
alice.athena.worker@aaaaaaaaaaaa: prompt archive is unresolved and a missing 
local source does not prove there was no prompt obligation
============================= slowest 20 durations =============================
19.55s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
19.23s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
8.73s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
7.69s call     tests/test_project_display_presentation_audit.py::test_path_label_exemptions_name_existing_sites_and_rationales
7.14s call     tests/test_project_display_presentation_audit.py::test_project_labels_never_derive_from_paths
7.11s call     tests/test_finalizers_live_e2e_cycles.py::test_live_command_and_fixture_plugin_run_in_order
5.91s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
5.20s call     tests/agents_sync/test_commit_publication_bounded_drain.py::test_manifest_timeout_cleans_regenerable_paths_and_preserves_objects
4.03s call     tests/test_gemini_active_surface_guard.py::test_no_gemini_cli_provider_surface_in_active_tree
2.16s call     tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms
2.14s call     tests/test_macro_terminology.py::test_macro_imports_avoid_xprompt_modules
2.00s call     tests/test_finalizers_step_channel_live_sink.py::test_timeout_kill_leaves_live
1.90s call     tests/test_finalizers_discard_guard_before_head.py::test_post_dispatch_revert_on_external_still_fails
1.85s call     tests/test_sase_turn_terminology.py::test_current_source_avoids_shell_concept_identifiers
1.73s call     tests/test_finalizers_discard_guard_before_head.py::test_post_dispatch_unpushed_foreign_race_still_fails
1.69s call     tests/test_macro_terminology.py::test_macro_source_avoids_xprompt_identifiers
1.68s call     tests/test_finalizers_commit_beads_residual.py::test_unpublishable_late_bead_commit_fails_with_recovery_path
1.67s call     tests/test_finalizers_discard_guard_before_head.py::test_post_dispatch_foreign_race_on_external_is_exempt
1.63s call     tests/test_finalizers_live_e2e_cycles.py::test_live_first_repo_conflict_blocks_second_then_resumes
1.63s call     tests/test_finalizers_live_e2e_cycles.py::test_live_later_finalizer_dirt_reactivates_commit
=========================== short test summary info ============================
FAILED tests/test_commit_publication_inline.py::test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning - AssertionError: assert (AgentPublica...016.3632627),) == ()
  
  Left contains one more item: AgentPublicationOutboxItem(project_key='proj', project='Project', local_agent='worker', global_agent='alice.athena.wor...uarantined_at=None, terminal=False, terminal_reason=None, created_at=1792546016.1245878, updated_at=1792546016.3632627)
  
  Full diff:
  - ()
  + (
  +     AgentPublicationOutboxItem(
  +         project_key='proj',
  +         project='Project',
  +         local_agent='worker',
  +         global_agent='alice.athena.worker',
  +         primary_revision='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa',
  +         local_hood='worker',
  +         hood_digest='dddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddd',
  +         attempts=1,
  +         last_error='could not restore deferred prompt archive for '
  +                    'alice.athena.worker@aaaaaaaaaaaa: prompt archive is '
  +                    'unresolved and a missing local source does not prove there '
  +                    'was no prompt obligation',
  +         quarantined=False,
  +         quarantined_at=None,
  +         terminal=False,
  +         terminal_reason=None,
  +         created_at=1792546016.1245878,
  +         updated_at=1792546016.3632627,
  +     ),
  + )
============ 1 failed, 1934 passed, 5 skipped in 270.19s (0:04:30) =============
error: recipe `test-scoped` failed on line 595 with exit code 1
error: recipe `check` failed on line 861 with exit code 1
failed  exit=1  duration=533435ms
unattrib  6.7s
triage test (scoped): 1 NEW stopped
NEW test (scoped): FAILED tests/test_commit_publication_inline.py::test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning - AssertionError: assert (AgentPublica...016.3632627),) == () — recorded evidence; no owner
verdict: new_failures — 1 NEW; exit 1

