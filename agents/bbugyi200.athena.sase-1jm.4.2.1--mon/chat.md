# Chat History - ace-run (sase-1jm.4.2.1--mon)

- **TIMESTAMP:** 2026-10-12 07:38:13 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1jm.4.2.1--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'finish check (joined run)'

## Response

sase tool run 344a6ffab71903b926876208839e2ed8
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.38.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ fmt (python)
✓ fmt (markdown)
✓ fmt (generated docs)
✓ model policy
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✗ lint (symvision)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.38.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol 'sase-1jm(archive_corpus_is_warm)' --epic-symbol 'sase-1jx.8(evaluate_repo_creation_form)' --epic-symbol 'sase-1jx.11(NewProjectModal)' --epic-symbol 'sase-1jx.11(NewProjectSelection)' --epic-symbol 'sase-1jx.12(record_owner_selection)' --epic-symbol 'sase-1jx.12(record_visibility_selection)' --epic-symbol 'sase-1jx.10.1.4(run_project_init)' 
Error: --epic-symbol 'sase-1jx.8(evaluate_repo_creation_form)': bead 'sase-1jx.8' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
error: recipe `_lint-symvision` failed on line 455 with exit code 1
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.35.0 is missing 146 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] PromptPredictionCorpus: first appears in sase-core 12e012d (feat(core-binding): add prompt_prediction binding module with tests); release v0.36.1 contains it.
[core-floor-probe] PromptPredictionModel: first appears in sase-core 12e012d (feat(core-binding): add prompt_prediction binding module with tests); release v0.36.1 contains it.
[core-floor-probe] ack_agent_completions: first appears in sase-core 28befcb (feat(notifications): store generations, ack API, and lean unread index); release v0.36.2 contains it.
[core-floor-probe] advance_auto_restart_ledger: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] agent_auto_restart_wire_schema_version: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] alternation_scan: first appears in sase-core 1e51ff3 (feat(alternation): shared scanner, binding, diagnostic, and LSP tokens); release v0.36.1 contains it.
[core-floor-probe] argument_list_continuation_edit: first appears in sase-core 2f16dc4 (feat(editor): continue existing macro argument lists); release v0.36.6 contains it.
[core-floor-probe] attachment_audience_decision: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_canonical_extension: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_object_digest_from_relpath: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_placement: first appears in sase-core 43f744b (feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy); release v0.36.1 contains it.
[core-floor-probe] attachment_public_object_relpath: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_scan_file: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_scanner_rules_version: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_sensitive_path_reason: first appears in sase-core 43f744b (feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy); release v0.36.1 contains it.
[core-floor-probe] attachment_should_auto_fetch: first appears in sase-core 43f744b (feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy); release v0.36.1 contains it.
[core-floor-probe] auto_restart_lineage_root: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] auto_restart_recovery_is_in_flight: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] autonomy_append_decision: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_decision_sentence: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_evaluate: first appears in sase-core 01b0ad7 (feat(autonomy): add core record, compatibility profiles, and evaluate()); release v0.37.1 contains it.
[core-floor-probe] autonomy_inherit: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_legacy_projection: first appears in sase-core 01b0ad7 (feat(autonomy): add core record, compatibility profiles, and evaluate()); release v0.37.1 contains it.
[core-floor-probe] autonomy_mutate: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_profiles: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_read_decisions: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_record_from_legacy_meta: first appears in sase-core 01b0ad7 (feat(autonomy): add core record, compatibility profiles, and evaluate()); release v0.37.1 contains it.
[core-floor-probe] autonomy_resolve_selection: first appears in sase-core 01b0ad7 (feat(autonomy): add core record, compatibility profiles, and evaluate()); release v0.37.1 contains it.
[core-floor-probe] autonomy_summary: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] bead_probe_target_owner: first appears in sase-core bff4860 (feat(bead): one-replay core support for in-mutation resolution and target probing); release v0.37.1 contains it.
[core-floor-probe] build_agent_tab_catalog: first appears in sase-core c448ed6 (feat(agent-tab): core tab model with directive, typed units, and Python bindings); release v0.36.0 contains it.
[core-floor-probe] canonicalize_agent_tab_name: first appears in sase-core c448ed6 (feat(agent-tab): core tab model with directive, typed units, and Python bindings); release v0.36.0 contains it.
[core-floor-probe] check_input_value: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] claim_auto_restart_ledger: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] classify_agent_failure: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] classify_attachment: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] classify_auto_directive: first appears in sase-core e8606a5 (feat(auto): fail-closed %auto grammar classifier in sase-core); release v0.37.1 contains it.
[core-floor-probe] classify_deferred_prompt_obligation: first appears in sase-core 3d406d4 (feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status); release v0.36.5 contains it.
[core-floor-probe] classify_git_lock_failure: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] classify_git_lock_owner: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] classify_model_value: first appears in sase-core 16095fc (feat(macros): add builtin model and effort types with one routing classifier); release v0.36.6 contains it.
[core-floor-probe] classify_project_candidates: first appears in sase-core aaec3bf (feat(project-onboarding): classify candidates and evaluate creation forms); no release tag contains it yet.
[core-floor-probe] classify_session_manifest_files: first appears in sase-core d7f2dbf (feat(agent-session-manifest): canonical file-set derivation and classification); release v0.36.5 contains it.
[core-floor-probe] compare_prose: first appears in sase-core 3b27df5 (feat(prose-diff): add pure sase-core prose_diff module and Python binding); release v0.36.2 contains it.
[core-floor-probe] compile_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] compose_note_attachment_text: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] count_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] decide_eager_git_lock_cleanup: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] decide_git_lock_recovery: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] decide_publication_request_completion: first appears in sase-core 3d406d4 (feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status); release v0.36.5 contains it.
[core-floor-probe] default_git_lock_retry_delays: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] derive_auto_restart_episode: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] editor_snippet_catalog_wire_schema_version: first appears in sase-core a62699b (feat(macros)!: emit canonical macro wires and snippet catalog schema 2); release v0.37.0 contains it.
[core-floor-probe] evaluate_prompt_prediction_replay: first appears in sase-core 1ad57ea (feat(prompt-prediction): add per-point novel coverage and precision to sweep wire); release v0.36.1 contains it.
[core-floor-probe] evaluate_repo_creation_form: first appears in sase-core aaec3bf (feat(project-onboarding): classify candidates and evaluate creation forms); no release tag contains it yet.
[core-floor-probe] git_lock_wire_schema_version: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] goal_card_markdown: first appears in sase-core 33b0250 (feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)); release v0.36.0 contains it.
[core-floor-probe] goal_card_view: first appears in sase-core 33b0250 (feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)); release v0.36.0 contains it.
[core-floor-probe] goal_citation_line: first appears in sase-core 33b0250 (feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)); release v0.36.0 contains it.
[core-floor-probe] goal_fast_path: first appears in sase-core d2d9ec7 (feat(goals): add goal ledger, fast path, and terminal renderer backend); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_append: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_doctor: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_history: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_init: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_list: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_probe_list: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_show: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_store_schema_version: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_wire_schema_version: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_mint_id: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_projection_refresh: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_projection_status: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_render_card: first appears in sase-core d2d9ec7 (feat(goals): add goal ledger, fast path, and terminal renderer backend); release v0.36.0 contains it.
[core-floor-probe] goal_render_list: first appears in sase-core d2d9ec7 (feat(goals): add goal ledger, fast path, and terminal renderer backend); release v0.36.0 contains it.
[core-floor-probe] instruction_manifest_wire_schema_version: first appears in sase-core fa39036 (feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)); release v0.37.1 contains it.
[core-floor-probe] jinja_catalog: first appears in sase-core 3adc01b (feat(editor-completion): add jinja completion bindings and tests); release v0.36.2 contains it.
[core-floor-probe] jinja_completion: first appears in sase-core 3adc01b (feat(editor-completion): add jinja completion bindings and tests); release v0.36.2 contains it.
[core-floor-probe] jinja_scope_variables: first appears in sase-core 3adc01b (feat(editor-completion): add jinja completion bindings and tests); release v0.36.2 contains it.
[core-floor-probe] launch_scratch_liveness_wire_schema_version: first appears in sase-core 297bc1e (feat(core): launch_scratch_liveness module with procfs probe bindings); release v0.36.0 contains it.
[core-floor-probe] load_macro_input_type_registry: first appears in sase-core af5df61 (feat(core): load plugin input_type registries with resolution, catalog, and LSP wiring); release v0.37.0 contains it.
[core-floor-probe] lookup_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] macro_argument_choice_candidates: first appears in sase-core 0d27dad (feat(macros): carry resolved choice metadata and shared candidates); release v0.36.6 contains it.
[core-floor-probe] macro_argument_spans: first appears in sase-core c4444ab (feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output); release v0.36.3 contains it.
[core-floor-probe] macro_completion_spacer_to_parentheses_edit: first appears in sase-core 0279de6 (feat(macros): flip emitted wires to macro spellings, rename LSP crate); release v0.36.6 contains it.
[core-floor-probe] macro_input_type_catalog: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] macro_input_type_label: first appears in sase-core 0d27dad (feat(macros): carry resolved choice metadata and shared candidates); release v0.36.6 contains it.
[core-floor-probe] macro_skill_definition_wire_schema_version: first appears in sase-core c4444ab (feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output); release v0.36.3 contains it.
[core-floor-probe] managed_tmp_roots_list: first appears in sase-core 924884e (feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)); release v0.36.0 contains it.
[core-floor-probe] managed_tmp_roots_register: first appears in sase-core 924884e (feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)); release v0.36.0 contains it.
[core-floor-probe] managed_tmp_roots_wire_schema_version: first appears in sase-core 924884e (feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)); release v0.36.0 contains it.
[core-floor-probe] match_git_lock_path: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] memory_history_compare: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_feed: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_mark_reviewed: first appears in sase-core c2a415e (feat(memory-history): add review state store with query and mark-reviewed); release v0.36.4 contains it.
[core-floor-probe] memory_history_resolve: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_review_state: first appears in sase-core c2a415e (feat(memory-history): add review state store with query and mark-reviewed); release v0.36.4 contains it.
[core-floor-probe] memory_history_subjects: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_sync: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_timeline: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_version: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_wire_schema_version: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] normalize_instruction_manifest: first appears in sase-core fa39036 (feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)); release v0.37.1 contains it.
[core-floor-probe] normalize_macro_config_layer: first appears in sase-core 4eb40d5 (feat(compat): shared Rust config normalization contract); release v0.36.4 contains it.
[core-floor-probe] observe_launch_scratch_liveness: first appears in sase-core 297bc1e (feat(core): launch_scratch_liveness module with procfs probe bindings); release v0.36.0 contains it.
[core-floor-probe] parse_git_lock_retry_delays: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] plan_decision_quote_match: first appears in sase-core df735e4 (feat(sase-core): add plan decision human quote matcher with PyO3 binding); release v0.37.1 contains it.
[core-floor-probe] plan_decision_sheet: first appears in sase-core 88d6385 (feat(plan): add decision sheet, summary, and prompt-block backend); release v0.37.1 contains it.
[core-floor-probe] plan_decision_summary: first appears in sase-core 88d6385 (feat(plan): add decision sheet, summary, and prompt-block backend); release v0.37.1 contains it.
[core-floor-probe] plan_decisions_digest: first appears in sase-core c089cf1 (feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings); release v0.37.1 contains it.
[core-floor-probe] plan_decisions_payload: first appears in sase-core c089cf1 (feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings); release v0.37.1 contains it.
[core-floor-probe] plan_decisions_prompt_block: first appears in sase-core 88d6385 (feat(plan): add decision sheet, summary, and prompt-block backend); release v0.37.1 contains it.
[core-floor-probe] plan_decisions_resolve: first appears in sase-core c089cf1 (feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings); release v0.37.1 contains it.
[core-floor-probe] plan_project_onboarding: first appears in sase-core 792255d (feat(project-onboarding): derive ordered onboarding plans from facts); no release tag contains it yet.
[core-floor-probe] project_finalizer_node_view: first appears in sase-core f52fa7c (feat(finalizer): implement core-run-view-model run_view module); release v0.35.1 contains it.
[core-floor-probe] project_onboarding_wire_schema_version: first appears in sase-core aaec3bf (feat(project-onboarding): classify candidates and evaluate creation forms); no release tag contains it yet.
[core-floor-probe] prompt_looks_generated: first appears in sase-core 0ad6e44 (feat(prompt-prediction): flag chop and job tribe origins as generated); release v0.36.2 contains it.
[core-floor-probe] prompt_prediction_wire_schema_version: first appears in sase-core 12e012d (feat(core-binding): add prompt_prediction binding module with tests); release v0.36.1 contains it.
[core-floor-probe] prompt_proc_origin: first appears in sase-core 92a4fc4 (feat(agent-launch): add native %proc dispatch helpers); release v0.31.5 contains it.
[core-floor-probe] read_prompt_stash_archive: first appears in sase-core df23cce (feat(prompt-stash): append-only archive for every permanent stash removal); release v0.36.1 contains it.
[core-floor-probe] read_unread_completion_index: first appears in sase-core 28befcb (feat(notifications): store generations, ack API, and lean unread index); release v0.36.2 contains it.
[core-floor-probe] reconcile_notification_rows: first appears in sase-core 413511f (feat(notifications): lock-held field-scoped reconcile write plus empty raw_suffix matcher parity); release v0.36.1 contains it.
[core-floor-probe] recover_prompt_stash_archive: first appears in sase-core df23cce (feat(prompt-stash): append-only archive for every permanent stash removal); release v0.36.1 contains it.
[core-floor-probe] resolve_input_type: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] resolve_macro_skill_definition: first appears in sase-core c4444ab (feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output); release v0.36.3 contains it.
[core-floor-probe] rows_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] sanitize_attachment_name: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] scan_note_attachment_refs: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] select_publication_retries: first appears in sase-core 3d406d4 (feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status); release v0.36.5 contains it.
[core-floor-probe] status_bucket_for_status: first appears in sase-core 9f6ce0c (feat(agent-archive): add live status-bucket match with outcome derived from bucket); release v0.38.0 contains it.
[core-floor-probe] summarize_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] summarize_agent_models: first appears in sase-core a95609e (feat(core): expose session agent model summaries); release v0.38.0 contains it.
[core-floor-probe] tool_run_briefs: first appears in sase-core 9368ddf (feat(tool-run): add live glance, briefs, and node-summary projections); release v0.36.0 contains it.
[core-floor-probe] tool_run_detail: first appears in sase-core 830e900 (feat(tool-run): add tool_run_detail projection with stage timeline and witness counts); release v0.36.0 contains it.
[core-floor-probe] tool_run_duration_calibration: first appears in sase-core 17b072b (feat(tool-run): add duration classes and inline-fit policy); release v0.36.1 contains it.
[core-floor-probe] tool_run_duration_fit: first appears in sase-core 17b072b (feat(tool-run): add duration classes and inline-fit policy); release v0.36.1 contains it.
[core-floor-probe] tool_run_join: first appears in sase-core cee9f49 (feat(tool-run): add detached starter scope, monitor join, and sync wait budget); release v0.36.1 contains it.
[core-floor-probe] tool_run_live_glance: first appears in sase-core 9368ddf (feat(tool-run): add live glance, briefs, and node-summary projections); release v0.36.0 contains it.
[core-floor-probe] tool_run_node_summaries: first appears in sase-core 9368ddf (feat(tool-run): add live glance, briefs, and node-summary projections); release v0.36.0 contains it.
[core-floor-probe] tool_run_record_demand: first appears in sase-core 7a9ffad (feat(tool-run): record per-run demand context, usage, and worker grants); release v0.36.2 contains it.
[core-floor-probe] tool_run_release_join: first appears in sase-core cee9f49 (feat(tool-run): add detached starter scope, monitor join, and sync wait budget); release v0.36.1 contains it.
[core-floor-probe] tool_run_stats_report: first appears in sase-core 6e23783 (feat(tool-run): implement core-stats report for sase-1dm.3); release v0.36.2 contains it.
[core-floor-probe] tool_run_sync_wait_budget: first appears in sase-core cee9f49 (feat(tool-run): add detached starter scope, monitor join, and sync wait budget); release v0.36.1 contains it.
[core-floor-probe] unique_attachment_name: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] validate_enum_choices: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] validate_git_lock_retry_delays: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] wait_epic_follow_reduce: first appears in sase-core 4b4a052 (feat(wait): add pure wait_epic_follow reducer with Python binding (sase-1h7.4)); release v0.37.1 contains it.
{"cache_hit": true, "capabilities": [{"commit": "12e012d", "name": "PromptPredictionCorpus", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "12e012d", "name": "PromptPredictionModel", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "28befcb", "name": "ack_agent_completions", "release": "v0.36.2", "subject": "feat(notifications): store generations, ack API, and lean unread index"}, {"commit": "d4ad8c9", "name": "advance_auto_restart_ledger", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "d4ad8c9", "name": "agent_auto_restart_wire_schema_version", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "1e51ff3", "name": "alternation_scan", "release": "v0.36.1", "subject": "feat(alternation): shared scanner, binding, diagnostic, and LSP tokens"}, {"commit": "2f16dc4", "name": "argument_list_continuation_edit", "release": "v0.36.6", "subject": "feat(editor): continue existing macro argument lists"}, {"commit": "7806f58", "name": "attachment_audience_decision", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_canonical_extension", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_object_digest_from_relpath", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "43f744b", "name": "attachment_placement", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "7806f58", "name": "attachment_public_object_relpath", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_scan_file", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_scanner_rules_version", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "43f744b", "name": "attachment_sensitive_path_reason", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "43f744b", "name": "attachment_should_auto_fetch", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "d4ad8c9", "name": "auto_restart_lineage_root", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "d4ad8c9", "name": "auto_restart_recovery_is_in_flight", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "51b66fd", "name": "autonomy_append_decision", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "51b66fd", "name": "autonomy_decision_sentence", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "01b0ad7", "name": "autonomy_evaluate", "release": "v0.37.1", "subject": "feat(autonomy): add core record, compatibility profiles, and evaluate()"}, {"commit": "51b66fd", "name": "autonomy_inherit", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "01b0ad7", "name": "autonomy_legacy_projection", "release": "v0.37.1", "subject": "feat(autonomy): add core record, compatibility profiles, and evaluate()"}, {"commit": "51b66fd", "name": "autonomy_mutate", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "51b66fd", "name": "autonomy_profiles", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "51b66fd", "name": "autonomy_read_decisions", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "01b0ad7", "name": "autonomy_record_from_legacy_meta", "release": "v0.37.1", "subject": "feat(autonomy): add core record, compatibility profiles, and evaluate()"}, {"commit": "01b0ad7", "name": "autonomy_resolve_selection", "release": "v0.37.1", "subject": "feat(autonomy): add core record, compatibility profiles, and evaluate()"}, {"commit": "51b66fd", "name": "autonomy_summary", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "bff4860", "name": "bead_probe_target_owner", "release": "v0.37.1", "subject": "feat(bead): one-replay core support for in-mutation resolution and target probing"}, {"commit": "c448ed6", "name": "build_agent_tab_catalog", "release": "v0.36.0", "subject": "feat(agent-tab): core tab model with directive, typed units, and Python bindings"}, {"commit": "c448ed6", "name": "canonicalize_agent_tab_name", "release": "v0.36.0", "subject": "feat(agent-tab): core tab model with directive, typed units, and Python bindings"}, {"commit": "2838c7e", "name": "check_input_value", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "d4ad8c9", "name": "claim_auto_restart_ledger", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "d4ad8c9", "name": "classify_agent_failure", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "39324ac", "name": "classify_attachment", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "e8606a5", "name": "classify_auto_directive", "release": "v0.37.1", "subject": "feat(auto): fail-closed %auto grammar classifier in sase-core"}, {"commit": "3d406d4", "name": "classify_deferred_prompt_obligation", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "47b28fb", "name": "classify_git_lock_failure", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "47b28fb", "name": "classify_git_lock_owner", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "16095fc", "name": "classify_model_value", "release": "v0.36.6", "subject": "feat(macros): add builtin model and effort types with one routing classifier"}, {"commit": "aaec3bf", "name": "classify_project_candidates", "release": null, "subject": "feat(project-onboarding): classify candidates and evaluate creation forms"}, {"commit": "d7f2dbf", "name": "classify_session_manifest_files", "release": "v0.36.5", "subject": "feat(agent-session-manifest): canonical file-set derivation and classification"}, {"commit": "3b27df5", "name": "compare_prose", "release": "v0.36.2", "subject": "feat(prose-diff): add pure sase-core prose_diff module and Python binding"}, {"commit": "bc40675", "name": "compile_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "39324ac", "name": "compose_note_attachment_text", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "bc40675", "name": "count_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "47b28fb", "name": "decide_eager_git_lock_cleanup", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "47b28fb", "name": "decide_git_lock_recovery", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "3d406d4", "name": "decide_publication_request_completion", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "47b28fb", "name": "default_git_lock_retry_delays", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "d4ad8c9", "name": "derive_auto_restart_episode", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "a62699b", "name": "editor_snippet_catalog_wire_schema_version", "release": "v0.37.0", "subject": "feat(macros)!: emit canonical macro wires and snippet catalog schema 2"}, {"commit": "1ad57ea", "name": "evaluate_prompt_prediction_replay", "release": "v0.36.1", "subject": "feat(prompt-prediction): add per-point novel coverage and precision to sweep wire"}, {"commit": "aaec3bf", "name": "evaluate_repo_creation_form", "release": null, "subject": "feat(project-onboarding): classify candidates and evaluate creation forms"}, {"commit": "47b28fb", "name": "git_lock_wire_schema_version", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "33b0250", "name": "goal_card_markdown", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "33b0250", "name": "goal_card_view", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "33b0250", "name": "goal_citation_line", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "d2d9ec7", "name": "goal_fast_path", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "cbe70f6", "name": "goal_ledger_append", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_doctor", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_history", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_init", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_list", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_probe_list", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_show", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_store_schema_version", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_wire_schema_version", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_mint_id", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_projection_refresh", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_projection_status", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "d2d9ec7", "name": "goal_render_card", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "d2d9ec7", "name": "goal_render_list", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "fa39036", "name": "instruction_manifest_wire_schema_version", "release": "v0.37.1", "subject": "feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)"}, {"commit": "3adc01b", "name": "jinja_catalog", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "3adc01b", "name": "jinja_completion", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "3adc01b", "name": "jinja_scope_variables", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "297bc1e", "name": "launch_scratch_liveness_wire_schema_version", "release": "v0.36.0", "subject": "feat(core): launch_scratch_liveness module with procfs probe bindings"}, {"commit": "af5df61", "name": "load_macro_input_type_registry", "release": "v0.37.0", "subject": "feat(core): load plugin input_type registries with resolution, catalog, and LSP wiring"}, {"commit": "bc40675", "name": "lookup_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "0d27dad", "name": "macro_argument_choice_candidates", "release": "v0.36.6", "subject": "feat(macros): carry resolved choice metadata and shared candidates"}, {"commit": "c4444ab", "name": "macro_argument_spans", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "0279de6", "name": "macro_completion_spacer_to_parentheses_edit", "release": "v0.36.6", "subject": "feat(macros): flip emitted wires to macro spellings, rename LSP crate"}, {"commit": "2838c7e", "name": "macro_input_type_catalog", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "0d27dad", "name": "macro_input_type_label", "release": "v0.36.6", "subject": "feat(macros): carry resolved choice metadata and shared candidates"}, {"commit": "c4444ab", "name": "macro_skill_definition_wire_schema_version", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "924884e", "name": "managed_tmp_roots_list", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "924884e", "name": "managed_tmp_roots_register", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "924884e", "name": "managed_tmp_roots_wire_schema_version", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "47b28fb", "name": "match_git_lock_path", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "11f29c3", "name": "memory_history_compare", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_feed", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "c2a415e", "name": "memory_history_mark_reviewed", "release": "v0.36.4", "subject": "feat(memory-history): add review state store with query and mark-reviewed"}, {"commit": "11f29c3", "name": "memory_history_resolve", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "c2a415e", "name": "memory_history_review_state", "release": "v0.36.4", "subject": "feat(memory-history): add review state store with query and mark-reviewed"}, {"commit": "11f29c3", "name": "memory_history_subjects", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_sync", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_timeline", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_version", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_wire_schema_version", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "fa39036", "name": "normalize_instruction_manifest", "release": "v0.37.1", "subject": "feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)"}, {"commit": "4eb40d5", "name": "normalize_macro_config_layer", "release": "v0.36.4", "subject": "feat(compat): shared Rust config normalization contract"}, {"commit": "297bc1e", "name": "observe_launch_scratch_liveness", "release": "v0.36.0", "subject": "feat(core): launch_scratch_liveness module with procfs probe bindings"}, {"commit": "47b28fb", "name": "parse_git_lock_retry_delays", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "df735e4", "name": "plan_decision_quote_match", "release": "v0.37.1", "subject": "feat(sase-core): add plan decision human quote matcher with PyO3 binding"}, {"commit": "88d6385", "name": "plan_decision_sheet", "release": "v0.37.1", "subject": "feat(plan): add decision sheet, summary, and prompt-block backend"}, {"commit": "88d6385", "name": "plan_decision_summary", "release": "v0.37.1", "subject": "feat(plan): add decision sheet, summary, and prompt-block backend"}, {"commit": "c089cf1", "name": "plan_decisions_digest", "release": "v0.37.1", "subject": "feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings"}, {"commit": "c089cf1", "name": "plan_decisions_payload", "release": "v0.37.1", "subject": "feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings"}, {"commit": "88d6385", "name": "plan_decisions_prompt_block", "release": "v0.37.1", "subject": "feat(plan): add decision sheet, summary, and prompt-block backend"}, {"commit": "c089cf1", "name": "plan_decisions_resolve", "release": "v0.37.1", "subject": "feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings"}, {"commit": "792255d", "name": "plan_project_onboarding", "release": null, "subject": "feat(project-onboarding): derive ordered onboarding plans from facts"}, {"commit": "f52fa7c", "name": "project_finalizer_node_view", "release": "v0.35.1", "subject": "feat(finalizer): implement core-run-view-model run_view module"}, {"commit": "aaec3bf", "name": "project_onboarding_wire_schema_version", "release": null, "subject": "feat(project-onboarding): classify candidates and evaluate creation forms"}, {"commit": "0ad6e44", "name": "prompt_looks_generated", "release": "v0.36.2", "subject": "feat(prompt-prediction): flag chop and job tribe origins as generated"}, {"commit": "12e012d", "name": "prompt_prediction_wire_schema_version", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "92a4fc4", "name": "prompt_proc_origin", "release": "v0.31.5", "subject": "feat(agent-launch): add native %proc dispatch helpers"}, {"commit": "df23cce", "name": "read_prompt_stash_archive", "release": "v0.36.1", "subject": "feat(prompt-stash): append-only archive for every permanent stash removal"}, {"commit": "28befcb", "name": "read_unread_completion_index", "release": "v0.36.2", "subject": "feat(notifications): store generations, ack API, and lean unread index"}, {"commit": "413511f", "name": "reconcile_notification_rows", "release": "v0.36.1", "subject": "feat(notifications): lock-held field-scoped reconcile write plus empty raw_suffix matcher parity"}, {"commit": "df23cce", "name": "recover_prompt_stash_archive", "release": "v0.36.1", "subject": "feat(prompt-stash): append-only archive for every permanent stash removal"}, {"commit": "2838c7e", "name": "resolve_input_type", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "c4444ab", "name": "resolve_macro_skill_definition", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "bc40675", "name": "rows_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "39324ac", "name": "sanitize_attachment_name", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "39324ac", "name": "scan_note_attachment_refs", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "3d406d4", "name": "select_publication_retries", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "9f6ce0c", "name": "status_bucket_for_status", "release": "v0.38.0", "subject": "feat(agent-archive): add live status-bucket match with outcome derived from bucket"}, {"commit": "bc40675", "name": "summarize_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "a95609e", "name": "summarize_agent_models", "release": "v0.38.0", "subject": "feat(core): expose session agent model summaries"}, {"commit": "9368ddf", "name": "tool_run_briefs", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "830e900", "name": "tool_run_detail", "release": "v0.36.0", "subject": "feat(tool-run): add tool_run_detail projection with stage timeline and witness counts"}, {"commit": "17b072b", "name": "tool_run_duration_calibration", "release": "v0.36.1", "subject": "feat(tool-run): add duration classes and inline-fit policy"}, {"commit": "17b072b", "name": "tool_run_duration_fit", "release": "v0.36.1", "subject": "feat(tool-run): add duration classes and inline-fit policy"}, {"commit": "cee9f49", "name": "tool_run_join", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "9368ddf", "name": "tool_run_live_glance", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "9368ddf", "name": "tool_run_node_summaries", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "7a9ffad", "name": "tool_run_record_demand", "release": "v0.36.2", "subject": "feat(tool-run): record per-run demand context, usage, and worker grants"}, {"commit": "cee9f49", "name": "tool_run_release_join", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "6e23783", "name": "tool_run_stats_report", "release": "v0.36.2", "subject": "feat(tool-run): implement core-stats report for sase-1dm.3"}, {"commit": "cee9f49", "name": "tool_run_sync_wait_budget", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "39324ac", "name": "unique_attachment_name", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "2838c7e", "name": "validate_enum_choices", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "47b28fb", "name": "validate_git_lock_retry_delays", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "4b4a052", "name": "wait_epic_follow_reduce", "release": "v0.37.1", "subject": "feat(wait): add pure wait_epic_follow reducer with Python binding (sase-1h7.4)"}], "declared_floor": "0.35.0", "exit_code": 4, "message": "sase-core-rs==0.35.0 is missing 146 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.38.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 5141 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 4274 commits behind HEAD) matched 2 changed file(s) and contributed 26 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
plugins: cov-7.1.0, mock-3.16.0, inline-snapshot-0.36.0, asyncio-1.4.0, hypothesis-6.168.5, platformdirs-4.12.4, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [8904 items]

........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  3%]
.................................................................F...... [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 18%]
..............................................F......................... [ 19%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 25%]
..........................................................F............. [ 25%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
.....
................................................................... [ 30%]
........................................................................ [ 31%]
.......................F................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
..............................................sase completion: built command-line spec in 0.59s
.......................... [ 40%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................s............................... [ 44%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 80%]
.......F................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 99%]
................................................                         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______________ test_ace_page_group_rejects_overlapping_checkouts _______________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

    async def test_ace_page_group_rejects_overlapping_checkouts() -> None:
        async with AcePageGroup() as group:
            checkout = group.checkout()
            await checkout.__aenter__()
            try:
                with pytest.raises(RuntimeError, match="overlapping checkouts"):
                    async with group.checkout():
                        pass
            finally:
>               await checkout.__aexit__(None, None, None)

tests/test_ace_testing.py:555: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:221: in __aexit__
    await anext(self.gen)
src/sase/ace/testing/ace_page_group.py:155: in checkout
    await self._reset_shared_page(shared_page)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <sase.ace.testing.ace_page_group.AcePageGroup object at 0x7fa8ebd14910>
page = <sase.ace.testing.ace_page.AcePage object at 0x7fa8eb3e0390>

    async def _reset_shared_page(self, page: AcePage) -> None:
        baseline = self._baseline
        if baseline is None:
            raise RuntimeError("AcePageGroup baseline is not available")
    
        app = page.app
        await _drain_app_work(app)
        await _close_extra_screens(page)
        _remove_prompt_surfaces(app)
        app._notifications.clear()
        _reset_navigation_modes(app)
        _restore_baseline_state(app, baseline)
        await app.recompose()
        _restore_focus(app, baseline)
        app._refresh_current_tab()
        await page.pause()
    
        if self._reset_hook is not None:
            result = self._reset_hook(page)
            if result is not None:
                await result
            await page.pause()
    
        after = _IsolationSnapshot.capture(
            page,
            track_notifications=self._notifications,
        )
        leaks = after.diff(baseline)
        if leaks:
            lines = [
                f"{name}: expected {expected!r}, got {actual!r}"
                for name, (actual, expected) in sorted(leaks.items())
            ]
>           raise AssertionError(
                "AcePageGroup isolation leak(s):\n"
                + "\n".join(f"- {line}" for line in lines)
            )
E           AssertionError: AcePageGroup isolation leak(s):
E           - focus: expected ('CommitsTimeline', 'stitches-timeline'), got None

src/sase/ace/testing/ace_page_group.py:203: AssertionError

During handling of the above exception, another exception occurred:

    async def test_ace_page_group_rejects_overlapping_checkouts() -> None:
>       async with AcePageGroup() as group:
                   ^^^^^^^^^^^^^^

tests/test_ace_testing.py:547: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page_group.py:133: in __aexit__
    await page.__aexit__(exc_type, exc_val, exc_tb)
src/sase/ace/testing/ace_page.py:357: in __aexit__
    await stack.__aexit__(exc_type, exc_val, exc_tb)
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:768: in __aexit__
    raise exc
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:751: in __aexit__
    cb_suppress = await cb(*exc_details)
                  ^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:235: in __aexit__
    await self.gen.athrow(value)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:693: in _flush_next_callbacks
    await invoke(callback.callback)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:58: in _invoke
    result = await result
             ^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/screen.py:1265: in _invoke_and_clear_callbacks
    await invoke(callback)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/actions/link_subject.py:167: in _refresh_link_rail_now
    rail.refresh_from_app(self)
src/sase/ace/tui/widgets/link_rail.py:78: in refresh_from_app
    subject_for_selection()
src/sase/ace/tui/actions/link_subject.py:42: in link_subject_for_selection
    subject = selected_link_subject(self)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/relations/link_subject.py:177: in selected_link_subject
    return adapter(app)
           ^^^^^^^^^^^^
src/sase/ace/tui/relations/link_subject.py:119: in _subject_from_artifacts
    return _subject_from_target(pane.selected_entry_target())
                                ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/artifacts/commits_detail.py:102: in selected_entry_target
    timeline = self.query_one("#stitches-timeline", CommitsTimeline)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = CommitsPane(id='artifacts-stitches-pane')
selector = '#stitches-timeline'
expect_type = <class 'sase.ace.tui.widgets.artifacts.commits_timeline.CommitsTimeline'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#stitches-timeline' on CommitsPane(id='artifacts-stitches-pane')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/ │
│ tui/actions/link_subject.py:167 in _refresh_link_rail_now                    │
│                                                                              │
│   164 │   │   │   rail.clear()                                               │
│   165 │   │   │   self._schedule_link_index_refresh(source="rail")           │
│   166 │   │   │   return                                                     │
│ ❱ 167 │   │   rail.refresh_from_app(self)                                    │
│   168 │                                                                      │
│   169 │   def _schedule_link_index_refresh(self, *, source: str) -> None:    │
│   170 │   │   """Build or refresh the app-owned link index outside the messa │
│                                                                              │
│ ╭────────────────── locals ───────────────────╮                              │
│ │ rail = LinkRail(id='link-rail')             │                              │
│ │ self = AceApp(                              │                              │
│ │        │   title='sase tui (v0.17.1)',      │                              │
│ │        │   classes={'-dark-mode'},          │                              │
│ │        │   pseudo_classes={                 │                              │
│ │        │   │   'focus',                     │                              │
│ │        │   │   'dark'                       │                              │
│ │        │   }                                │                              │
│ │        )                                    │                              │
│ ╰─────────────────────────────────────────────╯                              │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/ │
│ tui/widgets/link_rail.py:78 in refresh_from_app                              │
│                                                                              │
│    75 │   │   breadcrumb = link_trail_breadcrumb_text(host)                  │
│    76 │   │   subject_for_selection = getattr(host, "link_subject_for_select │
│    77 │   │   subject = (                                                    │
│ ❱  78 │   │   │   subject_for_selection()                                    │
│    79 │   │   │   if callable(subject_for_selection)                         │
│    80 │   │   │   else selected_link_subject(host)                           │
│    81 │   │   )                                                              │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │                   app = AceApp(                                          │ │
│ │                         │   title='sase tui (v0.17.1)',                  │ │
│ │                         │   classes={'-dark-mode'},                      │ │
│ │                         │   pseudo_classes={'focus', 'dark'}             │ │
│ │                         )                                                │ │
│ │            breadcrumb = None                                             │ │
│ │                  host = AceApp(                                          │ │
│ │                         │   title='sase tui (v0.17.1)',                  │ │
│ │                         │   classes={'-dark-mode'},                      │ │
│ │                         │   pseudo_classes={'focus', 'dark'}             │ │
│ │                         )                                                │ │
│ │                  self = LinkRail(id='link-rail')                         │ │
│ │ subject_for_selection = <bound method                                    │ │
│ │                         LinkSubjectMixin.link_subject_for_selection of   │ │
│ │                         AceApp(title='sase tui (v0.17.1)',               │ │
│ │                         classes={'-dark-mode'}, pseudo_classes={'focus', │ │
│ │                         'dark'})>                                        │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/ │
│ tui/actions/link_subject.py:42 in link_subject_for_selection                 │
│                                                                              │
│    39 │   │   cached = getattr(self, "_link_subject_cache", None)            │
│    40 │   │   if cached is not None and cached[0] == cache_key:              │
│    41 │   │   │   return cached[1]                                           │
│ ❱  42 │   │   subject = selected_link_subject(self)                          │
│    43 │   │   self._link_subject_cache = (cache_key, subject)                │
│    44 │   │   return subject                                                 │
│    45                                                                        │
│                                                                              │
│ ╭───────────────────── locals ─────────────────────╮                         │
│ │ cache_key = ('artifacts', 2, 'stitches', None)   │                         │
│ │    cached = None                                 │                         │
│ │      self = AceApp(                              │                         │
│ │             │   title='sase tui (v0.17.1)',      │                         │
│ │             │   classes={'-dark-mode'},          │                         │
│ │             │   pseudo_classes={                 │                         │
│ │             │   │   'focus',                     │                         │
│ │             │   │   'dark'                       │                         │
│ │             │   }                                │                         │
│ │             )                                    │                         │
│ ╰──────────────────────────────────────────────────╯                         │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/ │
│ tui/relations/link_subject.py:177 in selected_link_subject                   │
│                                                                              │
│   174 │   adapter = _ADAPTERS.get(str(getattr(app, "current_tab", "")))      │
│   175 │   if adapter is None:                                                │
│   176 │   │   return None                                                    │
│ ❱ 177 │   return adapter(app)                                                │
│   178                                                                        │
│   179                                                                        │
│   180 __all__ = [                                                            │
│                                                                              │
│ ╭────────────────── locals ──────────────────╮                               │
│ │ app = AceApp(                              │                               │
│ │       │   title='sase tui (v0.17.1)',      │                               │
│ │       │   classes={'-dark-mode'},          │                               │
│ │       │   pseudo_classes={                 │                               │
│ │       │   │   'focus',                     │                               │
│ │       │   │   'dark'                       │                               │
│ │       │   }                                │                               │
│ │       )                                    │                               │
│ ╰────────────────────────────────────────────╯                               │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/ │
│ tui/relations/link_subject.py:119 in _subject_from_artifacts                 │
│                                                                              │
│   116 │   pane = app._artifacts_entry_navigator()                            │
│   117 │   if pane is None:                                                   │
│   118 │   │   return None                                                    │
│ ❱ 119 │   return _subject_from_target(pane.selected_entry_target())          │
│   120                                                                        │
│   121                                                                        │
│   122 def _subject_from_agents(app: Any) -> LinkSubject | None:              │
│                                                                              │
│ ╭───────────────────── locals ─────────────────────╮                         │
│ │  app = AceApp(                                   │                         │
│ │        │   title='sase tui (v0.17.1)',           │                         │
│ │        │   classes={'-dark-mode'},               │                         │
│ │        │   pseudo_classes={'focus', 'dark'}      │                         │
│ │        )                                         │                         │
│ │ pane = CommitsPane(id='artifacts-stitches-pane') │                         │
│ ╰──────────────────────────────────────────────────╯                         │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/ │
│ tui/widgets/artifacts/commits_detail.py:102 in selected_entry_target         │
│                                                                              │
│    99 │   │   return timeline.entry_targets                                  │
│   100 │                                                                      │
│   101 │   def selected_entry_target(self) -> ArtifactEntryTarget | None:     │
│ ❱ 102 │   │   timeline = self.query_one("#stitches-timeline", CommitsTimelin │
│   103 │   │   return timeline.selected_entry_target                          │
│   104 │                                                                      │
│   105 │   def select_entry_target(self, target: ArtifactEntryTarget) -> bool │
│                                                                              │
│ ╭───────────────────── locals ─────────────────────╮                         │
│ │ self = CommitsPane(id='artifacts-stitches-pane') │                         │
│ ╰──────────────────────────────────────────────────╯                         │
╰──────────────────────────────────────────────────────────────────────────────╯
NoMatches: No nodes match '#stitches-timeline' on 
CommitsPane(id='artifacts-stitches-pane')

NOTE: 1 of 2 errors shown. Run with textual run --dev to see all errors.
------------------------------ Captured log call -------------------------------
ERROR    sase.ace.tui.app:app.py:385 Unhandled exception in sase's TUI
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 693, in _flush_next_callbacks
    await invoke(callback.callback)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_callback.py", line 58, in _invoke
    result = await result
             ^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/screen.py", line 1265, in _invoke_and_clear_callbacks
    await invoke(callback)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/link_subject.py", line 167, in _refresh_link_rail_now
    rail.refresh_from_app(self)
    ~~~~~~~~~~~~~~~~~~~~~^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/link_rail.py", line 78, in refresh_from_app
    subject_for_selection()
    ~~~~~~~~~~~~~~~~~~~~~^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/link_subject.py", line 42, in link_subject_for_selection
    subject = selected_link_subject(self)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/relations/link_subject.py", line 177, in selected_link_subject
    return adapter(app)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/relations/link_subject.py", line 119, in _subject_from_artifacts
    return _subject_from_target(pane.selected_entry_target())
                                ~~~~~~~~~~~~~~~~~~~~~~~~~~^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/artifacts/commits_detail.py", line 102, in selected_entry_target
    timeline = self.query_one("#stitches-timeline", CommitsTimeline)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/dom.py", line 1503, in query_one
    raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
textual.css.query.NoMatches: No nodes match '#stitches-timeline' on CommitsPane(id='artifacts-stitches-pane')
ERROR    sase.ace.tui.app:app.py:385 Unhandled exception in sase's TUI
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/app.py", line 2137, in run_test
    yield pilot
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_ace_testing.py", line 555, in test_ace_page_group_rejects_overlapping_checkouts
    await checkout.__aexit__(None, None, None)
  File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 221, in __aexit__
    await anext(self.gen)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/testing/ace_page_group.py", line 155, in checkout
    await self._reset_shared_page(shared_page)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/testing/ace_page_group.py", line 203, in _reset_shared_page
    raise AssertionError(
    ...<2 lines>...
    )
AssertionError: AcePageGroup isolation leak(s):
- focus: expected ('CommitsTimeline', 'stitches-timeline'), got None

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 693, in _flush_next_callbacks
    await invoke(callback.callback)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_callback.py", line 58, in _invoke
    result = await result
             ^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/reactive.py", line 85, in await_watcher
    await awaitable
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/widgets/_header.py", line 221, in set_title
    self.query_one(HeaderTitle).update(self.format_title())
    ~~~~~~~~~~~~~~^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/dom.py", line 1531, in query_one
    raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
textual.css.query.NoMatches: No nodes match 'HeaderTitle' on UsageHeader(id='ace-header')
__________________ test_cycle_focused_deck_wraps_and_reloads ___________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-13/popen-gw2/test_cycle_focused_deck_wraps_0')

    async def test_cycle_focused_deck_wraps_and_reloads(tmp_path: Path) -> None:
        app = _DetailApp()
        pin_paged(app)
        async with app.run_test(size=(100, 30)) as pilot:
            await pilot.pause()
            detail = app.query_one("#agent-detail-panel", AgentDetail)
            agent = make_artifact_agent(tmp_path, status="DONE")
            detail.update_display(agent)
            await pilot.pause()
            panel = detail.deck_area.panel(0)
            assert panel.deck is DeckId.MAIN
            detail.cycle_focused_deck(1)
            await pilot.pause()
            assert panel.deck is DeckId.FILES
            detail.cycle_focused_deck(1)
            await pilot.pause()
            assert panel.deck is DeckId.TOOLS
            detail.cycle_focused_deck(1)
            await pilot.pause()
            assert panel.deck is DeckId.FINAL
            detail.cycle_focused_deck(1)
            await pilot.pause()
>           assert panel.deck is DeckId.MAIN
E           AssertionError: assert <DeckId.RECORD: 'record'> is <DeckId.MAIN: 'main'>
E            +  where <DeckId.RECORD: 'record'> = DeckPanel(id='agent-deck-panel-0', classes='-deck-record deck-panel -focused').deck
E            +  and   <DeckId.MAIN: 'main'> = DeckId.MAIN

tests/ace/tui/widgets/decks/test_deck_panels.py:277: AssertionError
_______ test_agents_help_deck_other_panel_row_follows_pick_deck_binding ________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

    def test_agents_help_deck_other_panel_row_follows_pick_deck_binding() -> None:
        rebound = dict(
            dict(
                agents_bindings(
                    load_keymap_registry({"keymaps": {"app": {"pick_deck": "f12"}}})
                )
            )["Navigation"]
        )
>       assert rebound["f12 M/F/T/N"] == "Show deck in other panel (decks)"
               ^^^^^^^^^^^^^^^^^^^^^^
E       KeyError: 'f12 M/F/T/N'

tests/test_keymaps_display_help_agents.py:221: KeyError
_____ test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data ______
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-13/popen-gw2/test_workflow_snapshot_render_0')

    def test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data(
        tmp_path: Path,
    ) -> None:
        state = {
            "inputs": {"task": "fix"},
            "steps": [
                {
                    "name": "plan",
                    "status": "completed",
                    "output": {
                        "meta_project": "sase",
                        "meta_workspace": 7,
                        "meta_result": "ok",
                    },
                }
            ],
            "step_prompts": [{"name": "plan", "agent": "fallback prompt"}],
        }
        state_path = tmp_path / "workflow_state.json"
        state_path.write_text(json.dumps(state), encoding="utf-8")
        agent = _make_agent(artifacts_dir=str(tmp_path), cl_name="old_cl")
        panel = _Panel()
    
        from sase.ace.tui.widgets.prompt_panel import _workflow_display
    
        real_load_json_cached = _workflow_display.load_json_cached
        with patch.object(
            _workflow_display, "load_json_cached", wraps=real_load_json_cached
        ) as mock_load:
            panel._update_workflow_display(agent)
    
        state_reads = [
            call for call in mock_load.call_args_list if call.args[0] == state_path
        ]
        assert len(state_reads) == 1
    
        plain = _plain(panel.captured[-1])
>       assert "Project: sase" in plain
E       assert 'Project: sase' in 'WORKFLOW DETAILS\nWorkflow: demo_workflow\nProject: tmp\nWorkspace: #7\nStatus: DONE\nTimestamps: START | 2026-05-14 ...ta_result": "ok"\n      }\n\n\n\n──────────────────────────────────────────────────\n\nAGENT PROMPT\n\nfallback prompt'

tests/ace/tui/widgets/test_agent_display_workflow_async.py:151: AssertionError
________________________ test_prewarm_waits_for_idle_ui ________________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

    @pytest.mark.asyncio
    async def test_prewarm_waits_for_idle_ui() -> None:
        owner = _owner()
        spawn, compile_calls, _facets = _instrument(owner)
        owner._nav_gate.record()
    
        with override_flags(agents_archive_view=True):
            note_inbox_applied_for_archive(owner, load_state=_complete_load())
>           assert spawn.coros == []
E           assert [<coroutine o...7f5ed6867a40>] == []
E             
E             Left contains one more item: <coroutine object _run_archive_request at 0x7f5ed6867a40>
E             Use -v to get more diff

tests/ace/tui/test_agent_archive_controller.py:311: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

tests/test_ace_testing.py::test_ace_page_group_rejects_overlapping_checkouts
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/stash.py:108: RuntimeWarning: coroutine 'Header._on_mount.<locals>.set_title' was never awaited
    del self._storage[key]
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:233: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    args = (deepcopy(arg, memo) for arg in args)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/command_line/test_panel_shell_submit.py:162: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object CommandLineScreenSubmissionMixin._record_local_history.<locals>._record at 0x7f5ed0543400>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:110: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def deepcopy(x, memo=None, _nil=[]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object CommandLineScreen._load_tail_worker at 0x7f5ed0d55e00>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/completion/compat.py:48: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    return frozenset(getattr(action, _OPTION_STRINGS_ATTR, ()))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller.py::test_inbox_load_scheduled_resets_on_apply_and_failure
  <string>:3: RuntimeWarning: coroutine '_run_archive_request' was never awaited
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_hidden_inbox_refresh_preserves_archive_hydration
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/app.py:1423: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    @property
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
27.95s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
20.55s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
19.77s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
16.29s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
15.80s teardown tests/ace/tui/widgets/test_prompt_tab_focus_steal.py::test_tab_with_focus_on_list_still_stays_on_agents
14.49s call     tests/test_agent_group_revival_e2e.py::test_saved_group_revive_restores_deleted_artifacts_and_tribe_real_loader
13.36s call     tests/test_keymaps_e2e.py::test_default_query_shortcuts_follow_the_context_matrix
12.78s call     tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
12.05s call     tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
11.86s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
11.65s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
11.01s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
10.28s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
9.96s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
9.00s call     tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
8.97s call     tests/ace/tui/test_agents_deck_picker.py::test_agents_ctrl_n_updates_return_partner
8.88s call     tests/test_keymaps_e2e.py::test_bare_question_mark_opens_help_and_leader_chord_is_retired
8.77s call     tests/ace/tui/test_agent_grouping_picker.py::test_agents_default_oo_toggles_panel_layout_once_and_preserves_mode
8.71s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
8.70s call     tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
=========================== short test summary info ============================
FAILED tests/test_ace_testing.py::test_ace_page_group_rejects_overlapping_checkouts
FAILED tests/ace/tui/widgets/decks/test_deck_panels.py::test_cycle_focused_deck_wraps_and_reloads
FAILED tests/test_keymaps_display_help_agents.py::test_agents_help_deck_other_panel_row_follows_pick_deck_binding
FAILED tests/ace/tui/widgets/test_agent_display_workflow_async.py::test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data
FAILED tests/ace/tui/test_agent_archive_controller.py::test_prewarm_waits_for_idle_ui
===== 5 failed, 8898 passed, 1 skipped, 21 warnings in 1423.21s (0:23:43) ======
error: recipe `test-scoped` failed on line 569 with exit code 1
error: recipe `check` failed on line 819 with exit code 1
failed/1  1800783ms
triage lint (symvision): 1 KNOWN
triage test (scoped): 5 NEW
NEW test (scoped): FAILED tests/ace/tui/test_agent_archive_controller.py::test_prewarm_waits_for_idle_ui — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/decks/test_deck_panels.py::test_cycle_focused_deck_wraps_and_reloads — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_ace_testing.py::test_ace_page_group_rejects_overlapping_checkouts — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_keymaps_display_help_agents.py::test_agents_help_deck_other_panel_row_follows_pick_deck_binding — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_agent_display_workflow_async.py::test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data — recorded evidence; no owner
KNOWN lint (symvision): Error: --epic-symbol 'sase-1jx.8(evaluate_repo_creation_form)': bead 'sase-1jx.8' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — witness 71f62a3388253f8b09d8e9375eea8ef1; no owner
sase tool show 344a6ffab71903b926876208839e2ed8 -l
verdict: new_failures — 5 NEW, 1 KNOWN; exit 1

