# Chat History - ace-run (sase-1jm.5--mon-0)

- **TIMESTAMP:** 2026-10-12 06:06:07 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1jm.5--mon-0

## Prompt

sase monitor start --command 'just check' --reason 'Verify before host completion'

## Response

sase tool run 655bd71126f7f21070beacf049d40f3e
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
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol 'sase-1jm.3.1(archive_read_only_context)' --epic-symbol 'sase-1jm(archive_corpus_is_warm)' --epic-symbol 'sase-1jx.8(evaluate_repo_creation_form)' --epic-symbol 'sase-1jx.10(parse_event_line)' --epic-symbol 'sase-1jx.7.1(journal_path)' --epic-symbol 'sase-1jx.7.1(journal_lock_path)' --epic-symbol 'sase-1jx.7.1(journal_lock)' --epic-symbol 'sase-1jx.11(NewProjectModal)' --epic-symbol 'sase-1jx.11(NewProjectSelection)' --epic-symbol 'sase-1jx.12(record_owner_selection)' --epic-symbol 'sase-1jx.12(record_visibility_selection)' 
Error: --epic-symbol 'sase-1jm.3.1(archive_read_only_context)': bead 'sase-1jm.3.1' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1jx.7.1(journal_path)': bead 'sase-1jx.7.1' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1jx.7.1(journal_lock_path)': bead 'sase-1jx.7.1' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1jx.7.1(journal_lock)': bead 'sase-1jx.7.1' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
error: recipe `_lint-symvision` failed on line 456 with exit code 1
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
test selection escalated to the full suite (rules: justfile, src-data-asset); 5136 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: justfile, src-data-asset)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, mock-3.16.0, inline-snapshot-0.36.0, asyncio-1.4.0, hypothesis-6.168.5, platformdirs-4.12.4, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [55076 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
............................s........................................... [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................F............................... [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................s............................................... [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
..................................................................s..... [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
............F........................................................... [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
......................s................................................. [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
.........................................................s.............. [ 60%]
........................................................................ [ 60%]
...................s..s................................................. [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
s....................................................................... [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
......................................................F................. [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
.....................s.................................................. [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
............................................ssss........................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
.....................................................s.................. [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
..................................s..................................... [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........s............................................................... [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
.....................................F.................................. [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
...................................................s.................... [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
.....................F.................................................. [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
....................................................................     [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________ TestMetaPatchPriority.test_project_shown_when_no_patch ____________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

self = <tests.test_agent_display_meta_priority.TestMetaPatchPriority object at 0x7fcaad2e4690>

    def test_project_shown_when_no_patch(self) -> None:
        agent = _make_agent(
            step_output={"meta_project": "my_project"},
        )
        header, _ = build_header_text(agent)
        text = header.plain
    
>       assert "Project: my_project" in text
E       AssertionError: assert 'Project: my_project' in 'AGENT TURN\nName: unassigned\nProject: fake\nTimestamps: START | 2026-01-01 12:00:00\n\n──────────────────────────────────────────────────\n\n'

tests/test_agent_display_meta_priority.py:44: AssertionError
______________ test_every_value_slot_is_kinded_choiced_or_hinted _______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

    def test_every_value_slot_is_kinded_choiced_or_hinted() -> None:
        missing = _uncovered_slots()
>       assert not missing, (
            "uncaptioned completion value slots: "
            + ", ".join(f"{'/'.join(path) or 'sase'}:{dest}" for path, dest in missing)
            + ". Fix each slot one of three ways: (1) a ValueKind in "
            "src/sase/completion/kinds.py NAME_TABLE/PATH_OVERRIDES (or "
            "set_completion_kind at the parser), (2) argparse choices= on the "
            "action, or (3) a free-form value_hint in the kinds.py hint table."
        )
E       AssertionError: uncaptioned completion value slots: project/suggest:owner. Fix each slot one of three ways: (1) a ValueKind in src/sase/completion/kinds.py NAME_TABLE/PATH_OVERRIDES (or set_completion_kind at the parser), (2) argparse choices= on the action, or (3) a free-form value_hint in the kinds.py hint table.
E       assert not [(('project', 'suggest'), 'owner')]

tests/completion/test_kind_coverage.py:56: AssertionError
________________ test_tui_app_import_stays_under_startup_budget ________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

    def test_tui_app_import_stays_under_startup_budget() -> None:
        """Importing the app should not pull known heavy deferred profile edges."""
    
        last_elapsed = 0.0
        last_count = 0
        for _ in range(2):
>           payload = _measure_tui_app_import()
                      ^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_app_import_budget.py:89: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    def _measure_tui_app_import() -> dict[str, Any]:
        result = subprocess.run(
            [
                sys.executable,
                "-c",
                textwrap.dedent(
                    """
                    import importlib
                    import json
                    import sys
                    import time
    
                    started = time.process_time()
                    importlib.import_module("sase.ace.tui.app")
                    elapsed = time.process_time() - started
    
                    print(json.dumps({
                        "elapsed_seconds": elapsed,
                        "module_count": len(sys.modules),
                        "deferred_modules": [
                            name for name in (
                                "sase.agent.multi_prompt",
                                "sase.agent.multi_prompt_launcher",
                                "sase.agent.scope_sweep",
                                "sase.artifact_cli.create",
                                "sase.artifact_links.projection._agent_created_epic",
                                "sase.core.wait_dependency_resolution",
                                "sase.core.wait_epic_follow_view",
                                "sase.finalizers.commit_memory_guard",
                                "sase.service.status",
                                "sase.service.control",
                                "sase.dev_update",
                                "sase.dev_update.execute",
                                "sase.update_progress",
                            )
                            if name in sys.modules
                        ],
                    }))
                    """
                ),
            ],
            check=False,
            text=True,
            capture_output=True,
        )
        assert result.returncode == 0, result.stderr + result.stdout
        payload = json.loads(result.stdout)
        assert payload["deferred_modules"] == [], (
            f"TUI startup eagerly imports deferred modules: {payload['deferred_modules']!r}"
        )
>       assert payload["module_count"] < _MAX_MODULE_COUNT, (
            f"TUI app import loads {payload['module_count']} modules "
            f"against the {_MAX_MODULE_COUNT} cap; attribute the growth with "
            f"`tools/tui_import_closure --diff "
            f"$(git merge-base HEAD origin/master)` and defer the new edges"
        )
E       AssertionError: TUI app import loads 3518 modules against the 3513 cap; attribute the growth with `tools/tui_import_closure --diff $(git merge-base HEAD origin/master)` and defer the new edges
E       assert 3518 < 3513

tests/ace/tui/test_app_import_budget.py:74: AssertionError
_____ test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data ______
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-12/popen-gw3/test_workflow_snapshot_render_0')

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
____________________ test_each_activation_mints_new_session ____________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f047acc8a60>
tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-12/popen-gw1/test_each_activation_mints_new0')

    @pytest.mark.asyncio
    async def test_each_activation_mints_new_session(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        """Every reveal gets a new ``_prompt_session.session_id`` and instance."""
        _stub_backends(monkeypatch, tmp_path)
        app = AceApp(query="!!!", auto_start_axe=False, refresh_interval=0)
>       async with app.run_test() as pilot:
                   ^^^^^^^^^^^^^^

tests/ace/tui/test_prompt_bar_hot_spare.py:265: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:221: in __aexit__
    await anext(self.gen)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/timer.py:189: in _tick
    await invoke(self._callback)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/screen.py:1248: in _on_timer_update
    self._compositor_refresh()
.venv/lib/python3.14/site-packages/textual/screen.py:1214: in _compositor_refresh
    update = self._compositor.render_update(
.venv/lib/python3.14/site-packages/textual/_compositor.py:1113: in render_update
    return self.render_full_update(simplify=simplify)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_compositor.py:1149: in render_full_update
    chops = self._render_chops(crop, lambda y: True)
            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_compositor.py:1222: in _render_chops
    for region, clip, strips in renders:
                                ^^^^^^^
.venv/lib/python3.14/site-packages/textual/_compositor.py:1068: in _get_renders
    widget.render_lines(
.venv/lib/python3.14/site-packages/textual/widgets/_text_area.py:1200: in render_lines
    theme.apply_css(self)
.venv/lib/python3.14/site-packages/textual/_text_area_theme.py:107: in apply_css
    gutter_style = get_style("text-area--gutter")
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/widget.py:1166: in get_component_rich_style
    component_styles = self.get_component_styles(*names)
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = PromptTextArea(id='prompt-input-g0-p0', classes='prompt-input solo -vim-insert active')
names = ('text-area--gutter',)

    def get_component_styles(self, *names: str) -> RenderStyles:
        """Get a "component" styles object (must be defined in COMPONENT_CLASSES classvar).
    
        Args:
            names: Names of the components.
    
        Raises:
            KeyError: If the component class doesn't exist.
    
        Returns:
            A Styles object.
        """
    
        styles = RenderStyles(self, Styles(), Styles())
    
        for name in names:
            if name not in self._component_styles:
>               raise KeyError(f"No {name!r} key in COMPONENT_CLASSES")
E               KeyError: "No 'text-area--gutter' key in COMPONENT_CLASSES"

.venv/lib/python3.14/site-packages/textual/dom.py:616: KeyError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/pyt │
│ hon3.14/site-packages/textual/widgets/_text_area.py:1200 in render_lines     │
│                                                                              │
│   1197 │   def render_lines(self, crop: Region) -> list[Strip]:              │
│   1198 │   │   theme = self._theme                                           │
│   1199 │   │   if theme:                                                     │
│ ❱ 1200 │   │   │   theme.apply_css(self)                                     │
│   1201 │   │   return super().render_lines(crop)                             │
│   1202 │                                                                     │
│   1203 │   def render_line(self, y: int) -> Strip:                           │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │  crop = Region(x=0, y=0, width=76, height=1)                             │ │
│ │  self = PromptTextArea(                                                  │ │
│ │         │   id='prompt-input-g0-p0',                                     │ │
│ │         │   classes='prompt-input solo -vim-insert active'               │ │
│ │         )                                                                │ │
│ │ theme = TextAreaTheme(                                                   │ │
│ │         │   name='sase-jinja-prompt',                                    │ │
│ │         │   base_style=Style(                                            │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#dfdfdf',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=223,                                         │ │
│ │         │   │   │   │   green=223,                                       │ │
│ │         │   │   │   │   blue=223                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#100f0f',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=16, green=15, blue=15)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   gutter_style=Style(                                          │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#6f6d69',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=111,                                         │ │
│ │         │   │   │   │   green=109,                                       │ │
│ │         │   │   │   │   blue=105                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#100f0f',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=16, green=15, blue=15)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   cursor_style=Style(                                          │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#100f0f',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=16, green=15, blue=15)      │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#3aa99f',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=58,                                          │ │
│ │         │   │   │   │   green=169,                                       │ │
│ │         │   │   │   │   blue=159                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bold=True                                                │ │
│ │         │   ),                                                           │ │
│ │         │   cursor_line_style=Style(                                     │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#e1e0e0',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=225,                                         │ │
│ │         │   │   │   │   green=224,                                       │ │
│ │         │   │   │   │   blue=224                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#191818',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=25, green=24, blue=24)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   cursor_line_gutter_style=Style(                              │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#a3a099',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=163,                                         │ │
│ │         │   │   │   │   green=160,                                       │ │
│ │         │   │   │   │   blue=153                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#191818',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=25, green=24, blue=24)      │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bold=True                                                │ │
│ │         │   ),                                                           │ │
│ │         │   bracket_matching_style=Style(                                │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#e9e9e8',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=233,                                         │ │
│ │         │   │   │   │   green=233,                                       │ │
│ │         │   │   │   │   blue=232                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#575652',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=87, green=86, blue=82)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   selection_style=Style(                                       │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#e4e4e3',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=228,                                         │ │
│ │         │   │   │   │   green=228,                                       │ │
│ │         │   │   │   │   blue=227                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#31302e',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=49, green=48, blue=46)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   syntax_styles={                                              │ │
│ │         │   │   'string': Style(                                         │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#ce9178',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=206,                                     │ │
│ │         │   │   │   │   │   green=145,                                   │ │
│ │         │   │   │   │   │   blue=120                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'string.documentation': Style(                           │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#ce9178',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=206,                                     │ │
│ │         │   │   │   │   │   green=145,                                   │ │
│ │         │   │   │   │   │   blue=120                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'comment': Style(                                        │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#6a9955',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=106,                                     │ │
│ │         │   │   │   │   │   green=153,                                   │ │
│ │         │   │   │   │   │   blue=85                                      │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'heading.marker': Style(                                 │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#6e7681',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=110,                                     │ │
│ │         │   │   │   │   │   green=118,                                   │ │
│ │         │   │   │   │   │   blue=129                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'keyword': Style(                                        │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#c586c0',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=197,                                     │ │
│ │         │   │   │   │   │   green=134,                                   │ │
│ │         │   │   │   │   │   blue=192                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'operator': Style(                                       │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#cccccc',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=204,                                     │ │
│ │         │   │   │   │   │   green=204,                                   │ │
│ │         │   │   │   │   │   blue=204                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'conditional': Style(                                    │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#569cd6',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=86,                                      │ │
│ │         │   │   │   │   │   green=156,                                   │ │
│ │         │   │   │   │   │   blue=214                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'keyword.function': Style(                               │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#569cd6',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=86,                                      │ │
│ │         │   │   │   │   │   green=156,                                   │ │
│ │         │   │   │   │   │   blue=214                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'keyword.return': Style(                                 │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#569cd6',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=86,                                      │ │
│ │         │   │   │   │   │   green=156,                                   │ │
│ │         │   │   │   │   │   blue=214                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'keyword.operator': Style(                               │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#569cd6',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=86,                                      │ │
│ │         │   │   │   │   │   green=156,                                   │ │
│ │         │   │   │   │   │   blue=214                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   ... +151                                                 │ │
│ │         │   },                                                           │ │
│ │         │   _theme_configured_attributes={                               │ │
│ │         │   │   'name',                                                  │ │
│ │         │   │   '_theme_configured_attributes',                          │ │
│ │         │   │   'syntax_styles'                                          │ │
│ │         │   }                                                            │ │
│ │         )                                                                │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/pyt │
│ hon3.14/site-packages/textual/_text_area_theme.py:107 in apply_css           │
│                                                                              │
│   104 │   │   assert self.base_style.bgcolor is not None                     │
│   105 │   │                                                                  │
│   106 │   │   if not configured("gutter_style"):                             │
│ ❱ 107 │   │   │   gutter_style = get_style("text-area--gutter")              │
│   108 │   │   │   if gutter_style:                                           │
│   109 │   │   │   │   self.gutter_style = gutter_style                       │
│   110 │   │   │   else:                                                      │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │  app_theme = Theme(                                                      │ │
│ │              │   name='flexoki',                                         │ │
│ │              │   primary='#205EA6',                                      │ │
│ │              │   secondary='#24837B',                                    │ │
│ │              │   warning='#AD8301',                                      │ │
│ │              │   error='#AF3029',                                        │ │
│ │              │   success='#66800B',                                      │ │
│ │              │   accent='#9B76C8',                                       │ │
│ │              │   foreground='#FFFCF0',                                   │ │
│ │              │   background='#100F0F',                                   │ │
│ │              │   surface='#1C1B1A',                                      │ │
│ │              │   panel='#282726',                                        │ │
│ │              │   boost=None,                                             │ │
│ │              │   dark=True,                                              │ │
│ │              │   luminosity_spread=0.15,                                 │ │
│ │              │   text_alpha=0.95,                                        │ │
│ │              │   variables={                                             │ │
│ │              │   │   'input-cursor-foreground': '#5E409D',               │ │
│ │              │   │   'input-cursor-background': '#FFFCF0',               │ │
│ │              │   │   'input-selection-background': '#6F6E69 35%',        │ │
│ │              │   │   'button-color-foreground': '#FFFCF0'                │ │
│ │              │   }                                                       │ │
│ │              )                                                           │ │
│ │ configured = <built-in method __contains__ of set object at              │ │
│ │              0x7f0462626c00>                                             │ │
│ │  get_style = <bound method Widget.get_component_rich_style of            │ │
│ │              PromptTextArea(id='prompt-input-g0-p0',                     │ │
│ │              classes='prompt-input solo -vim-insert active')>            │ │
│ │       self = TextAreaTheme(                                              │ │
│ │              │   name='sase-jinja-prompt',                               │ │
│ │              │   base_style=Style(                                       │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#dfdfdf',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=223,                                    │ │
│ │              │   │   │   │   green=223,                                  │ │
│ │              │   │   │   │   blue=223                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#100f0f',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=16,                                     │ │
│ │              │   │   │   │   green=15,                                   │ │
│ │              │   │   │   │   blue=15                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   gutter_style=Style(                                     │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#6f6d69',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=111,                                    │ │
│ │              │   │   │   │   green=109,                                  │ │
│ │              │   │   │   │   blue=105                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#100f0f',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=16,                                     │ │
│ │              │   │   │   │   green=15,                                   │ │
│ │              │   │   │   │   blue=15                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   cursor_style=Style(                                     │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#100f0f',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=16,                                     │ │
│ │              │   │   │   │   green=15,                                   │ │
│ │              │   │   │   │   blue=15                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#3aa99f',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=58,                                     │ │
│ │              │   │   │   │   green=169,                                  │ │
│ │              │   │   │   │   blue=159                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bold=True                                           │ │
│ │              │   ),                                                      │ │
│ │              │   cursor_line_style=Style(                                │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#e1e0e0',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=225,                                    │ │
│ │              │   │   │   │   green=224,                                  │ │
│ │              │   │   │   │   blue=224                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#191818',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=25,                                     │ │
│ │              │   │   │   │   green=24,                                   │ │
│ │              │   │   │   │   blue=24                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   cursor_line_gutter_style=Style(                         │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#a3a099',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=163,                                    │ │
│ │              │   │   │   │   green=160,                                  │ │
│ │              │   │   │   │   blue=153                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#191818',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=25,                                     │ │
│ │              │   │   │   │   green=24,                                   │ │
│ │              │   │   │   │   blue=24                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bold=True                                           │ │
│ │              │   ),                                                      │ │
│ │              │   bracket_matching_style=Style(                           │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#e9e9e8',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=233,                                    │ │
│ │              │   │   │   │   green=233,                                  │ │
│ │              │   │   │   │   blue=232                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#575652',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=87,                                     │ │
│ │              │   │   │   │   green=86,                                   │ │
│ │              │   │   │   │   blue=82                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   selection_style=Style(                                  │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#e4e4e3',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=228,                                    │ │
│ │              │   │   │   │   green=228,                                  │ │
│ │              │   │   │   │   blue=227                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#31302e',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=49,                                     │ │
│ │              │   │   │   │   green=48,                                   │ │
│ │              │   │   │   │   blue=46                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   syntax_styles={                                         │ │
│ │              │   │   'string': Style(                                    │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#ce9178',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=206,                                │ │
│ │              │   │   │   │   │   green=145,                              │ │
│ │              │   │   │   │   │   blue=120                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'string.documentation': Style(                      │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#ce9178',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=206,                                │ │
│ │              │   │   │   │   │   green=145,                              │ │
│ │              │   │   │   │   │   blue=120                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'comment': Style(                                   │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#6a9955',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=106,                                │ │
│ │              │   │   │   │   │   green=153,                              │ │
│ │              │   │   │   │   │   blue=85                                 │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'heading.marker': Style(                            │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#6e7681',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=110,                                │ │
│ │              │   │   │   │   │   green=118,                              │ │
│ │              │   │   │   │   │   blue=129                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'keyword': Style(                                   │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#c586c0',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=197,                                │ │
│ │              │   │   │   │   │   green=134,                              │ │
│ │              │   │   │   │   │   blue=192                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'operator': Style(                                  │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#cccccc',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=204,                                │ │
│ │              │   │   │   │   │   green=204,                              │ │
│ │              │   │   │   │   │   blue=204                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'conditional': Style(                               │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#569cd6',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=86,                                 │ │
│ │              │   │   │   │   │   green=156,                              │ │
│ │              │   │   │   │   │   blue=214                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'keyword.function': Style(                          │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#569cd6',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=86,                                 │ │
│ │              │   │   │   │   │   green=156,                              │ │
│ │              │   │   │   │   │   blue=214                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'keyword.return': Style(                            │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#569cd6',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=86,                                 │ │
│ │              │   │   │   │   │   green=156,                              │ │
│ │              │   │   │   │   │   blue=214                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'keyword.operator': Style(                          │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#569cd6',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=86,                                 │ │
│ │              │   │   │   │   │   green=156,                              │ │
│ │              │   │   │   │   │   blue=214                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   ... +151                                            │ │
│ │              │   },                                                      │ │
│ │              │   _theme_configured_attributes={                          │ │
│ │              │   │   'name',                                             │ │
│ │              │   │   '_theme_configured_attributes',                     │ │
│ │              │   │   'syntax_styles'                                     │ │
│ │              │   }                                                       │ │
│ │              )                                                           │ │
│ │  text_area = PromptTextArea(                                             │ │
│ │              │   id='prompt-input-g0-p0',                                │ │
│ │              │   classes='prompt-input solo -vim-insert active'          │ │
│ │              )                                                           │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/pyt │
│ hon3.14/site-packages/textual/widget.py:1166 in get_component_rich_style     │
│                                                                              │
│   1163 │   │                                                                 │
│   1164 │   │   if names not in self._rich_style_cache:                       │
│   1165 │   │   │   if default is None:                                       │
│ ❱ 1166 │   │   │   │   component_styles = self.get_component_styles(*names)  │
│   1167 │   │   │   else:                                                     │
│   1168 │   │   │   │   try:                                                  │
│   1169 │   │   │   │   │   component_styles = self.get_component_styles(*nam │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ default = None                                               │             │
│ │   names = ('text-area--gutter',)                             │             │
│ │ partial = False                                              │             │
│ │    self = PromptTextArea(                                    │             │
│ │           │   id='prompt-input-g0-p0',                       │             │
│ │           │   classes='prompt-input solo -vim-insert active' │             │
│ │           )                                                  │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/pyt │
│ hon3.14/site-packages/textual/dom.py:616 in get_component_styles             │
│                                                                              │
│    613 │   │                                                                 │
│    614 │   │   for name in names:                                            │
│    615 │   │   │   if name not in self._component_styles:                    │
│ ❱  616 │   │   │   │   raise KeyError(f"No {name!r} key in COMPONENT_CLASSES │
│    617 │   │   │   component_styles = self._component_styles[name]           │
│    618 │   │   │   assert component_styles.node is not None                  │
│    619 │   │   │   styles._update_node(component_styles.node)                │
│                                                                              │
│ ╭──────────────────────────── locals ─────────────────────────────╮          │
│ │   name = 'text-area--gutter'                                    │          │
│ │  names = ('text-area--gutter',)                                 │          │
│ │   self = PromptTextArea(                                        │          │
│ │          │   id='prompt-input-g0-p0',                           │          │
│ │          │   classes='prompt-input solo -vim-insert active'     │          │
│ │          )                                                      │          │
│ │ styles = RenderStyles(                                          │          │
│ │          │   PromptTextArea(                                    │          │
│ │          │   │   id='prompt-input-g0-p0',                       │          │
│ │          │   │   classes='prompt-input solo -vim-insert active' │          │
│ │          │   )                                                  │          │
│ │          )                                                      │          │
│ ╰─────────────────────────────────────────────────────────────────╯          │
╰──────────────────────────────────────────────────────────────────────────────╯
KeyError: "No 'text-area--gutter' key in COMPONENT_CLASSES"
------------------------------ Captured log call -------------------------------
ERROR    sase.ace.tui.app:app.py:385 Unhandled exception in sase's TUI
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/timer.py", line 189, in _tick
    await invoke(self._callback)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/screen.py", line 1248, in _on_timer_update
    self._compositor_refresh()
    ~~~~~~~~~~~~~~~~~~~~~~~~^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/screen.py", line 1214, in _compositor_refresh
    update = self._compositor.render_update(
        screen_stack=app._background_screens
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1113, in render_update
    return self.render_full_update(simplify=simplify)
           ~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1149, in render_full_update
    chops = self._render_chops(crop, lambda y: True)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1222, in _render_chops
    for region, clip, strips in renders:
                                ^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1068, in _get_renders
    widget.render_lines(
    ~~~~~~~~~~~~~~~~~~~^
        _Region(
        ^^^^^^^^
    ...<4 lines>...
        )
        ^
    ),
    ^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/widgets/_text_area.py", line 1200, in render_lines
    theme.apply_css(self)
    ~~~~~~~~~~~~~~~^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/_text_area_theme.py", line 107, in apply_css
    gutter_style = get_style("text-area--gutter")
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/widget.py", line 1166, in get_component_rich_style
    component_styles = self.get_component_styles(*names)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/dom.py", line 616, in get_component_styles
    raise KeyError(f"No {name!r} key in COMPONENT_CLASSES")
KeyError: "No 'text-area--gutter' key in COMPONENT_CLASSES"
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:295 TUI message pump stall detected: 5.014s pid=3118886
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

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=3118923) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/macro/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/config/loading.py:60: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:234: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    y = func(*args)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/command_line/test_panel_shell_submit.py:162: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:234: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    y = func(*args)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/main/parser_gettext.py:54: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    tuple(os.environ.get(key) for key in _GETTEXT_ENV_KEYS)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=3118976) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/ace/tui/test_agent_archive_controller.py::test_lookup_reads_name_from_request_snapshot_not_live_state
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:1725: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return ((p, type(p)) for p in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=3118886) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
99.60s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
65.34s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
48.84s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
39.48s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
39.19s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
36.74s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
34.89s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
27.74s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
25.05s call     tests/test_ace_testing.py::test_ace_page_initial_state
22.75s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
22.67s call     tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly
20.31s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_each_activation_mints_new_session
20.14s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
19.98s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
19.48s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
18.65s call     tests/test_agent_group_revival_e2e.py::test_saved_group_revive_restores_deleted_artifacts_and_tribe_real_loader
17.33s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_cancel_is_non_mutating
16.60s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
15.43s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent
15.42s call     tests/test_sdd_commit.py::test_commit_sdd_files_removes_persistent_index_lock_after_retry_exhausted
=========================== short test summary info ============================
FAILED tests/test_agent_display_meta_priority.py::TestMetaPatchPriority::test_project_shown_when_no_patch
FAILED tests/completion/test_kind_coverage.py::test_every_value_slot_is_kinded_choiced_or_hinted
FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget
FAILED tests/ace/tui/widgets/test_agent_display_workflow_async.py::test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data
FAILED tests/ace/tui/test_prompt_bar_hot_spare.py::test_each_activation_mints_new_session
==== 5 failed, 55054 passed, 18 skipped, 110 warnings in 2775.73s (0:46:15) ====
error: recipe `test-scoped` failed on line 570 with exit code 1
scoped: escalated to the full suite (rules: justfile, src-data-asset); contexts baseline not consulted
✗ 2 stage(s) failed; continued past them (first exit 1)
error: recipe `check` failed on line 822 with exit code 1
failed  exit=1  duration=3191233ms
unattrib  1m 13s
triage lint (symvision): 4 KNOWN continued
triage test (scoped): 1 FLAKY 4 KNOWN continued
KNOWN lint (symvision): Error: --epic-symbol 'sase-1jm.3.1(archive_read_only_context)': bead 'sase-1jm.3.1' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — witness b31ff81db2e176e14ec0e810f4937cb6; no owner
KNOWN lint (symvision): Error: --epic-symbol 'sase-1jx.7.1(journal_lock_path)': bead 'sase-1jx.7.1' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — witness b31ff81db2e176e14ec0e810f4937cb6; no owner
KNOWN lint (symvision): Error: --epic-symbol 'sase-1jx.7.1(journal_lock)': bead 'sase-1jx.7.1' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — witness b31ff81db2e176e14ec0e810f4937cb6; no owner
FLAKY test (scoped): FAILED tests/ace/tui/widgets/test_agent_display_workflow_async.py::test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data — recorded evidence; no owner
verdict: no_new_failures — 8 KNOWN, 1 FLAKY; exit 1

