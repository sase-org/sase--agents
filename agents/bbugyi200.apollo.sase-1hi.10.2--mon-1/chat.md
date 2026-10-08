# Chat History - ace-run (sase-1hi.10.2--mon-1)

- **TIMESTAMP:** 2026-10-08 08:45:28 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1hi.10.2--mon-1

## Prompt

sase monitor start --command 'just check' --reason 'Verify before host completion'

## Response

sase tool run c6c8f235a102ab9b2efbc727683931f5
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.37.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
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
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.37.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  BeadBoardSnapshot in src/sase/core/bead_read_facade.py
  BeadStoreFingerprint in src/sase/core/bead_read_facade.py
  CacheKeyInputs in src/sase/instructions/cache.py
  CoreMemoryUnit in src/sase/amd/memory_units.py
  InstructionManifestError in src/sase/core/instruction_manifest.py
  InstructionManifestError in src/sase/instructions/manifest.py
  MemoryIntroTexts in src/sase/amd/memory_units.py
  ParityIssue in src/sase/instructions/parity.py
  ParityReport in src/sase/instructions/parity.py
  ReferenceMemoryUnit in src/sase/amd/memory_units.py
  RunManifest in src/sase/instructions/manifests.py
  WebMemoryUnit in src/sase/amd/memory_units.py
  advertised_config_type_names in src/sase/ace/tui/modals/macro_config_modal.py
  aggregate_rows in src/sase/instructions/verify.py
  bead_push_log_retention_config in src/sase/bead/_sync_logs.py
  cache_entry_path in src/sase/instructions/cache.py
  check_instructions_coverage in src/sase/doctor/checks_instructions.py
  check_instructions_delivery in src/sase/doctor/checks_instructions.py
  check_instructions_helpers in src/sase/doctor/checks_instructions.py
  classify_callout in src/sase/ace/tui/modals/plan_decision_document.py
  claude_projects_root in src/sase/instructions/_runs.py
  codex_sessions_root in src/sase/instructions/_runs.py
  collapsed_row_text in src/sase/ace/tui/modals/plan_decision_rows.py
  context_block_texts in src/sase/instructions/muse.py
  controller_failure_for_handoff in src/sase/finalizers/controller_run.py
  coverage_block_to_json_dict in src/sase/instructions/render.py
  default_provider in src/sase/instructions/facts.py
  detect_host in src/sase/instructions/facts.py
  expanded_row_text in src/sase/ace/tui/modals/plan_decision_rows.py
  finalizer_owned_monitor_refusal in src/sase/monitor/start_flow.py
  finalizer_reports_failure in src/sase/axe/run_agent_exec_finalize.py
  git_fetch_origin in src/sase/llm_provider/commit_finalizer_git_status.py
  git_is_ahead_of_upstream in src/sase/llm_provider/commit_finalizer_git_status.py
  git_remote_tracking_ref in src/sase/llm_provider/commit_finalizer_git_status.py
  grok_cwd_dir in src/sase/instructions/_runs.py
  grok_sessions_root in src/sase/instructions/_runs.py
  hidden_sidecar_clone_dirs in src/sase/sdd/_store_maintenance.py
  instruction_shadow_render_enabled in src/sase/llm_provider/_instruction_boundary.py
  is_unverified_row in src/sase/ace/tui/modals/plan_decision_rows.py
  macro_input_choice_to_wire in src/sase/macro/_input_hint_wire.py
  maybe_gc_hidden_sidecar_clone in src/sase/sdd/_store_maintenance.py
  observe_agy_session in src/sase/instructions/agy.py
  prune_cache_entries in src/sase/instructions/cache.py
  report_to_json_dict in src/sase/instructions/render.py
  route_bead_targets in src/sase/core/bead_target_routing_facade.py
  run_instructions_render in src/sase/main/instructions_handler.py
  run_instructions_verify in src/sase/main/instructions_handler.py
  section_diff_to_json_dict in src/sase/instructions/render.py
  staged_sdd_files in src/sase/sdd/_commit_store.py
  validate_config_input_type in src/sase/ace/tui/modals/macro_config_modal.py
  write_acceptance_meta in src/sase/notification_gates/decision.py
error: Recipe `_lint-symvision` failed on line 410 with exit code 1
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.35.0 is missing 107 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] PromptPredictionCorpus: first appears in sase-core 12e012d (feat(core-binding): add prompt_prediction binding module with tests); release v0.36.1 contains it.
[core-floor-probe] PromptPredictionModel: first appears in sase-core 12e012d (feat(core-binding): add prompt_prediction binding module with tests); release v0.36.1 contains it.
[core-floor-probe] ack_agent_completions: first appears in sase-core 28befcb (feat(notifications): store generations, ack API, and lean unread index); release v0.36.2 contains it.
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
[core-floor-probe] bead_probe_target_owner: first appears in sase-core bff4860 (feat(bead): one-replay core support for in-mutation resolution and target probing); no release tag contains it yet.
[core-floor-probe] build_agent_tab_catalog: first appears in sase-core c448ed6 (feat(agent-tab): core tab model with directive, typed units, and Python bindings); release v0.36.0 contains it.
[core-floor-probe] canonicalize_agent_tab_name: first appears in sase-core c448ed6 (feat(agent-tab): core tab model with directive, typed units, and Python bindings); release v0.36.0 contains it.
[core-floor-probe] check_input_value: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] classify_attachment: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] classify_deferred_prompt_obligation: first appears in sase-core 3d406d4 (feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status); release v0.36.5 contains it.
[core-floor-probe] classify_model_value: first appears in sase-core 16095fc (feat(macros): add builtin model and effort types with one routing classifier); release v0.36.6 contains it.
[core-floor-probe] classify_session_manifest_files: first appears in sase-core d7f2dbf (feat(agent-session-manifest): canonical file-set derivation and classification); release v0.36.5 contains it.
[core-floor-probe] compare_prose: first appears in sase-core 3b27df5 (feat(prose-diff): add pure sase-core prose_diff module and Python binding); release v0.36.2 contains it.
[core-floor-probe] compose_note_attachment_text: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] decide_publication_request_completion: first appears in sase-core 3d406d4 (feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status); release v0.36.5 contains it.
[core-floor-probe] editor_snippet_catalog_wire_schema_version: first appears in sase-core a62699b (feat(macros)!: emit canonical macro wires and snippet catalog schema 2); release v0.37.0 contains it.
[core-floor-probe] evaluate_prompt_prediction_replay: first appears in sase-core 1ad57ea (feat(prompt-prediction): add per-point novel coverage and precision to sweep wire); release v0.36.1 contains it.
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
[core-floor-probe] instruction_manifest_wire_schema_version: first appears in sase-core fa39036 (feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)); no release tag contains it yet.
[core-floor-probe] jinja_catalog: first appears in sase-core 3adc01b (feat(editor-completion): add jinja completion bindings and tests); release v0.36.2 contains it.
[core-floor-probe] jinja_completion: first appears in sase-core 3adc01b (feat(editor-completion): add jinja completion bindings and tests); release v0.36.2 contains it.
[core-floor-probe] jinja_scope_variables: first appears in sase-core 3adc01b (feat(editor-completion): add jinja completion bindings and tests); release v0.36.2 contains it.
[core-floor-probe] launch_scratch_liveness_wire_schema_version: first appears in sase-core 297bc1e (feat(core): launch_scratch_liveness module with procfs probe bindings); release v0.36.0 contains it.
[core-floor-probe] load_macro_input_type_registry: first appears in sase-core af5df61 (feat(core): load plugin input_type registries with resolution, catalog, and LSP wiring); release v0.37.0 contains it.
[core-floor-probe] macro_argument_choice_candidates: first appears in sase-core 0d27dad (feat(macros): carry resolved choice metadata and shared candidates); release v0.36.6 contains it.
[core-floor-probe] macro_argument_spans: first appears in sase-core c4444ab (feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output); release v0.36.3 contains it.
[core-floor-probe] macro_completion_spacer_to_parentheses_edit: first appears in sase-core 0279de6 (feat(macros): flip emitted wires to macro spellings, rename LSP crate); release v0.36.6 contains it.
[core-floor-probe] macro_input_type_catalog: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] macro_input_type_label: first appears in sase-core 0d27dad (feat(macros): carry resolved choice metadata and shared candidates); release v0.36.6 contains it.
[core-floor-probe] macro_skill_definition_wire_schema_version: first appears in sase-core c4444ab (feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output); release v0.36.3 contains it.
[core-floor-probe] managed_tmp_roots_list: first appears in sase-core 924884e (feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)); release v0.36.0 contains it.
[core-floor-probe] managed_tmp_roots_register: first appears in sase-core 924884e (feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)); release v0.36.0 contains it.
[core-floor-probe] managed_tmp_roots_wire_schema_version: first appears in sase-core 924884e (feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)); release v0.36.0 contains it.
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
[core-floor-probe] normalize_instruction_manifest: first appears in sase-core fa39036 (feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)); no release tag contains it yet.
[core-floor-probe] normalize_macro_config_layer: first appears in sase-core 4eb40d5 (feat(compat): shared Rust config normalization contract); release v0.36.4 contains it.
[core-floor-probe] observe_launch_scratch_liveness: first appears in sase-core 297bc1e (feat(core): launch_scratch_liveness module with procfs probe bindings); release v0.36.0 contains it.
[core-floor-probe] plan_decision_quote_match: first appears in sase-core df735e4 (feat(sase-core): add plan decision human quote matcher with PyO3 binding); no release tag contains it yet.
[core-floor-probe] plan_decision_sheet: first appears in sase-core 88d6385 (feat(plan): add decision sheet, summary, and prompt-block backend); no release tag contains it yet.
[core-floor-probe] plan_decision_summary: first appears in sase-core 88d6385 (feat(plan): add decision sheet, summary, and prompt-block backend); no release tag contains it yet.
[core-floor-probe] plan_decisions_digest: first appears in sase-core c089cf1 (feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings); no release tag contains it yet.
[core-floor-probe] plan_decisions_payload: first appears in sase-core c089cf1 (feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings); no release tag contains it yet.
[core-floor-probe] plan_decisions_prompt_block: first appears in sase-core 88d6385 (feat(plan): add decision sheet, summary, and prompt-block backend); no release tag contains it yet.
[core-floor-probe] plan_decisions_resolve: first appears in sase-core c089cf1 (feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings); no release tag contains it yet.
[core-floor-probe] project_finalizer_node_view: first appears in sase-core f52fa7c (feat(finalizer): implement core-run-view-model run_view module); release v0.35.1 contains it.
[core-floor-probe] prompt_looks_generated: first appears in sase-core 0ad6e44 (feat(prompt-prediction): flag chop and job tribe origins as generated); release v0.36.2 contains it.
[core-floor-probe] prompt_prediction_wire_schema_version: first appears in sase-core 12e012d (feat(core-binding): add prompt_prediction binding module with tests); release v0.36.1 contains it.
[core-floor-probe] prompt_proc_origin: first appears in sase-core 92a4fc4 (feat(agent-launch): add native %proc dispatch helpers); release v0.31.5 contains it.
[core-floor-probe] read_prompt_stash_archive: first appears in sase-core df23cce (feat(prompt-stash): append-only archive for every permanent stash removal); release v0.36.1 contains it.
[core-floor-probe] read_unread_completion_index: first appears in sase-core 28befcb (feat(notifications): store generations, ack API, and lean unread index); release v0.36.2 contains it.
[core-floor-probe] reconcile_notification_rows: first appears in sase-core 413511f (feat(notifications): lock-held field-scoped reconcile write plus empty raw_suffix matcher parity); release v0.36.1 contains it.
[core-floor-probe] recover_prompt_stash_archive: first appears in sase-core df23cce (feat(prompt-stash): append-only archive for every permanent stash removal); release v0.36.1 contains it.
[core-floor-probe] resolve_input_type: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] resolve_macro_skill_definition: first appears in sase-core c4444ab (feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output); release v0.36.3 contains it.
[core-floor-probe] sanitize_attachment_name: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] scan_note_attachment_refs: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] select_publication_retries: first appears in sase-core 3d406d4 (feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status); release v0.36.5 contains it.
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
[core-floor-probe] wait_epic_follow_reduce: first appears in sase-core 4b4a052 (feat(wait): add pure wait_epic_follow reducer with Python binding (sase-1h7.4)); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "12e012d", "name": "PromptPredictionCorpus", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "12e012d", "name": "PromptPredictionModel", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "28befcb", "name": "ack_agent_completions", "release": "v0.36.2", "subject": "feat(notifications): store generations, ack API, and lean unread index"}, {"commit": "1e51ff3", "name": "alternation_scan", "release": "v0.36.1", "subject": "feat(alternation): shared scanner, binding, diagnostic, and LSP tokens"}, {"commit": "2f16dc4", "name": "argument_list_continuation_edit", "release": "v0.36.6", "subject": "feat(editor): continue existing macro argument lists"}, {"commit": "7806f58", "name": "attachment_audience_decision", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_canonical_extension", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_object_digest_from_relpath", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "43f744b", "name": "attachment_placement", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "7806f58", "name": "attachment_public_object_relpath", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_scan_file", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_scanner_rules_version", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "43f744b", "name": "attachment_sensitive_path_reason", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "43f744b", "name": "attachment_should_auto_fetch", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "bff4860", "name": "bead_probe_target_owner", "release": null, "subject": "feat(bead): one-replay core support for in-mutation resolution and target probing"}, {"commit": "c448ed6", "name": "build_agent_tab_catalog", "release": "v0.36.0", "subject": "feat(agent-tab): core tab model with directive, typed units, and Python bindings"}, {"commit": "c448ed6", "name": "canonicalize_agent_tab_name", "release": "v0.36.0", "subject": "feat(agent-tab): core tab model with directive, typed units, and Python bindings"}, {"commit": "2838c7e", "name": "check_input_value", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "39324ac", "name": "classify_attachment", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "3d406d4", "name": "classify_deferred_prompt_obligation", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "16095fc", "name": "classify_model_value", "release": "v0.36.6", "subject": "feat(macros): add builtin model and effort types with one routing classifier"}, {"commit": "d7f2dbf", "name": "classify_session_manifest_files", "release": "v0.36.5", "subject": "feat(agent-session-manifest): canonical file-set derivation and classification"}, {"commit": "3b27df5", "name": "compare_prose", "release": "v0.36.2", "subject": "feat(prose-diff): add pure sase-core prose_diff module and Python binding"}, {"commit": "39324ac", "name": "compose_note_attachment_text", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "3d406d4", "name": "decide_publication_request_completion", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "a62699b", "name": "editor_snippet_catalog_wire_schema_version", "release": "v0.37.0", "subject": "feat(macros)!: emit canonical macro wires and snippet catalog schema 2"}, {"commit": "1ad57ea", "name": "evaluate_prompt_prediction_replay", "release": "v0.36.1", "subject": "feat(prompt-prediction): add per-point novel coverage and precision to sweep wire"}, {"commit": "33b0250", "name": "goal_card_markdown", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "33b0250", "name": "goal_card_view", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "33b0250", "name": "goal_citation_line", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "d2d9ec7", "name": "goal_fast_path", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "cbe70f6", "name": "goal_ledger_append", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_doctor", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_history", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_init", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_list", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_probe_list", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_show", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_store_schema_version", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_wire_schema_version", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_mint_id", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_projection_refresh", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_projection_status", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "d2d9ec7", "name": "goal_render_card", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "d2d9ec7", "name": "goal_render_list", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "fa39036", "name": "instruction_manifest_wire_schema_version", "release": null, "subject": "feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)"}, {"commit": "3adc01b", "name": "jinja_catalog", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "3adc01b", "name": "jinja_completion", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "3adc01b", "name": "jinja_scope_variables", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "297bc1e", "name": "launch_scratch_liveness_wire_schema_version", "release": "v0.36.0", "subject": "feat(core): launch_scratch_liveness module with procfs probe bindings"}, {"commit": "af5df61", "name": "load_macro_input_type_registry", "release": "v0.37.0", "subject": "feat(core): load plugin input_type registries with resolution, catalog, and LSP wiring"}, {"commit": "0d27dad", "name": "macro_argument_choice_candidates", "release": "v0.36.6", "subject": "feat(macros): carry resolved choice metadata and shared candidates"}, {"commit": "c4444ab", "name": "macro_argument_spans", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "0279de6", "name": "macro_completion_spacer_to_parentheses_edit", "release": "v0.36.6", "subject": "feat(macros): flip emitted wires to macro spellings, rename LSP crate"}, {"commit": "2838c7e", "name": "macro_input_type_catalog", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "0d27dad", "name": "macro_input_type_label", "release": "v0.36.6", "subject": "feat(macros): carry resolved choice metadata and shared candidates"}, {"commit": "c4444ab", "name": "macro_skill_definition_wire_schema_version", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "924884e", "name": "managed_tmp_roots_list", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "924884e", "name": "managed_tmp_roots_register", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "924884e", "name": "managed_tmp_roots_wire_schema_version", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "11f29c3", "name": "memory_history_compare", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_feed", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "c2a415e", "name": "memory_history_mark_reviewed", "release": "v0.36.4", "subject": "feat(memory-history): add review state store with query and mark-reviewed"}, {"commit": "11f29c3", "name": "memory_history_resolve", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "c2a415e", "name": "memory_history_review_state", "release": "v0.36.4", "subject": "feat(memory-history): add review state store with query and mark-reviewed"}, {"commit": "11f29c3", "name": "memory_history_subjects", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_sync", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_timeline", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_version", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_wire_schema_version", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "fa39036", "name": "normalize_instruction_manifest", "release": null, "subject": "feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)"}, {"commit": "4eb40d5", "name": "normalize_macro_config_layer", "release": "v0.36.4", "subject": "feat(compat): shared Rust config normalization contract"}, {"commit": "297bc1e", "name": "observe_launch_scratch_liveness", "release": "v0.36.0", "subject": "feat(core): launch_scratch_liveness module with procfs probe bindings"}, {"commit": "df735e4", "name": "plan_decision_quote_match", "release": null, "subject": "feat(sase-core): add plan decision human quote matcher with PyO3 binding"}, {"commit": "88d6385", "name": "plan_decision_sheet", "release": null, "subject": "feat(plan): add decision sheet, summary, and prompt-block backend"}, {"commit": "88d6385", "name": "plan_decision_summary", "release": null, "subject": "feat(plan): add decision sheet, summary, and prompt-block backend"}, {"commit": "c089cf1", "name": "plan_decisions_digest", "release": null, "subject": "feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings"}, {"commit": "c089cf1", "name": "plan_decisions_payload", "release": null, "subject": "feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings"}, {"commit": "88d6385", "name": "plan_decisions_prompt_block", "release": null, "subject": "feat(plan): add decision sheet, summary, and prompt-block backend"}, {"commit": "c089cf1", "name": "plan_decisions_resolve", "release": null, "subject": "feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings"}, {"commit": "f52fa7c", "name": "project_finalizer_node_view", "release": "v0.35.1", "subject": "feat(finalizer): implement core-run-view-model run_view module"}, {"commit": "0ad6e44", "name": "prompt_looks_generated", "release": "v0.36.2", "subject": "feat(prompt-prediction): flag chop and job tribe origins as generated"}, {"commit": "12e012d", "name": "prompt_prediction_wire_schema_version", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "92a4fc4", "name": "prompt_proc_origin", "release": "v0.31.5", "subject": "feat(agent-launch): add native %proc dispatch helpers"}, {"commit": "df23cce", "name": "read_prompt_stash_archive", "release": "v0.36.1", "subject": "feat(prompt-stash): append-only archive for every permanent stash removal"}, {"commit": "28befcb", "name": "read_unread_completion_index", "release": "v0.36.2", "subject": "feat(notifications): store generations, ack API, and lean unread index"}, {"commit": "413511f", "name": "reconcile_notification_rows", "release": "v0.36.1", "subject": "feat(notifications): lock-held field-scoped reconcile write plus empty raw_suffix matcher parity"}, {"commit": "df23cce", "name": "recover_prompt_stash_archive", "release": "v0.36.1", "subject": "feat(prompt-stash): append-only archive for every permanent stash removal"}, {"commit": "2838c7e", "name": "resolve_input_type", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "c4444ab", "name": "resolve_macro_skill_definition", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "39324ac", "name": "sanitize_attachment_name", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "39324ac", "name": "scan_note_attachment_refs", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "3d406d4", "name": "select_publication_retries", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "9368ddf", "name": "tool_run_briefs", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "830e900", "name": "tool_run_detail", "release": "v0.36.0", "subject": "feat(tool-run): add tool_run_detail projection with stage timeline and witness counts"}, {"commit": "17b072b", "name": "tool_run_duration_calibration", "release": "v0.36.1", "subject": "feat(tool-run): add duration classes and inline-fit policy"}, {"commit": "17b072b", "name": "tool_run_duration_fit", "release": "v0.36.1", "subject": "feat(tool-run): add duration classes and inline-fit policy"}, {"commit": "cee9f49", "name": "tool_run_join", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "9368ddf", "name": "tool_run_live_glance", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "9368ddf", "name": "tool_run_node_summaries", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "7a9ffad", "name": "tool_run_record_demand", "release": "v0.36.2", "subject": "feat(tool-run): record per-run demand context, usage, and worker grants"}, {"commit": "cee9f49", "name": "tool_run_release_join", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "6e23783", "name": "tool_run_stats_report", "release": "v0.36.2", "subject": "feat(tool-run): implement core-stats report for sase-1dm.3"}, {"commit": "cee9f49", "name": "tool_run_sync_wait_budget", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "39324ac", "name": "unique_attachment_name", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "2838c7e", "name": "validate_enum_choices", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "4b4a052", "name": "wait_epic_follow_reduce", "release": null, "subject": "feat(wait): add pure wait_epic_follow reducer with Python binding (sase-1h7.4)"}], "declared_floor": "0.35.0", "exit_code": 4, "message": "sase-core-rs==0.35.0 is missing 107 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.37.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-missing, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 4963 test files in scope
coverage contexts: no baseline cached (run `just refresh-contexts-baseline`); static closure only
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
configfile: pyproject.toml
plugins: cov-7.1.0, xdist-3.8.0, mock-3.15.1, hypothesis-6.168.0, asyncio-1.4.0, inline-snapshot-0.35.4
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [7385 items]

........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  2%]
........s............................................................... [  3%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  9%]
..................................................................F..... [ 10%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 21%]
......................................................F................. [ 22%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 26%]
.................................................................F...... [ 27%]
..............................................................F.....F... [ 28%]
.......FFF.FF........................................................... [ 29%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 36%]
.......................................................................F [ 37%]
........................................................................ [ 38%]
.....................FF................................................. [ 38%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 49%]
...............................F.......F................................ [ 50%]
............................................................F........... [ 51%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 70%]
................F....................................................... [ 71%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 76%]
...............s.........ss............................................. [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 83%]
.......................................................................F [ 84%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........F............................................................... [ 90%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 93%]
F....F.F................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 99%]
.........................................                                [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
________________ test_macro_string_literals_avoid_xprompt_terms ________________
[gw2] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    def test_macro_string_literals_avoid_xprompt_terms() -> None:
        findings: list[str] = []
        for path in iter_scope_files(suffix=".py"):
            relative = path.relative_to(ROOT)
            if _string_scope_ok(relative):
                continue
            for literal in _iter_py_string_lines(path):
                if (relative.as_posix(), literal) not in _MACRO_STRING_ALLOWLIST:
                    findings.append(f"{relative}: string {literal!r}")
        for path in _iter_resource_files():
            relative = path.relative_to(ROOT)
            if _string_scope_ok(relative):
                continue
            if relative.as_posix().startswith(("smoke/", "demos/")) or (
                "/skills/" in relative.as_posix()
            ):
                # Strict zones: skill sources and smoke/demo scripts stay clean.
                try:
                    text = path.read_text(encoding="utf-8")
                except (UnicodeDecodeError, OSError):
                    continue
                for line in text.splitlines():
                    if "xprompt" in line.lower():
                        findings.append(f"{relative}: resource {line.strip()!r}")
>       assert findings == []
               ^^^^^^^^^^^^^^
E       AssertionError

tests/_macro_terminology_strings.py:288: AssertionError
_ test_neutral_plan_archive_failure_is_retryable_without_duplicate_option_work _
[gw2] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

gate_home = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw2/test_neutral_plan_archive_fail0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7446134c7410>

    def test_neutral_plan_archive_failure_is_retryable_without_duplicate_option_work(
        gate_home: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        plan = write_plan(gate_home, "archive-retry.md", VALID_TALE_PLAN)
        gate = create_gate(build_plan_approval_gate_spec(plan, "plan-archive-retry"))
        envelope = json.loads((gate.bundle_path / "request.json").read_text())
        context = plan_context_from_envelope(gate.bundle_path, envelope)
        archived = gate_home / "archived-plan.md"
        archived.write_text("# archived\n", encoding="utf-8")
        calls = {"n": 0}
    
        def flaky_archive(*_args: object, **_kwargs: object) -> _ApprovedPlanArchive:
            calls["n"] += 1
            if calls["n"] == 1:
                raise PlanApprovalActionError(
                    "plan_archive_failed",
                    str(plan),
                    "failed to archive approved plan: archive boom",
                )
            return _ApprovedPlanArchive(archived, "plan:202608/archived-plan.md")
    
        monkeypatch.setattr(
            "sase.plan_approval_actions._archive_plan_for_approval",
            flaky_archive,
        )
    
        with pytest.raises(PlanApprovalActionError) as failed:
            execute_plan_approval_response(
                context,
                "approve",
                commit_plan=True,
                run_coder=True,
            )
    
        assert failed.value.code == "plan_archive_failed"
        assert not gate.response_path.exists()
        assert (gate.bundle_path / "decision_receipt.json").is_file()
        records = list(read_journal_records(gate.bundle_path))
        assert [record["event"] for record in records].count("option_completed") == 2
        [failure] = [record for record in records if record["event"] == "attempt_failed"]
        assert failure["stage"] == "terminal_prepare"
        assert failure["code"] == "plan_archive_failed"
        assert (gate.bundle_path / failure["error_record"]).is_file()
    
        [notification] = [
            row
            for row in load_notifications()
            if row.action == GATE_EXECUTION_FAILED_ACTION
        ]
        assert notification.tags == ["gate", "execution", "error"]
        assert notification.action_data["request_kind"] == "plan"
        assert notification.action_data["stage"] == "terminal_prepare"
        assert notification.action_data["code"] == "plan_archive_failed"
        assert notification.action_data["recovery_actions"] == "resume,restart,cancel"
        assert (
            notification.action_data["resume_command"]
            == "sase gate answer --kind plan --id plan-archive-retry "
            "--option approve --option commit --resume"
        )
        assert (
            notification.action_data["restart_command"]
            == "sase gate answer --kind plan --id plan-archive-retry "
            "--option approve --option commit --restart"
        )
        assert (
            notification.action_data["cancel_command"]
            == "sase gate cancel --kind plan --id plan-archive-retry"
        )
    
        recovered = execute_gate_selection(
            gate.bundle_path,
            ["approve", "commit"],
            {},
            source="plan_response",
            retry="resume",
        )
    
        assert recovered.already_completed is False
        assert calls["n"] == 2
        assert gate.response_path.is_file()
        recovered_records = list(read_journal_records(gate.bundle_path))
        assert [record["event"] for record in recovered_records].count(
            "option_completed"
        ) == 2
        assert "attempt_resumed" in [record["event"] for record in recovered_records]
>       assert translate_plan_gate_response(gate.bundle_path, recovered.response) == {
            "action": "approve",
            "commit_plan": True,
            "run_coder": True,
            "saved_plan_path": str(archived),
            "plan_archive_owner": "host",
            "plan_archive_state": "archived",
            "plan_archive_protocol": "host_v2",
            "plan_archive_ref": "plan:202608/archived-plan.md",
        }
E       AssertionError: assert {'action': 'a...plan.md', ...} == {'action': 'a...plan.md', ...}
E         
E         Omitting 8 identical items, use -vv to show
E         Left contains 4 more items:
E         {'_gate_caller': 'human',
E          '_gate_source': 'plan_response',
E          'decided_by': 'reviewer',
E          'decided_via': 'tui'}
E         Use -v to get more diff

tests/test_plan_approval_actions_archive.py:348: AssertionError
____ test_collapsed_presence_discovery_enriches_and_reuses_member_artifacts ____
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_presence_discov0')

    def test_collapsed_presence_discovery_enriches_and_reuses_member_artifacts(
        tmp_path: Path,
    ) -> None:
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        (artifacts / "raw_prompt.md").write_text(
            "#review representative segment\n",
            encoding="utf-8",
        )
        (artifacts / "01_prompt.md").write_text(
            "Inspect the clan summary contract.\n",
            encoding="utf-8",
        )
        response = artifacts / "response.md"
        response.write_text("Representative reply.\n", encoding="utf-8")
        member = _agent(
            "research.one",
            artifacts_dir=str(artifacts),
            response_path=str(response),
        )
        container = project_clan_tree([member])[0]
        panel = _ClanPanel()
        panel.set_agent_detail_render_context(
            generation=3,
            attempt_view_mode="merged",
            attempt_pinned_number=None,
            is_current=lambda identity, *_args: identity == container.identity,
        )
        panel.set_clan_disk_sections_required(
            clan_disk_sections_for_fold_state(FoldLevel.COLLAPSED)
        )
    
        panel.update_display(container)
    
        from sase.ace.tui.widgets.decks.card_part import flatten_card_document
    
        cold = cast(Text, flatten_card_document(panel.captured[-1])).plain
        for heading in ("REPLIES", "SASE CONTEXT", "SLOW TOOL CALLS", "PROMPTS"):
            assert heading not in cold
        assert cold.count("⋯ scanning member data…") == 1
        assert panel.worker_runs == 1
        assert panel.worker_fn is not None
    
        panel.worker.result = panel.worker_fn()
        panel._apply_clan_section_enrichment_result(
            cast(Worker[Any], panel.worker),
            WorkerState.SUCCESS,
        )
        panel.update_display(container)
    
        cached = get_cached_clan_section_snapshot(panel, container)
        assert cached is not None and cached.disk is not None
        assert cached.disk.loaded_sections == CLAN_DISK_SECTIONS
        assert [entry.preview for entry in cached.disk.replies] == ["Representative reply."]
>       assert [entry.preview for entry in cached.disk.prompts] == [
            "#review representative segment",
            "Inspect the clan summary contract.",
        ]
E       AssertionError: assert ['#review rep...tive segment'] == ['#review rep...ry contract.']
E         
E         At index 1 diff: '#review representative segment' != 'Inspect the clan summary contract.'
E         Use -v to get more diff

tests/ace/tui/widgets/test_agent_clan_aggregation_async.py:181: AssertionError
_ test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace _
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_content_hin0')

    def test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace(
        tmp_path: Path,
    ) -> None:
        root, child = make_agent_session(tmp_path)
        root_workspace = tmp_path / "root-workspace"
        child_workspace = tmp_path / "child-workspace"
        root_workspace.mkdir()
        child_workspace.mkdir()
        root.workspace_dir = str(root_workspace)
        child.workspace_dir = str(child_workspace)
    
        root_dir = Path(root.artifacts_dir or "")
        child_dir = Path(child.artifacts_dir or "")
        (root_dir / "raw_prompt.md").write_text(
            "@docs/visible-macro.md\n"
            + "\n".join(f"macro filler {index}" for index in range(2, 15))
            + "\n@docs/hidden-macro.md\n",
            encoding="utf-8",
        )
        (root_dir / "01_prompt.md").write_text(
            "src/visible-prompt.py\n"
            + "\n".join(f"prompt filler {index}" for index in range(2, 15))
            + "\nsrc/hidden-prompt.py\n",
            encoding="utf-8",
        )
        (root_dir / "response.md").write_text(
            "root/hidden-reply.txt\nroot filler 2\nroot filler 3\n"
            "root filler 4\nroot filler 5\nroot/visible-reply.txt\n",
            encoding="utf-8",
        )
        (child_dir / "response.md").write_text(
            "child/hidden-reply.txt\nchild filler 2\nchild filler 3\n"
            "child filler 4\nchild filler 5\nchild/visible-reply.txt\n",
            encoding="utf-8",
        )
    
        expected_paths = {
            str(root_workspace / "docs/visible-macro.md"),
            str(root_workspace / "docs/hidden-macro.md"),
            str(root_workspace / "src/visible-prompt.py"),
            str(root_workspace / "src/hidden-prompt.py"),
            str(root_workspace / "root/hidden-reply.txt"),
            str(root_workspace / "root/visible-reply.txt"),
            str(child_workspace / "child/hidden-reply.txt"),
            str(child_workspace / "child/visible-reply.txt"),
        }
        rendered_paths: list[set[str]] = []
        for level in (FoldLevel.EXPANDED, FoldLevel.FULLY_EXPANDED):
            panel = FakePromptPanel()
            panel.app = SimpleNamespace(
                panel_fold_level=level,
                _panel_fold_overrides=SimpleNamespace(snapshot=lambda: {}),
            )
            cache_detail_header_summary(panel, root, DetailHeaderSummary())
    
            result = panel.update_display_with_hints(root)
            rendered_paths.append(set(result.file_hints.values()))
    
>       assert rendered_paths == [expected_paths, expected_paths]
E       AssertionError: assert [{'/var/tmp/s...e-reply.txt'}] == [{'/var/tmp/s...ly.txt', ...}]
E         
E         At index 0 diff: {'/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md', '/var/tmp/sase-3573d744/pytest-of-brya...
E         
E         ...Full output truncated (2 lines hidden), use '-vv' to show

tests/ace/tui/widgets/test_agent_display_agent_session_hints.py:168: AssertionError
_____________ test_session_collapsed_detached_macro_skips_markers ______________
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_session_collapsed_detache0')

    def test_session_collapsed_detached_macro_skips_markers(tmp_path: Path) -> None:
        root, _child = make_agent_session(tmp_path)
        workspace = tmp_path / "workspace"
        (workspace / "src").mkdir(parents=True)
        (workspace / "src" / "example.py").write_text("", encoding="utf-8")
        (workspace / "src" / "body.py").write_text("", encoding="utf-8")
        root.workspace_dir = str(workspace)
        Path(str(root.artifacts_dir)).joinpath("raw_prompt.md").write_text(
            "Read @src/example.py\n", encoding="utf-8"
        )
        Path(str(root.artifacts_dir)).joinpath("01_prompt.md").write_text(
            "See src/body.py\n", encoding="utf-8"
        )
        panel = _CollapsedDetachedSessionPanel()
    
        result = panel.update_display_with_hints(root)
    
        identity = find_identity_header(panel.captured[-1])
        assert identity is not None
        assert identity.raw_prompt is not None
        assert "[1]" not in identity.raw_prompt.plain
        assert "Read @src/example.py" in identity.raw_prompt.plain
>       assert str(workspace / "src/example.py") not in result.file_hints.values()
E       AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_session_collapsed_detache0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_session_collapsed_detache0/workspace/src/example.py'])
E        +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_session_collapsed_detache0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_session_collapsed_detache0/workspace') / 'src/example.py'))
E        +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_session_collapsed_detache0/workspace/src/example.py']) = <built-in method values of dict object at 0x7edc18151700>()
E        +    where <built-in method values of dict object at 0x7edc18151700> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_session_collapsed_detache0/workspace/src/example.py'}.values
E        +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_session_collapsed_detache0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_session_collapsed_detac... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints

tests/ace/tui/widgets/test_agent_display_agent_session_hints.py:290: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.COLLAPSED-overrides0] _
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_conversatio0')
level = <FoldLevel.COLLAPSED: 'collapsed'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nTurns: --plan · CLAUDE(opus)\n       --code · CLAUDE(sonnet)\nTimestamps: ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides1] _
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_conversatio1')
level = <FoldLevel.EXPANDED: 'expanded'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nTurns: --plan · CLAUDE(opus)\n       --code · CLAUDE(sonnet)\nTimestamps: ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.FULLY_EXPANDED-overrides2] _
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_conversatio2')
level = <FoldLevel.FULLY_EXPANDED: 'fully_expanded'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nTurns: --plan · CLAUDE(opus)\n       --code · CLAUDE(sonnet)\nTimestamps: ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.EXHAUSTIVE-overrides3] _
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_conversatio3')
level = <FoldLevel.EXHAUSTIVE: 'exhaustive'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nTurns: --plan · CLAUDE(opus)\n       --code · CLAUDE(sonnet)\nTimestamps: ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides4] _
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_session_conversatio4')
level = <FoldLevel.EXPANDED: 'expanded'>
overrides = {'agent-raw-prompt': <FoldLevel.COLLAPSED: 'collapsed'>, 'agent-prompt': <FoldLevel.EXPANDED: 'expanded'>, 'agent-reply': <FoldLevel.FULLY_EXPANDED: 'fully_expanded'>}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nTurns: --plan · CLAUDE(opus)\n       --code · CLAUDE(sonnet)\nTimestamps: ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
___________ test_agent_macro_and_prompt_receive_roles_replies_do_not ___________
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_agent_macro_and_prompt_re0')

    def test_agent_macro_and_prompt_receive_roles_replies_do_not(
        tmp_path: Path,
    ) -> None:
        panel = FakePromptPanel()
        source = "Ask Agent Clan to inspect sase-core; run `checks`"
        glossary = dynamic_catalog_for_term(tmp_path, "Agent Clan")
        repo = dynamic_catalog_for_identifier(tmp_path, "sase-core")
        install_panel_semantics(panel, glossary=glossary, repo=repo)
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            raw_prompt="#git:sase %auto Ask Agent Clan to inspect sase-core",
        )
        Path(agent.artifacts_dir, "01_prompt.md").write_text(
            source + "\n", encoding="utf-8"
        )
        Path(agent.response_path).write_text(
            "Reply repeats Agent Clan and sase-core.\n",
            encoding="utf-8",
        )
    
        panel.update_display(agent)
        rendered = flatten_card_document(panel.captured[-1])
        header = _header_text(rendered)
        assert MACRO_TOKEN_STYLES["invocation"] in _styles_at(header, "#git")
        assert _has_role_underline(_styles_at(header, "Agent Clan"))
        assert _has_role_underline(_styles_at(header, "sase-core"))
    
        prompt_body = _prompt_body(rendered)
        assert _has_role_underline(_styles_at(prompt_body, "Agent Clan"))
>       inline = _styles_at(prompt_body, "`checks`", offset=1)
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/widgets/test_agent_prompt_semantic.py:198: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

text = <text '#git:sase %auto Ask Agent Clan to inspect sase-core' [Span(0, 51, Style(color=Color('#f8f8f2', ColorType.TRUECO...nderline=True))] Style(bgcolor=Color('#272822', ColorType.TRUECOLOR, triplet=ColorTriplet(red=39, green=40, blue=34)))>
needle = '`checks`', offset = 1

    def _styles_at(
        text: Text | AgentHeaderRenderable,
        needle: str,
        *,
        offset: int = 0,
    ) -> set[str]:
>       position = text.plain.index(needle) + offset
                   ^^^^^^^^^^^^^^^^^^^^^^^^
E       ValueError: substring not found

tests/ace/tui/widgets/test_agent_prompt_semantic.py:64: ValueError
________ test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers ________
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_hinted_raw_prompt_moves_t0')

    def test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers(
        tmp_path: Path,
    ) -> None:
        workspace = tmp_path / "workspace"
        workspace.mkdir()
        panel = _DetachedPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
            raw_prompt="Read @src/example.py",
        )
    
        result = panel.update_display_with_hints(agent)
    
        identity = find_identity_header(panel.captured[-1])
        assert identity is not None
        assert identity.raw_prompt is not None
        assert identity.raw_prompt.plain == "Read [1] @src/example.py"
>       assert result.file_hints == {1: str(workspace / "src/example.py")}
E       AssertionError: assert {1: '/var/tmp...c/example.py'} == {1: '/var/tmp...c/example.py'}
E         
E         Omitting 1 identical items, use -vv to show
E         Left contains 1 more item:
E         {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_hinted_raw_prompt_moves_t0/workspace/src/example.py'}
E         Use -v to get more diff

tests/ace/tui/widgets/test_identity_header_raw_prompt.py:127: AssertionError
_______________ test_collapsed_detached_raw_prompt_skips_markers _______________
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_detached_raw_pr0')

    def test_collapsed_detached_raw_prompt_skips_markers(tmp_path: Path) -> None:
        workspace = tmp_path / "workspace"
        (workspace / "src").mkdir(parents=True)
        (workspace / "src" / "example.py").write_text("", encoding="utf-8")
        (workspace / "src" / "body.py").write_text("", encoding="utf-8")
        panel = _CollapsedDetachedPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
            raw_prompt="Read @src/example.py",
        )
        prompt_path = Path(str(agent.artifacts_dir)) / "01_prompt.md"
        prompt_path.write_text("See src/body.py\n", encoding="utf-8")
    
        result = panel.update_display_with_hints(agent)
    
        identity = find_identity_header(panel.captured[-1])
        assert identity is not None
        assert identity.raw_prompt is not None
        assert identity.raw_prompt.plain == "Read @src/example.py"
        assert "[1]" not in identity.raw_prompt.plain
>       assert str(workspace / "src/example.py") not in result.file_hints.values()
E       AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_detached_raw_pr0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_detached_raw_pr0/workspace/src/example.py'])
E        +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_detached_raw_pr0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_detached_raw_pr0/workspace') / 'src/example.py'))
E        +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_detached_raw_pr0/workspace/src/example.py']) = <built-in method values of dict object at 0x7edc1176eec0>()
E        +    where <built-in method values of dict object at 0x7edc1176eec0> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_detached_raw_pr0/workspace/src/example.py'}.values
E        +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_detached_raw_pr0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_collapsed_detached_raw_... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints

tests/ace/tui/widgets/test_identity_header_raw_prompt.py:153: AssertionError
___________ test_plan_action_api_executes_selected_approval_options ____________
[gw2] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

gate_home = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw2/test_plan_action_api_executes_0')
stub_host_plan_archive = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw2/test_plan_action_api_executes_0/host-archived-plan.md')

    def test_plan_action_api_executes_selected_approval_options(
        gate_home: Path,
        stub_host_plan_archive: Path,
    ) -> None:
        gate = create_gate(
            build_plan_approval_gate_spec(
                write_plan(gate_home, "action-api.md", VALID_TALE_PLAN),
                "action-api",
            )
        )
        envelope = json.loads(gate.request_path.read_text(encoding="utf-8"))
    
        action_result = execute_plan_approval_response(
            plan_context_from_envelope(gate.bundle_path, envelope),
            "approve",
            commit_plan=True,
            run_coder=False,
        )
    
        assert action_result.response_json["selected_option_ids"] == ["commit"]
>       assert action_result.response_json["option_results"] == [
            {
                "id": "commit",
                "result": {
                    "action": "approve",
                    "commit_plan": True,
                    "run_coder": False,
                    "plan_archive_owner": "host",
                    "plan_archive_state": "archived",
                    "plan_archive_protocol": "host_v2",
                    "plan_archive_ref": "plan:202608/host-archived-plan.md",
                    "saved_plan_path": str(stub_host_plan_archive),
                },
            }
        ]
E       AssertionError: assert [{'id': 'comm...ponse', ...}}] == [{'id': 'comm...'host', ...}}]
E         
E         At index 0 diff: {'id': 'commit', 'result': {'action': 'approve', 'commit_plan': True, 'run_coder': False, '_gate_source': 'plan_response', '_gate_caller': 'human', 'decided_by': 'reviewer', 'decided_via': 'tui', 'plan_archive_owner': 'host', 'plan_archive_state': 'archived', 'saved_plan_path': '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw2/test_plan_action_api_executes_0/host-archived-plan.md', 'plan_archive_protocol': 'host_v2', 'plan_archive_ref': 'plan:202608/host-archived-plan.md'}} != {'id': 'commit', 'result': {'action': 'approve', 'commit_plan': True...
E         
E         ...Full output truncated (2 lines hidden), use '-vv' to show

tests/test_plan_gates_action_api.py:54: AssertionError
_________ test_plan_action_api_filters_coder_options_for_commit_preset _________
[gw2] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

gate_home = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw2/test_plan_action_api_filters_c0')
stub_host_plan_archive = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw2/test_plan_action_api_filters_c0/host-archived-plan.md')

    def test_plan_action_api_filters_coder_options_for_commit_preset(
        gate_home: Path,
        stub_host_plan_archive: Path,
    ) -> None:
        gate = create_gate(
            build_plan_approval_gate_spec(
                write_plan(gate_home, "action-commit.md", VALID_TALE_PLAN),
                "action-commit",
            )
        )
        envelope = json.loads(gate.request_path.read_text(encoding="utf-8"))
    
        action_result = execute_plan_approval_response(
            plan_context_from_envelope(gate.bundle_path, envelope),
            "commit",
            coder_prompt="#review+",
        )
    
        assert action_result.response_json["selected_option_ids"] == ["commit"]
        assert action_result.response_json["input"] == {}
>       assert action_result.response_json["option_results"][0]["result"] == {
            "action": "approve",
            "commit_plan": True,
            "run_coder": False,
            "plan_archive_owner": "host",
            "plan_archive_state": "archived",
            "plan_archive_protocol": "host_v2",
            "plan_archive_ref": "plan:202608/host-archived-plan.md",
            "saved_plan_path": str(stub_host_plan_archive),
        }
E       AssertionError: assert {'action': 'a...esponse', ...} == {'action': 'a...: 'host', ...}
E         
E         Omitting 8 identical items, use -vv to show
E         Left contains 4 more items:
E         {'_gate_caller': 'human',
E          '_gate_source': 'plan_response',
E          'decided_by': 'reviewer',
E          'decided_via': 'tui'}
E         Use -v to get more diff

tests/test_plan_gates_action_api.py:126: AssertionError
________ test_shared_host_executor_handles_feedback_rejection_and_races ________
[gw2] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

gate_home = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw2/test_shared_host_executor_hand0')

    def test_shared_host_executor_handles_feedback_rejection_and_races(
        gate_home: Path,
    ) -> None:
        create_gate(
            build_plan_approval_gate_spec(
                write_plan(gate_home, "feedback.md", VALID_TALE_PLAN),
                "feedback-request",
            )
        )
        [feedback_notification] = load_notifications()
        feedback_result = execute_plan_approval_response(
            plan_context_from_notification(feedback_notification),
            "feedback",
            feedback="Add rollback coverage",
        )
        assert feedback_result.response_file == "response.json"
        assert feedback_result.response_json["selected_option_ids"] == ["feedback"]
>       assert feedback_result.response_json["option_results"] == [
            {
                "id": "feedback",
                "result": {
                    "action": "reject",
                    "feedback": "Add rollback coverage",
                },
            }
        ]
E       AssertionError: assert [{'id': 'feed...human', ...}}] == [{'id': 'feed...k coverage'}}]
E         
E         At index 0 diff: {'id': 'feedback', 'result': {'action': 'reject', 'feedback': 'Add rollback coverage', '_gate_source': 'plan_response', '_gate_caller': 'human', 'decided_by': 'reviewer', 'decided_via': 'tui'}} != {'id': 'feedback', 'result': {'action': 'reject', 'feedback': 'Add rollback coverage'}}
E         Use -v to get more diff

tests/test_plan_gates_execution.py:207: AssertionError
____________ test_post_dispatch_foreign_race_on_external_is_exempt _____________
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

instance = ConfiguredFinalizerInstance(instance_id='commit', provider_ref='builtin@commit', after=(), max_attempts=2, refusal='fail', config={}, provenance={'use': FinalizerFieldProvenance(layer='test', path=None)})
context = FinalizerExecutionContext(artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw0/test_post_dispatch_...al object at 0x71342fcc8980>, tracker=<sase.finalizers.status_summary.FinalizerStatusTracker object at 0x71342fccb080>)
ledger = InstanceLedger(instance_id='commit', max_attempts=2, consumed=1, next_attempt=2, attempts=[FinalizerAttemptWire(attemp...based HEAD.', severity='error', instance_id='commit', attempt=1)], refusal_reason=None, deferral=None, status='failed')
journal = <sase.finalizers.progress.ProgressJournal object at 0x71342fcc8980>
provider = <MagicMock id='124469133349264'>
invoke_result = InvokeResult(content='done', usage=None), model_tier = 'large'
suppress_output = True, model_override = None, options = None
artifacts_dir = '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw0/test_post_dispatch_foreign_rac0/artifacts'
original_prompt = 'do work', no_model = False

    def _run_budgeted_commit(
        instance: Any,
        context: FinalizerExecutionContext,
        ledger: InstanceLedger,
        *,
        journal: ProgressJournal | None = None,
        provider: Any,
        invoke_result: Any,
        model_tier: ModelTier,
        suppress_output: bool,
        model_override: str | None,
        options: Any,
        artifacts_dir: str | None,
        original_prompt: str | None = None,
        no_model: bool = False,
    ) -> BuiltinCommitExecution:
        current_result = invoke_result
        ledger_before_run = load_commit_results(artifact_root(context.artifacts_dir))
        while True:
            consumed_before = ledger.consumed
            try:
>               execution = execute_commit_finalizer(
                    instance,
                    context,
                    provider=provider,
                    invoke_result=current_result,
                    model_tier=model_tier,
                    suppress_output=suppress_output,
                    model_override=model_override,
                    options=options,
                    ledger=ledger,
                    ledger_before_already_clean=ledger_before_run,
                )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/controller_cycle.py:214: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/commit_execution.py:377: in execute_commit_finalizer
    dispatched = dispatch_commit_decisions(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/commit_dispatch.py:433: in dispatch_commit_decisions
    repair_result = resolve_commit_conflict(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/commit_repair.py:113: in resolve_commit_conflict
    return _conflict_repair.resolve_commit_conflict(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/commit_repair_conflict.py:236: in resolve_commit_conflict
    return _verify_settled_or_raise(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

repo = DirtyRepo(name='research', path='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw0/test_post_dispatch_foreign_rac0/other', changed_files=('README.md',), kind='external')
context = FinalizerExecutionContext(artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw0/test_post_dispatch_...al object at 0x71342fcc8980>, tracker=<sase.finalizers.status_summary.FinalizerStatusTracker object at 0x71342fccb080>)
provider = <MagicMock id='124469133349264'>
invoke_result = InvokeResult(content='done\n\nrepaired', usage=None)
attempts = [FinalizerAttemptWire(attempt=1, status='failed', diagnostic_code='commit_conflict')]
evidence = [FinalizerOutcomeEvidenceWire(kind='cwd', value='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw0/test_post_d...7d5a95f57a18f849'), FinalizerOutcomeEvidenceWire(kind='commit_tree', value='4590793a8b2cc88f6bbbd7a7e10bcea90c66b93f')]
instance_id = 'commit'
git_changed_files_fn = <function git_changed_files at 0x7134431f4180>
git_head_commit_id_fn = <function git_head_commit_id at 0x7134431f4400>
git_unpushed_records_fn = <function _default_unpushed_records at 0x7134431d9f80>

    def _verify_settled_or_raise(
        repo: DirtyRepo,
        context: FinalizerExecutionContext,
        *,
        provider: Any,
        invoke_result: InvokeResult,
        attempts: list[FinalizerAttemptWire],
        evidence: list[FinalizerOutcomeEvidenceWire],
        instance_id: str,
        git_changed_files_fn: _GitChangedFiles,
        git_head_commit_id_fn: _GitHeadCommitId,
        git_unpushed_records_fn: _GitUnpushedRecords,
    ) -> ConflictRepairResult:
        if _repo_is_settled_after_repair(
            repo,
            provider=provider,
            git_changed_files_fn=git_changed_files_fn,
            git_unpushed_records_fn=git_unpushed_records_fn,
        ):
            evidence.append(
                FinalizerOutcomeEvidenceWire(
                    kind="conflict_repair", value="resolved_without_commit"
                )
            )
            evidence.append(
                FinalizerOutcomeEvidenceWire(
                    kind="head_sha", value=git_head_commit_id_fn(repo.path)
                )
            )
            return ConflictRepairResult(
                invoke_result=invoke_result,
                resolved_without_commit=True,
            )
        unpushed = _safe_unpushed_records(repo.path, git_unpushed_records_fn)
        clean = _repo_is_clean_after_repair(
            repo, provider=provider, git_changed_files_fn=git_changed_files_fn
        )
        if clean and unpushed:
            message_text = (
                f"sase stitch create --resume completed for {repo.name}, but HEAD is "
                "ahead of its upstream with unpushed commits and no "
                "commit_results.json entry was recorded:\n"
                + _format_unpushed_lines(unpushed)
                + "\nRun `sase stitch create --resume` to publish the rebased HEAD."
            )
>           raise BuiltinCommitFinalizerError(
                message_text,
                result=failed_result(
                    instance_id,
                    "unpushed_after_repair",
                    message_text,
                    attempts=attempts,
                    evidence=evidence,
                ),
                invoke_result=invoke_result,
            )
E           sase.finalizers.commit_types.BuiltinCommitFinalizerError: sase stitch create --resume completed for research, but HEAD is ahead of its upstream with unpushed commits and no commit_results.json entry was recorded:
E             ce4b6bfc6aed commit dirty payload
E           Run `sase stitch create --resume` to publish the rebased HEAD.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/commit_repair_conflict.py:354: BuiltinCommitFinalizerError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw0/test_post_dispatch_foreign_rac0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x71342f7371d0>

    def test_post_dispatch_foreign_race_on_external_is_exempt(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo, other, artifacts = _setup_main_and_external(tmp_path, monkeypatch)
        seen = _stitch_with_side_effect(monkeypatch, "foreign-commit")
    
        _live_config(monkeypatch)
        resolve_and_persist_finalizer_plan(PromptDirectives(), artifacts_dir=str(artifacts))
        submit_from_context(artifacts)
>       result = run_controller(artifacts, _live_provider())
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_finalizers_discard_guard_before_head.py:286: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/finalizers_live_e2e_test_helpers.py:324: in run_controller
    return run_finalizers(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/controller_run.py:290: in run_finalizers
    current_result = execute_pending_entry(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/controller_cycle.py:98: in execute_pending_entry
    execution = _run_budgeted_commit(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

instance = ConfiguredFinalizerInstance(instance_id='commit', provider_ref='builtin@commit', after=(), max_attempts=2, refusal='fail', config={}, provenance={'use': FinalizerFieldProvenance(layer='test', path=None)})
context = FinalizerExecutionContext(artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw0/test_post_dispatch_...al object at 0x71342fcc8980>, tracker=<sase.finalizers.status_summary.FinalizerStatusTracker object at 0x71342fccb080>)
ledger = InstanceLedger(instance_id='commit', max_attempts=2, consumed=1, next_attempt=2, attempts=[FinalizerAttemptWire(attemp...based HEAD.', severity='error', instance_id='commit', attempt=1)], refusal_reason=None, deferral=None, status='failed')
journal = <sase.finalizers.progress.ProgressJournal object at 0x71342fcc8980>
provider = <MagicMock id='124469133349264'>
invoke_result = InvokeResult(content='done', usage=None), model_tier = 'large'
suppress_output = True, model_override = None, options = None
artifacts_dir = '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw0/test_post_dispatch_foreign_rac0/artifacts'
original_prompt = 'do work', no_model = False

    def _run_budgeted_commit(
        instance: Any,
        context: FinalizerExecutionContext,
        ledger: InstanceLedger,
        *,
        journal: ProgressJournal | None = None,
        provider: Any,
        invoke_result: Any,
        model_tier: ModelTier,
        suppress_output: bool,
        model_override: str | None,
        options: Any,
        artifacts_dir: str | None,
        original_prompt: str | None = None,
        no_model: bool = False,
    ) -> BuiltinCommitExecution:
        current_result = invoke_result
        ledger_before_run = load_commit_results(artifact_root(context.artifacts_dir))
        while True:
            consumed_before = ledger.consumed
            try:
                execution = execute_commit_finalizer(
                    instance,
                    context,
                    provider=provider,
                    invoke_result=current_result,
                    model_tier=model_tier,
                    suppress_output=suppress_output,
                    model_override=model_override,
                    options=options,
                    ledger=ledger,
                    ledger_before_already_clean=ledger_before_run,
                )
            except BuiltinCommitFinalizerError as exc:
                if (
                    exc.code == "stale_commit_declaration"
                    and not no_model
                    and not declaration_recovery_spent(artifacts_dir)
                    and ledger.consumed == consumed_before
                ):
                    if journal is not None:
                        current_result = ensure_declaration_with_events(
                            journal,
                            provider=provider,
                            invoke_result=exc.invoke_result or current_result,
                            model_tier=model_tier,
                            suppress_output=suppress_output,
                            model_override=model_override,
                            artifacts_dir=artifacts_dir,
                            options=options,
                            original_prompt=original_prompt,
                        )
                    else:
                        current_result = ensure_current_declaration(
                            provider=provider,
                            invoke_result=exc.invoke_result or current_result,
                            model_tier=model_tier,
                            suppress_output=suppress_output,
                            model_override=model_override,
                            artifacts_dir=artifacts_dir,
                            options=options,
                            original_prompt=original_prompt,
                        )
                    execution = execute_commit_finalizer(
                        instance,
                        context,
                        provider=provider,
                        invoke_result=current_result,
                        model_tier=model_tier,
                        suppress_output=suppress_output,
                        model_override=model_override,
                        options=options,
                        ledger=ledger,
                        ledger_before_already_clean=ledger_before_run,
                    )
                    return BuiltinCommitExecution(
                        invoke_result=execution.invoke_result,
                        result=ledger.record(execution.result),
                    )
                merged = ledger.record(exc.result)
                if (
                    ledger.consumed > consumed_before
                    and is_retryable_result(exc.result)
                    and ledger.remaining() > 0
                ):
                    if exc.invoke_result is not None:
                        current_result = exc.invoke_result
                    continue
>               raise BuiltinCommitFinalizerError(
                    result_failure_message(merged),
                    result=merged,
                    invoke_result=exc.invoke_result,
                ) from exc
E               sase.finalizers.commit_types.BuiltinCommitFinalizerError: sase stitch create --resume completed for research, but HEAD is ahead of its upstream with unpushed commits and no commit_results.json entry was recorded:
E                 ce4b6bfc6aed commit dirty payload
E               Run `sase stitch create --resume` to publish the rebased HEAD.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/controller_cycle.py:281: BuiltinCommitFinalizerError
------------------------------ Captured log call -------------------------------
WARNING  sase.llm_provider._instruction_boundary:_instruction_boundary.py:348 instruction shadow render failed: invalid fact provider='unknown'; valid values: agy, claude, codex, fakey, grok, muse, opencode, qwen
_____________ test_default_list_includes_claimed_with_shared_glyph _____________
[gw2] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

claimed_view = <tests.test_bead.test_claimed_status._ReadView object at 0x74460b8f21e0>
capsys = <_pytest.capture.CaptureFixture object at 0x74460b8f31d0>

    def test_default_list_includes_claimed_with_shared_glyph(
        claimed_view: _ReadView,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
>       cli_query.handle_bead_list(
            argparse.Namespace(
                status=None,
                type=None,
                tier=None,
                limit=None,
                format="compact",
            )
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_bead/test_claimed_status.py:79: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

args = Namespace(status=None, type=None, tier=None, limit=None, format='compact')

    def handle_bead_list(args: argparse.Namespace) -> None:
        use_color = resolve_color(getattr(args, "color", "auto"))
        window = _resolve_created_window(args)
        with get_read_view() as view:
            explicit_statuses = args.status is not None
            statuses = (
                _list_statuses(args.status)
                if explicit_statuses
                else list(DEFAULT_LIST_STATUSES)
            )
            issue_types = [IssueType(t) for t in args.type] if args.type else None
            tiers = [BeadTier(t) for t in args.tier] if args.tier else None
            task_types = getattr(args, "task_type", None)
            explicit_limit = getattr(args, "limit", None) is not None
            if window == (None, None):
                # Pushdown lane: task-type filtering, the newest-N limit, and
                # the pre-limit total all resolve inside the read model, so
                # bounded listings never hydrate the rows they drop.
                limit = getattr(args, "limit", None)
                if limit is None and Status.CLOSED in statuses:
                    limit = DEFAULT_CLOSED_LIST_LIMIT
>               total, issues = view.list_issue_page(
                                ^^^^^^^^^^^^^^^^^^^^
                    statuses=statuses,
                    issue_types=issue_types,
                    tiers=tiers,
                    task_types=task_types,
                    limit=limit,
                )
E               AttributeError: '_ReadView' object has no attribute 'list_issue_page'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/bead/cli_query.py:109: AttributeError
______________ test_ordinary_gate_detaches_when_explicitly_asked _______________
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x713439b77470>

    def test_ordinary_gate_detaches_when_explicitly_asked(
        gate_home: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        del gate_home
        mock = _mock_submit(monkeypatch)
        gate = create_gate(_spec("plain-2"))
    
        code, payload = _run(
            "answer", "-i", "plain-2", "-k", "custom", "-o", "cleanup", "--detach"
        )
    
        assert code == 0
        mock.assert_called_once()
        submitted = mock.call_args.args[0]
        assert submitted.argv == [
            "sase",
            "gate",
            "answer",
            "--id",
            "plain-2",
            "--kind",
            "custom",
            "--no-detach",
            "--json",
        ]
>       assert submitted.operation_payload == {"option_ids": ["cleanup"]}
E       AssertionError: assert {'option_ids'...ource': 'cli'} == {'option_ids': ['cleanup']}
E         
E         Omitting 1 identical items, use -vv to show
E         Left contains 1 more item:
E         {'source': 'cli'}
E         Use -v to get more diff

tests/test_gate_cli_answer_detach.py:156: AssertionError
________________ test_fast_path_guards_mutations_but_not_reads _________________
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_fast_path_guards_mutation0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7edc13a9d820>

    def test_fast_path_guards_mutations_but_not_reads(tmp_path: Path, monkeypatch) -> None:
        read_dir = tmp_path / "production" / "beads"
        context = bead_fast_path._FastPathContext(
            read_beads_dirs=[read_dir],
            write_beads_dir=read_dir,
            relativize_design_paths=False,
        )
        calls: list[list[str]] = []
    
        def fake_binding(
            argv: list[str],
            _read_beads_dirs: list[str],
            _write_beads_dir: str,
            _cwd: str,
            _relativize_design_paths: bool,
        ) -> dict[str, object]:
            calls.append(argv)
            return {"handled": True, "exit_code": 0}
    
        monkeypatch.setattr(
            bead_fast_path,
            "_resolve_fast_path_context",
            lambda _argv: context,
        )
        monkeypatch.setattr(
            "sase.core.rust.require_rust_binding",
            lambda _name: fake_binding,
        )
        monkeypatch.setenv("PYTEST_CURRENT_TEST", "fast-path write guard")
        monkeypatch.setenv("SASE_PYTEST_SANDBOX_DIR", str(tmp_path / "sandbox"))
    
        assert try_handle_bead_fast_path(["search", "needle"]) == 0
        for argv in (["+1", "beads-1", "-n", "evidence"], ["rm", "beads-1"]):
>           with pytest.raises(RuntimeError, match=re.escape(f"fast-path {argv[0]}")):
E           Failed: DID NOT RAISE RuntimeError

tests/main/test_bead_fast_path.py:174: Failed
_________ test_fast_path_refuses_unsafe_resolved_location_before_rust __________
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_fast_path_refuses_unsafe_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7edc11b29250>

    def test_fast_path_refuses_unsafe_resolved_location_before_rust(
        tmp_path: Path, monkeypatch
    ) -> None:
        from sase.bead.cli_common import _BeadsLocation
        from sase.bead.model import IssueType
        from sase.bead.project import BeadProject
    
        unsafe_root = tmp_path / "production"
        unsafe_beads_dir = unsafe_root / "sdd/beads"
        with BeadProject.init(unsafe_root) as project:
            issue = project.create(
                "Unsafe remove", IssueType.TASK, task_type="bug", size="small"
            )
        sandbox = tmp_path / "sandbox"
        sandbox.mkdir()
    
        def fake_resolve_beads_location(*_args, **_kwargs):
            return _BeadsLocation(root=unsafe_root, beads_dirname="sdd/beads")
    
        def fail_binding(_name: str):
            raise AssertionError("unsafe bead write reached Rust binding")
    
        monkeypatch.chdir(tmp_path)
        monkeypatch.setattr(
            "sase.bead.cli_common.resolve_beads_location",
            fake_resolve_beads_location,
        )
        monkeypatch.setattr("sase.bead.sync.bead_refresh_mode", lambda: "background")
        monkeypatch.setattr("sase.core.rust.require_rust_binding", fail_binding)
        monkeypatch.setenv("PYTEST_CURRENT_TEST", "fast-path unsafe resolver")
        monkeypatch.setenv("SASE_PYTEST_SANDBOX_DIR", str(sandbox))
    
        with pytest.raises(RuntimeError) as exc_info:
>           try_handle_bead_fast_path(["rm", issue.id])

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/main/test_bead_fast_path.py:280: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/main/bead_fast_path.py:78: in try_handle_bead_fast_path
    return execute_bead_cli(argv)
           ^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/main/bead_fast_path.py:103: in execute_bead_cli
    context = _resolve_fast_path_context(argv, terminal_errors=True)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/main/bead_fast_path.py:232: in _resolve_fast_path_context
    bead_context = resolve_operation_context_for_targets(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/bead/operation_context.py:135: in resolve_operation_context_for_targets
    routes, batch_error = _route_targets_local_first(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/bead/operation_context.py:325: in _route_targets_local_first
    if _looks_like_full_bead_id(target) and not _local_probe_hit(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/bead/operation_context.py:366: in _local_probe_hit
    status, _stem = probe_bead_target_owner(local_descriptor.beads_dir, target)
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/bead/cross_project.py:124: in probe_bead_target_owner
    binding = require_rust_binding("bead_probe_target_owner")
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

_name = 'bead_probe_target_owner'

    def fail_binding(_name: str):
>       raise AssertionError("unsafe bead write reached Rust binding")
E       AssertionError: unsafe bead write reached Rust binding

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/main/test_bead_fast_path.py:267: AssertionError
______ test_fast_path_refuses_mutation_from_plain_checkout_sidecar_record ______
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-1/popen-gw3/test_fast_path_refuses_mutatio0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7edc11b29c10>
capsys = <_pytest.capture.CaptureFixture object at 0x7edc20517800>

    def test_fast_path_refuses_mutation_from_plain_checkout_sidecar_record(
        tmp_path: Path,
        monkeypatch,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        from sase.bead.model import IssueType
        from sase.bead.project import BeadProject
        from sase.sdd.store import write_sdd_store_record
    
        checkout = tmp_path / "checkout"
        beads_dir = checkout / "sase" / "repos" / "plans" / "beads"
        with BeadProject.init(beads_dir.parent, beads_dirname="beads") as project:
            issue = project.create(
                "Read-only remove", IssueType.TASK, task_type="bug", size="small"
            )
        write_sdd_store_record(
            checkout,
            {
                "schema_version": 2,
                "storage": "sidecar_repos",
                "provider": "github",
                "sidecars": {
                    "plans": {
                        "repo": "acme/project--plans",
                        "remote_url": "git@example.com:acme/project--plans.git",
                    },
                    "research": {
                        "repo": "acme/project--research",
                        "remote_url": "git@example.com:acme/project--research.git",
                    },
                },
            },
        )
        monkeypatch.chdir(checkout)
        monkeypatch.setattr(
            "sase.bead.cli_location._resolve_workspace_context",
            lambda _cwd: None,
        )
        monkeypatch.setattr("sase.bead.sync.bead_refresh_mode", lambda: "background")
    
        def fail_binding(_name: str):
            raise AssertionError("read-only bead mutation reached Rust binding")
    
        monkeypatch.setattr("sase.core.rust.require_rust_binding", fail_binding)
    
>       assert try_handle_bead_fast_path(["rm", issue.id]) == 1
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/main/test_bead_fast_path.py:333: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/main/bead_fast_path.py:78: in try_handle_bead_fast_path
    return execute_bead_cli(argv)
           ^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/main/bead_fast_path.py:103: in execute_bead_cli
    context = _resolve_fast_path_context(argv, terminal_errors=True)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/main/bead_fast_path.py:232: in _resolve_fast_path_context
    bead_context = resolve_operation_context_for_targets(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/bead/operation_context.py:135: in resolve_operation_context_for_targets
    routes, batch_error = _route_targets_local_first(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/bead/operation_context.py:325: in _route_targets_local_first
    if _looks_like_full_bead_id(target) and not _local_probe_hit(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/bead/operation_context.py:366: in _local_probe_hit
    status, _stem = probe_bead_target_owner(local_descriptor.beads_dir, target)
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/bead/cross_project.py:124: in probe_bead_target_owner
    binding = require_rust_binding("bead_probe_target_owner")
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

_name = 'bead_probe_target_owner'

    def fail_binding(_name: str):
>       raise AssertionError("read-only bead mutation reached Rust binding")
E       AssertionError: read-only bead mutation reached Rust binding

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/main/test_bead_fast_path.py:329: AssertionError
=============================== warnings summary ===============================
tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /usr/lib/python3.12/json/decoder.py:353: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
63.47s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
52.31s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
33.00s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
29.64s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
23.50s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
18.00s call     tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace
16.68s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
16.20s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
14.52s call     tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
13.62s call     tests/fakey/test_pipe_e2e.py::test_two_link_chain_then_bound_leaves_the_agent_running
12.44s call     tests/test_finalizers_live_e2e_cycles.py::test_live_command_and_fixture_plugin_run_in_order
11.35s call     tests/test_finalizers_run_view_adapter.py::test_plugin_execute_steps_project_typed_evidence
11.00s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
10.19s call     tests/fakey/test_pipe_e2e.py::test_fresh_named_model_pipe_skips_fork_and_records_model
8.55s call     tests/fakey/test_retry_pipeline_e2e.py::test_retryable_failure_then_success_records_lifecycle_and_nudge
8.22s call     tests/fakey/test_retry_pipeline_e2e.py::test_retries_exhausted_raises_after_snapshotting_terminal_attempt
8.00s call     tests/fakey/test_retry_pipeline_e2e.py::test_fallback_switches_the_real_subprocess_model
7.53s call     tests/pager/test_body_widget.py::test_opening_a_50k_line_document_paints_at_most_two_viewports
7.32s call     tests/test_gemini_active_surface_guard.py::test_no_gemini_cli_provider_surface_in_active_tree
6.18s call     tests/ace/tui/test_artifacts_plans_interactions.py::test_plans_pane_navigates_three_document_sections
=========================== short test summary info ============================
FAILED tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms
FAILED tests/test_plan_approval_actions_archive.py::test_neutral_plan_archive_failure_is_retryable_without_duplicate_option_work
FAILED tests/ace/tui/widgets/test_agent_clan_aggregation_async.py::test_collapsed_presence_discovery_enriches_and_reuses_member_artifacts
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_hints.py::test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_hints.py::test_session_collapsed_detached_macro_skips_markers
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.COLLAPSED-overrides0]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides1]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.FULLY_EXPANDED-overrides2]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.EXHAUSTIVE-overrides3]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides4]
FAILED tests/ace/tui/widgets/test_agent_prompt_semantic.py::test_agent_macro_and_prompt_receive_roles_replies_do_not
FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers
FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_collapsed_detached_raw_prompt_skips_markers
FAILED tests/test_plan_gates_action_api.py::test_plan_action_api_executes_selected_approval_options
FAILED tests/test_plan_gates_action_api.py::test_plan_action_api_filters_coder_options_for_commit_preset
FAILED tests/test_plan_gates_execution.py::test_shared_host_executor_handles_feedback_rejection_and_races
FAILED tests/test_finalizers_discard_guard_before_head.py::test_post_dispatch_foreign_race_on_external_is_exempt
FAILED tests/test_bead/test_claimed_status.py::test_default_list_includes_claimed_with_shared_glyph
FAILED tests/test_gate_cli_answer_detach.py::test_ordinary_gate_detaches_when_explicitly_asked
FAILED tests/main/test_bead_fast_path.py::test_fast_path_guards_mutations_but_not_reads
FAILED tests/main/test_bead_fast_path.py::test_fast_path_refuses_unsafe_resolved_location_before_rust
FAILED tests/main/test_bead_fast_path.py::test_fast_path_refuses_mutation_from_plain_checkout_sidecar_record
===== 22 failed, 7359 passed, 4 skipped, 55 warnings in 820.22s (0:13:40) ======
error: Recipe `test-scoped` failed on line 524 with exit code 1
error: Recipe `check` failed on line 774 with exit code 1
failed  exit=1  duration=1492075ms
unattrib  1m 12s
triage lint (symvision): 51 KNOWN continued
triage test (scoped): 11 KNOWN 7 NEW stopped
NEW test (scoped): FAILED tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_agent_prompt_semantic.py::test_agent_macro_and_prompt_receive_roles_replies_do_not — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_bead/test_claimed_status.py::test_default_list_includes_claimed_with_shared_glyph — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_gate_cli_answer_detach.py::test_ordinary_gate_detaches_when_explicitly_asked — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_plan_approval_actions_archive.py::test_neutral_plan_archive_failure_is_retryable_without_duplicate_option_work — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_finalizers_discard_guard_before_head.py::test_post_dispatch_foreign_race_on_external_is_exempt — recorded evidence; no owner
KNOWN lint (symvision): ParityIssue in src/sase/instructions/parity.py — witness 680ab14d27d6e8ddbd8b92a109443aa7; no owner
KNOWN lint (symvision): ParityReport in src/sase/instructions/parity.py — witness 680ab14d27d6e8ddbd8b92a109443aa7; no owner
KNOWN lint (symvision): staged_sdd_files in src/sase/sdd/_commit_store.py — witness 680ab14d27d6e8ddbd8b92a109443aa7; no owner
verdict: new_failures — 7 NEW, 62 KNOWN; exit 1

