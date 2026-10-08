# Chat History - ace-run (sase-1hi.10.2--mon-0)

- **TIMESTAMP:** 2026-10-08 08:10:57 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1hi.10.2--mon-0

## Prompt

sase monitor start --command 'sase tool run check' --reason 'finish check (joined run)'

## Response

sase tool run 6aa89307e436758279e81fc123358df2
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
test selection escalated to the full suite (rules: core-identity-changed); 4963 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, xdist-3.8.0, mock-3.15.1, hypothesis-6.168.0, asyncio-1.4.0, inline-snapshot-0.35.4
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 7/7 workers
7 workers [53521 items]

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
.............F.......................................................... [  1%]
.................................F...................................... [  1%]
........................................................................ [  2%]
....................s................................................... [  2%]
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
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
....................................................s................... [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
.........................................s.............................. [  5%]
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
.................................................F...................... [  7%]
...........s............................................................ [  8%]
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
........................................................................ [ 11%]
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
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
...........................................ss.s..ss..................... [ 14%]
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
..............F......................................................... [ 15%]
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
...........................................F............................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
......s................................................................. [ 17%]
........................................................................ [ 18%]
......................................F................................. [ 18%]
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
........................................................................ [ 23%]
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
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
..........................s............................................. [ 25%]
........................................................................ [ 25%]
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
...............................F........................................ [ 30%]
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
........................................................................ [ 31%]
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
........................................................................ [ 34%]
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
...............................s........................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
.........F........s..................................................... [ 39%]
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
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
.................................................F...................... [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
.....................F.................................................. [ 47%]
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
........................................................................ [ 48%]
........................................................................ [ 49%]
............................................................s........... [ 49%]
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
.........................s.............................................. [ 51%]
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
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
.......F................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
..................ssss.................................................. [ 54%]
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
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
......................F....F...........................................F [ 58%]
......F.......F......................................................... [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
.........F.............................................................. [ 59%]
................................................................F....... [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
..............................F......................................... [ 60%]
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
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
..........................................................F............. [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
....F................................................................... [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
..................................................................F..... [ 64%]
........................................................................ [ 64%]
..............................................F....F.................... [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
....................................................ss.sss.............. [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
............................................s........................... [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
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
......................................F................................. [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................s............................... [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
.................F....F................................................. [ 72%]
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
......................................................FF................ [ 78%]
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
........................................................................ [ 80%]
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
....F................F...........F...................................... [ 83%]
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
........................................................................ [ 85%]
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
...................................................................s.... [ 87%]
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
................................................s........ss............. [ 90%]
........................................................................ [ 90%]
.....................................................................F.. [ 90%]
........................................................................ [ 90%]
.............F......F............F.FF.F.F............................... [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
..........F..F.......................................................... [ 91%]
........................................................................ [ 91%]
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
........................................................................ [ 94%]
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
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
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
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
.........................                                                [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <function gc_cumulative_time.<locals>.gc_callback at 0x72b6f4b04040>

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 497, in gc_callback
    now = _perf_counter()
          ^^^^^^^^^^^^^^^
KeyboardInterrupt

Enable tracemalloc to get traceback where the object was allocated.
See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________ test_candidates_fast_path_child_cpu_budget[snippet] ______________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw4/test_candidates_fast_path_chil0')
kind = 'snippet'

    @pytest.mark.parametrize("kind", _SHIPPED_KINDS)
    def test_candidates_fast_path_child_cpu_budget(tmp_path: Path, kind: str) -> None:
        timings_seconds: list[float] = []
        for _ in range(2):
            result, cpu_seconds = _run_probe_with_cpu_seconds(tmp_path, kinds=(kind,))
            timings_seconds.append(cpu_seconds)
            assert result.returncode == 0, result.stderr + result.stdout
    
        best_ms = min(timings_seconds) * 1000
>       assert best_ms < _CPU_BUDGET_MS, (kind, timings_seconds, _CPU_BUDGET_MS)
E       AssertionError: ('snippet', [0.27857599999999927, 0.3069589999999991], 250.0)
E       assert 278.5759999999993 < 250.0

tests/main/test_completion_candidates_contract.py:162: AssertionError
___________ test_full_cluster_reads_label_chip_separator_label_chip ____________
[gw2] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    async def test_full_cluster_reads_label_chip_separator_label_chip() -> None:
        async with AcePage() as page:
            bar = await _mounted_bar(page)
            bar.apply_launch_context(_state())
            await page.pause()
    
            assert bar.density == "full"
>           assert _bar_plain(bar) == "model: o3@high · project: +sase"
E           AssertionError: assert 'model: opus@xhigh' == 'model: o3@hi...roject: +sase'
E             
E             - model: o3@high · project: +sase
E             + model: opus@xhigh

tests/ace/tui/test_launch_context_bar.py:141: AssertionError
____________ test_post_dispatch_foreign_race_on_external_is_exempt _____________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

instance = ConfiguredFinalizerInstance(instance_id='commit', provider_ref='builtin@commit', after=(), max_attempts=2, refusal='fail', config={}, provenance={'use': FinalizerFieldProvenance(layer='test', path=None)})
context = FinalizerExecutionContext(artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_post_dispatch_...al object at 0x7bd7f903d280>, tracker=<sase.finalizers.status_summary.FinalizerStatusTracker object at 0x7bd7f8e7eff0>)
ledger = InstanceLedger(instance_id='commit', max_attempts=2, consumed=1, next_attempt=2, attempts=[FinalizerAttemptWire(attemp...based HEAD.', severity='error', instance_id='commit', attempt=1)], refusal_reason=None, deferral=None, status='failed')
journal = <sase.finalizers.progress.ProgressJournal object at 0x7bd7f903d280>
provider = <MagicMock id='136167525723040'>
invoke_result = InvokeResult(content='done', usage=None), model_tier = 'large'
suppress_output = True, model_override = None, options = None
artifacts_dir = '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_post_dispatch_foreign_rac0/artifacts'
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

repo = DirtyRepo(name='research', path='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_post_dispatch_foreign_rac0/other', changed_files=('README.md',), kind='external')
context = FinalizerExecutionContext(artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_post_dispatch_...al object at 0x7bd7f903d280>, tracker=<sase.finalizers.status_summary.FinalizerStatusTracker object at 0x7bd7f8e7eff0>)
provider = <MagicMock id='136167525723040'>
invoke_result = InvokeResult(content='done\n\nrepaired', usage=None)
attempts = [FinalizerAttemptWire(attempt=1, status='failed', diagnostic_code='commit_conflict')]
evidence = [FinalizerOutcomeEvidenceWire(kind='cwd', value='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_post_d...eabd238470a85c38'), FinalizerOutcomeEvidenceWire(kind='commit_tree', value='4590793a8b2cc88f6bbbd7a7e10bcea90c66b93f')]
instance_id = 'commit'
git_changed_files_fn = <function git_changed_files at 0x7bd8265fff60>
git_head_commit_id_fn = <function git_head_commit_id at 0x7bd82662c2c0>
git_unpushed_records_fn = <function _default_unpushed_records at 0x7bd825ee59e0>

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
E             1002932fef1a commit dirty payload
E           Run `sase stitch create --resume` to publish the rebased HEAD.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/commit_repair_conflict.py:354: BuiltinCommitFinalizerError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_post_dispatch_foreign_rac0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7bd7f903cc80>

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
context = FinalizerExecutionContext(artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_post_dispatch_...al object at 0x7bd7f903d280>, tracker=<sase.finalizers.status_summary.FinalizerStatusTracker object at 0x7bd7f8e7eff0>)
ledger = InstanceLedger(instance_id='commit', max_attempts=2, consumed=1, next_attempt=2, attempts=[FinalizerAttemptWire(attemp...based HEAD.', severity='error', instance_id='commit', attempt=1)], refusal_reason=None, deferral=None, status='failed')
journal = <sase.finalizers.progress.ProgressJournal object at 0x7bd7f903d280>
provider = <MagicMock id='136167525723040'>
invoke_result = InvokeResult(content='done', usage=None), model_tier = 'large'
suppress_output = True, model_override = None, options = None
artifacts_dir = '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_post_dispatch_foreign_rac0/artifacts'
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
E                 1002932fef1a commit dirty payload
E               Run `sase stitch create --resume` to publish the rebased HEAD.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/finalizers/controller_cycle.py:281: BuiltinCommitFinalizerError
------------------------------ Captured log call -------------------------------
WARNING  sase.llm_provider._instruction_boundary:_instruction_boundary.py:348 instruction shadow render failed: invalid fact provider='unknown'; valid values: agy, claude, codex, fakey, grok, muse, opencode, qwen
_____________ test_default_list_includes_claimed_with_shared_glyph _____________
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

claimed_view = <tests.test_bead.test_claimed_status._ReadView object at 0x70e4d23bcd70>
capsys = <_pytest.capture.CaptureFixture object at 0x70e4d23bf2c0>

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
____________ test_memory_help_marks_primary_command_and_init_alias _____________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    def test_memory_help_marks_primary_command_and_init_alias() -> None:
        """Memory help text points users to the new primary command surface."""
        memory_help = flat_help(parser_for(("sase", "memory")).format_help())
        memory_init_help = flat_help(parser_for(("sase", "memory", "init")).format_help())
        memory_list_help = flat_help(parser_for(("sase", "memory", "list")).format_help())
        memory_read_help = flat_help(parser_for(("sase", "memory", "read")).format_help())
        memory_show_help = flat_help(parser_for(("sase", "memory", "show")).format_help())
        memory_log_help = flat_help(parser_for(("sase", "memory", "log")).format_help())
        init_alias_help = flat_help(parser_for(("sase", "init", "memory")).format_help())
        instructions_help = flat_help(parser_for(("sase", "instructions")).format_help())
        instructions_list_help = flat_help(
            parser_for(("sase", "instructions", "list")).format_help()
        )
        instructions_render_help = flat_help(
            parser_for(("sase", "instructions", "render")).format_help()
        )
    
        assert "{list,render,verify}" in instructions_help
        for _flag in (
            "-a, --agent",
            "-f, --fact",
            "-j, --json",
            "-N, --no-cache",
            "-p, --parity",
            "-s, --sections",
        ):
>           assert _flag in instructions_render_help
E           AssertionError: assert '-a, --agent' in 'usage: sase instructions render [-h] [-a NAME] [-f KEY=VALUE] [-j] [-N] [-p] [-s] Render the memory-built instruction...r -f provider=codex -s sase instructions render -a <agent> -j sase instructions render -f mode=export -f provider=grok'

tests/main/test_parser_command_help.py:275: AssertionError
______________ test_ordinary_gate_detaches_when_explicitly_asked _______________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7bd7efca4a40>

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
____________ test_current_source_avoids_stale_shell_concept_phrases ____________
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    def test_current_source_avoids_stale_shell_concept_phrases() -> None:
        findings: list[str] = []
        candidates = [
            *sorted((_ROOT / "src").rglob("*.py")),
            *sorted((_ROOT / "src").rglob("*.json")),
        ]
        for path in candidates:
            relative = path.relative_to(_ROOT)
            if relative in _SRC_STALE_PHRASE_FILE_ALLOWLIST:
                continue
            content = path.read_text(encoding="utf-8").lower()
            for phrase in _SRC_STALE_PHRASES:
                if (
                    phrase in content
                    and (
                        relative.as_posix(),
                        phrase,
                    )
                    not in _SRC_STALE_PHRASE_ALLOWLIST
                ):
                    findings.append(f"{relative}: {phrase}")
    
>       assert findings == []
E       AssertionError: assert ['src/sase/be... agent shell'] == []
E         
E         Left contains one more item: 'src/sase/bead/cli_work_from_plan.py: agent shell'
E         Use -v to get more diff

tests/test_sase_turn_terminology.py:267: AssertionError
________________ test_macro_string_literals_avoid_xprompt_terms ________________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

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
_____________ test_foreground_run_records_context_usage_and_grant ______________
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x72b6f4c34440>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_foreground_run_records_co0')
capsys = <_pytest.capture.CaptureFixture object at 0x72b6d4345970>

    def test_foreground_run_records_context_usage_and_grant(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        _clean_env(monkeypatch, tmp_path)
        _agent_env(monkeypatch)
        assert _run_snippet() == 0
        capsys.readouterr()
        shown = tool_run_show(_latest_run_id())
        demand = shown["run"].get("demand")
        assert isinstance(demand, dict)
        assert demand.get("context") == {
            "provider": "pytest-provider",
            "sync_ceiling_seconds": 600,
            "sync_soft_ceiling_seconds": 300,
        }
        usage = demand.get("usage")
        assert isinstance(usage, dict)
        assert usage["cpu_user_ms"] > 0
        assert usage["max_process_rss_kib"] > 0
        assert usage["tree_rss_samples"] >= 1
>       assert usage["peak_tree_rss_kib"] > 0
E       assert 0 > 0

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/tool/test_demand_runs.py:261: AssertionError
___________ test_clear_preserves_cursor_and_requests_agents_refresh ____________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7bd7f8af0a40>

    async def test_clear_preserves_cursor_and_requests_agents_refresh(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_alias_views(
            monkeypatch,
            [
                make_alias_view("default", "default"),
                make_alias_view(
                    "plain", "user", configured=True, configured_source="custom"
                ),
            ],
        )
        _patch_snapshot(monkeypatch, _snapshot(override=_override()))
        monkeypatch.setattr(ModelsPanel, "_clear_runner_limit_override", lambda self: True)
    
        app = _RefreshingModelsPanelTestApp()
        async with app.run_test() as pilot:
            panel = ModelsPanel()
            pilot.app.push_screen(panel)
            await pilot.pause()
>           _highlight_row(panel, "plain")

tests/test_models_panel_runner_limit.py:292: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/test_models_panel_runner_limit.py:90: in _highlight_row
    panel._set_highlighted_index(option_list, option_list.get_option_index(row_id))
                                              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.12/site-packages/textual/widgets/_option_list.py:460: in get_option_index
    option = self.get_option(option_id)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = OptionList(id='models-panel-list'), option_id = 'plain'

    def get_option(self, option_id: str) -> Option:
        """Get the option with the given ID.
    
        Args:
            option_id: The ID of the option to get.
    
        Returns:
            The option with the ID.
    
        Raises:
            OptionDoesNotExist: If no option has the given ID.
        """
        try:
            return self._id_to_option[option_id]
        except KeyError:
>           raise OptionDoesNotExist(
                f"There is no option with an ID of {option_id!r}"
            ) from None
E           textual.widgets._option_list.OptionDoesNotExist: There is no option with an ID of 'plain'

.venv/lib/python3.12/site-packages/textual/widgets/_option_list.py:444: OptionDoesNotExist
_ test_neutral_plan_archive_failure_is_retryable_without_duplicate_option_work _
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

gate_home = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_neutral_plan_archive_fail0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7bd81c18ca10>

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
________ TestAgentRawPromptRendering.test_done_agent_renders_raw_prompt ________
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt.TestAgentRawPromptRendering object at 0x72b6e8bf8ef0>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_done_agent_renders_raw_pr0')

    def test_done_agent_renders_raw_prompt(self, tmp_path: Path) -> None:
        panel = FakePromptPanel()
        agent = make_artifact_agent(tmp_path, status="DONE")
    
        panel.update_display(agent)
    
        plain = plain_of(panel.captured[-1])
        assert "AGENT RAW PROMPT" in plain
        assert "Launch from @src/raw.py" in plain
        assert "AGENT PROMPT" in plain
        assert "AGENT CHAT" in plain
        rendered = panel.captured[-1]
        assert_rendered_section_is_compact(
            rendered,
            "AGENT RAW PROMPT",
            "Launch from @src/raw.py",
        )
>       assert_rendered_section_is_compact(
            rendered,
            "AGENT PROMPT",
            "Expanded prompt body",
        )

tests/ace/tui/widgets/test_agent_display_raw_prompt.py:44: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

renderable = <rich.console.Group object at 0x72b6f4422150>
heading = 'AGENT PROMPT', first_content_prefix = 'Expanded prompt body'
widths = (60, 120)

    def assert_rendered_section_is_compact(
        renderable: object,
        heading: str,
        first_content_prefix: str,
        *,
        widths: tuple[int, ...] = (60, 120),
    ) -> None:
        """Assert compact section spacing after Rich renders Group boundaries."""
        for width in widths:
            output = StringIO()
            console = Console(file=output, width=width, color_system=None)
            console.print(renderable, end="")
            lines = output.getvalue().splitlines()
            heading_index = lines.index(heading)
>           assert lines[heading_index + 1].startswith(first_content_prefix)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E           AssertionError

tests/ace/tui/widgets/_agent_display_metadata_helpers.py:102: AssertionError
_ TestAgentRawPromptRendering.test_agent_prompt_and_chat_use_logical_project_name _
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt.TestAgentRawPromptRendering object at 0x72b6e8bfa0f0>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_agent_prompt_and_chat_use0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x72b6f3f5c590>

    def test_agent_prompt_and_chat_use_logical_project_name(
        self,
        tmp_path: Path,
        monkeypatch,
    ) -> None:
        monkeypatch.setattr("sase.project_aliases._vcs_workflow_names", lambda: {"gh"})
        monkeypatch.setattr(
            pdn,
            "_project_display_name_map_cached",
            lambda *_args, **_kwargs: {"gh_acme__widgets": "widgets"},
        )
        panel = FakePromptPanel()
        agent = make_artifact_agent(tmp_path, status="DONE")
        Path(agent.artifacts_dir, "01_prompt.md").write_text(
            "Prompt says #gh:gh_acme__widgets inspect.\n",
            encoding="utf-8",
        )
        Path(agent.response_path).write_text(
            "Response echoes #gh:gh_acme__widgets now.\n",
            encoding="utf-8",
        )
    
        panel.update_display(agent)
    
        plain = plain_of(panel.captured[-1])
>       assert "Prompt says #gh:widgets inspect." in plain
E       AssertionError: assert 'Prompt says #gh:widgets inspect.' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...─────────────────────────\n\nAGENT PROMPT\n\nLaunch from @src/raw.py\nAGENT CHAT\n\nResponse echoes #gh:widgets now.\n'

tests/ace/tui/widgets/test_agent_display_raw_prompt.py:92: AssertionError
_ TestAgentRawPromptHintMode.test_hint_mode_prompt_and_chat_use_logical_project_name _
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt_hints.TestAgentRawPromptHintMode object at 0x72b6e8bc33b0>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_prompt_and_chat0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x72b6f365a840>

    def test_hint_mode_prompt_and_chat_use_logical_project_name(
        self,
        tmp_path: Path,
        monkeypatch,
    ) -> None:
        monkeypatch.setattr("sase.project_aliases._vcs_workflow_names", lambda: {"gh"})
        monkeypatch.setattr(
            pdn,
            "_project_display_name_map_cached",
            lambda *_args, **_kwargs: {"gh_acme__widgets": "widgets"},
        )
        panel = FakePromptPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            raw_prompt="#gh:gh_acme__widgets raw",
        )
        Path(agent.artifacts_dir, "01_prompt.md").write_text(
            "#gh:gh_acme__widgets prompt\n",
            encoding="utf-8",
        )
        Path(agent.response_path).write_text(
            "#gh:gh_acme__widgets response\n",
            encoding="utf-8",
        )
    
        panel.update_display_with_hints(agent)
    
        plain = plain_of(panel.captured[-1])
        assert "#gh:widgets raw" in plain
>       assert "#gh:widgets prompt" in plain
E       AssertionError: assert '#gh:widgets prompt' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...─────────────────────────────────────────────\n\nAGENT PROMPT\n#gh:widgets raw\n\nAGENT CHAT\n#gh:widgets response\n\n'

tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py:62: AssertionError
_ TestAgentRawPromptHintMode.test_hint_mode_renders_raw_prompt_for_terminal_agent _
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt_hints.TestAgentRawPromptHintMode object at 0x72b6e8bf9130>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_renders_raw_pro0')

    def test_hint_mode_renders_raw_prompt_for_terminal_agent(
        self,
        tmp_path: Path,
    ) -> None:
        workspace_dir = tmp_path / "workspace"
        workspace_dir.mkdir()
        panel = FakePromptPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace_dir),
        )
    
        result = panel.update_display_with_hints(agent)
    
        rendered = panel.captured[-1]
        plain = plain_of(rendered)
        assert "AGENT RAW PROMPT" in plain
        assert "[1] @src/raw.py" in plain
        assert result.file_hints[1] == str(workspace_dir / "src/raw.py")
        assert_logical_section_is_compact(
            rendered,
            "AGENT RAW PROMPT",
            "Launch from [1] @src/raw.py",
        )
>       assert_logical_section_is_compact(
            rendered,
            "AGENT PROMPT",
            "Expanded prompt body",
        )

tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py:121: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

renderable = <rich.console.Group object at 0x72b6f3f5df40>
heading = 'AGENT PROMPT', first_content_prefix = 'Expanded prompt body'

    def assert_logical_section_is_compact(
        renderable: Any,
        heading: str,
        first_content_prefix: str,
    ) -> None:
        """Assert that logical text has no spacer after a section heading."""
        plain = _logical_plain(renderable)
        lines = plain.splitlines()
        heading_index = lines.index(heading)
>       assert lines[heading_index + 1].startswith(first_content_prefix)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/widgets/_agent_display_metadata_helpers.py:84: AssertionError
_ TestAgentRawPromptHintMode.test_hint_mode_keeps_typed_artifact_refs_semantic _
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt_hints.TestAgentRawPromptHintMode object at 0x72b6e8bc8ec0>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_typed_art0')

    def test_hint_mode_keeps_typed_artifact_refs_semantic(
        self,
        tmp_path: Path,
    ) -> None:
        workspace_dir = tmp_path / "workspace"
        workspace_dir.mkdir()
        panel = FakePromptPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace_dir),
            raw_prompt="#work(@plans:202608/design.md#L12) and @src/raw.py",
        )
    
        result = panel.update_display_with_hints(agent)
    
        rendered = _header_text(panel.captured[-1])
        assert "#work(@plans:202608/design.md#L12) and [1] @src/raw.py" in (
            rendered.plain
        )
>       assert result.file_hints == {1: str(workspace_dir / "src/raw.py")}
E       AssertionError: assert {1: '/var/tmp...e/src/raw.py'} == {1: '/var/tmp...e/src/raw.py'}
E         
E         Omitting 1 identical items, use -vv to show
E         Left contains 2 more items:
E         {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_typed_art0/workspace/202608/design.md',
E          3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_typed_art0/workspace/src/raw.py'}
E         Use -v to get more diff

tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py:186: AssertionError
_______________ test_hint_mode_keeps_collapsed_header_unchanged ________________
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0')

    async def test_hint_mode_keeps_collapsed_header_unchanged(tmp_path: Any) -> None:
        from pathlib import Path
    
        from tests.ace.tui.widgets._agent_display_helpers import make_artifact_agent
    
        workspace = tmp_path / "workspace"
        (workspace / "src").mkdir(parents=True)
        (workspace / "src" / "example.py").write_text("", encoding="utf-8")
        (workspace / "src" / "body.py").write_text("", encoding="utf-8")
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            raw_prompt="Read @src/example.py",
            workspace_dir=str(workspace),
        )
        Path(str(agent.response_path)).write_text("See src/body.py\n", encoding="utf-8")
        app = DetailApp()
        async with app.run_test(size=(80, 24)) as pilot:
            detail = app.query_one("#agent-detail-panel", AgentDetail)
            await show_agent_full(detail, agent, pilot)
            panel = header_panel(detail)
            assert not panel.is_expanded
            pre_text = header_text(panel)
            pre_rows = panel.rendered_row_count
            result = detail.update_display_with_hints(agent)
            await pilot.pause()
            assert not panel.is_expanded
            assert header_text(panel) == pre_text
            assert panel.rendered_row_count == pre_rows
            assert "[1]" not in header_text(panel)
>           assert str(workspace / "src/example.py") not in result.file_hints.values()
E           AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/...y', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/body.py'])
E            +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace') / 'src/example.py'))
E            +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/...y', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/body.py']) = <built-in method values of dict object at 0x72b6f3945c40>()
E            +    where <built-in method values of dict object at 0x72b6f3945c40> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/example.py', 2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/body.py'}.values
E            +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/example.py', 2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collapsed0/workspace/src/body.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hint_mode_keeps_collaps... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints

tests/ace/tui/widgets/test_agent_header_panel_basic.py:203: AssertionError
_______ test_collapsed_preview_shows_quote_bar_and_body_omits_raw_prompt _______
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_preview_shows_q0')

    async def test_collapsed_preview_shows_quote_bar_and_body_omits_raw_prompt(
        tmp_path: Any,
    ) -> None:
        app = DetailApp()
        async with app.run_test(size=(80, 24)) as pilot:
            detail = app.query_one("#agent-detail-panel", AgentDetail)
            await show_agent_full(
                detail, artifact_agent(tmp_path, "a", LONG_RAW_PROMPT), pilot
            )
            panel = header_panel(detail)
            assert not panel.is_expanded
            _assert_card(panel)
            assert "rendering the AGENT RAW PROMPT" in header_text(panel)
            prompt = detail.query_one("#agent-prompt-panel", AgentPromptPanel)
            body = renderable_to_text(prompt.content) or ""
>           assert "AGENT RAW PROMPT" not in body
E           AssertionError: assert 'AGENT RAW PROMPT' not in 'AGENT PROMP...esponse body'
E             
E             'AGENT RAW PROMPT' is contained here:
E               ering the AGENT RAW PROMPT section in the sticky header above the agent data deck panel? Make 
E             ?           ++++++++++++++++
E               sure that we provide a good preview of the contents in this section.                                                    
E                                                                                                                                       
E               - first list item explains the quote bar                                                                                ...
E             
E             ...Full output truncated (8 lines hidden), use '-vv' to show

tests/ace/tui/widgets/test_agent_header_panel_preview.py:76: AssertionError
_________ test_bottom_pinned_body_stays_pinned_across_row_count_change _________
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_bottom_pinned_body_stays_0')

    async def test_bottom_pinned_body_stays_pinned_across_row_count_change(
        tmp_path: Any,
    ) -> None:
        app = DetailApp()
        async with app.run_test(size=(80, 24)) as pilot:
            detail = app.query_one("#agent-detail-panel", AgentDetail)
            await show_agent_full(
                detail, artifact_agent(tmp_path, "a", _SHORT_RAW_PROMPT), pilot
            )
            panel = header_panel(detail)
            before = panel.rendered_row_count
            main_view = detail.deck_area.panel(0).main_view
            main_view.pin_to_bottom()
            assert bool(main_view.is_pinned_to_bottom) is True
            await show_agent_full(
                detail, artifact_agent(tmp_path, "b", LONG_RAW_PROMPT), pilot
            )
            assert panel.rendered_row_count != before
>           assert bool(main_view.is_pinned_to_bottom) is True
E           assert False is True
E            +  where False = bool(False)
E            +    where False = MainDeckView().is_pinned_to_bottom

tests/ace/tui/widgets/test_agent_header_panel_preview.py:359: AssertionError
___________ test_plan_action_api_executes_selected_approval_options ____________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

gate_home = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_plan_action_api_executes_0')
stub_host_plan_archive = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_plan_action_api_executes_0/host-archived-plan.md')

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
E         At index 0 diff: {'id': 'commit', 'result': {'action': 'approve', 'commit_plan': True, 'run_coder': False, '_gate_source': 'plan_response', '_gate_caller': 'human', 'decided_by': 'reviewer', 'decided_via': 'tui', 'plan_archive_owner': 'host', 'plan_archive_state': 'archived', 'saved_plan_path': '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_plan_action_api_executes_0/host-archived-plan.md', 'plan_archive_protocol': 'host_v2', 'plan_archive_ref': 'plan:202608/host-archived-plan.md'}} != {'id': 'commit', 'result': {'action': 'approve', 'commit_plan': True...
E         
E         ...Full output truncated (2 lines hidden), use '-vv' to show

tests/test_plan_gates_action_api.py:54: AssertionError
_________ test_plan_action_api_filters_coder_options_for_commit_preset _________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

gate_home = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_plan_action_api_filters_c0')
stub_host_plan_archive = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_plan_action_api_filters_c0/host-archived-plan.md')

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
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

gate_home = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_shared_host_executor_hand0')

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
___________ test_agent_macro_and_prompt_receive_roles_replies_do_not ___________
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_agent_macro_and_prompt_re0')

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
_________ test_agent_session_pinned_and_workflow_authored_prompt_paths _________
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_agent_session_pinned_and_0')

    def test_agent_session_pinned_and_workflow_authored_prompt_paths(
        tmp_path: Path,
    ) -> None:
        panel = FakePromptPanel()
        source = "Ask Agent Clan to inspect sase-core"
        glossary = dynamic_catalog_for_term(tmp_path, "Agent Clan")
        repo = dynamic_catalog_for_identifier(tmp_path, "sase-core")
        install_panel_semantics(panel, glossary=glossary, repo=repo)
    
        root, _child = make_agent_session(tmp_path)
        Path(root.artifacts_dir, "raw_prompt.md").write_text(
            "#git:sase Ask Agent Clan\n",
            encoding="utf-8",
        )
        Path(root.artifacts_dir, "01_prompt.md").write_text(source + "\n", encoding="utf-8")
        panel.update_display(root)
        agent_session_plain = plain_of(panel.captured[-1])
        assert "AGENT RAW PROMPT" in agent_session_plain
        assert "Agent Clan" in agent_session_plain
        agent_session_header = _header_text(panel.captured[-1])
        assert _has_role_underline(_styles_at(agent_session_header, "Agent Clan"))
    
        pinned = FakePromptPanel()
        install_panel_semantics(pinned, glossary=glossary, repo=repo)
        agent = make_artifact_agent(tmp_path, status="FAILED")
        Path(agent.artifacts_dir, "01_prompt.md").write_text(
            source + "\n", encoding="utf-8"
        )
    
        agent.attempt_history = [
            AttemptRecord(
                attempt_number=1,
                status="failed",
                start_epoch=1.0,
                end_epoch=2.0,
                model=None,
                used_fallback=False,
                error_snippet="err",
                error_full="",
                live_reply_path="/nonexistent.md",
                timestamps_path="/nonexistent.jsonl",
            )
        ]
        pinned.attempt_pinned_number = 1
        pinned._render_attempt_pinned(agent, 1)
        pinned_plain = plain_of(pinned.captured[-1])
        assert "AGENT PROMPT" in pinned_plain
>       assert "Agent Clan" in pinned_plain
E       AssertionError: assert 'Agent Clan' in 'Viewing Attempt 1 of 1 · started 19:00:01 · failed at 19:00:02\n\nATTEMPT ERROR\n\nerr\n\n\n──────────────────────────────────────────────────\n\n\nAGENT PROMPT\n\nLaunch from @src/raw.py\nATTEMPT 1 REPLY\n\n(no partial reply captured)\n'

tests/ace/tui/widgets/test_agent_prompt_semantic.py:297: AssertionError
_______________________ test_verify_help_documents_flags _______________________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    def test_verify_help_documents_flags() -> None:
        """``verify -h`` names every option and the reporting contract."""
        help_text = flat_help(parser_for(("sase", "instructions", "verify")).format_help())
        for flag in (
            "-a, --agent",
            "-c, --coverage",
            "-H, --helpers",
            "-j, --json",
            "-n, --limit",
            "-p, --provider",
            "-s, --since",
            "-u, --until",
        ):
>           assert flag in help_text
E           AssertionError: assert '-a, --agent' in 'usage: sase instructions verify [-h] [-a NAME] [-c] [-H] [-j] [-n N] [-p PROVIDER] [-s WHEN] [-u WHEN] Show what each...rify sase instructions verify -n 20 --since 7d sase instructions verify -p claude -H sase instructions verify -j -n 50'

tests/instructions/test_verify_cli.py:101: AssertionError
________ test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers ________
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hinted_raw_prompt_moves_t0')

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
E         {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_hinted_raw_prompt_moves_t0/workspace/src/example.py'}
E         Use -v to get more diff

tests/ace/tui/widgets/test_identity_header_raw_prompt.py:127: AssertionError
_______________ test_collapsed_detached_raw_prompt_skips_markers _______________
[gw5] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_detached_raw_pr0')

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
E       AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_detached_raw_pr0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_detached_raw_pr0/workspace/src/example.py'])
E        +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_detached_raw_pr0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_detached_raw_pr0/workspace') / 'src/example.py'))
E        +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_detached_raw_pr0/workspace/src/example.py']) = <built-in method values of dict object at 0x72b6c9695900>()
E        +    where <built-in method values of dict object at 0x72b6c9695900> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_detached_raw_pr0/workspace/src/example.py'}.values
E        +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_detached_raw_pr0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw5/test_collapsed_detached_raw_... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints

tests/ace/tui/widgets/test_identity_header_raw_prompt.py:153: AssertionError
_____________ test_lane_following_narrates_epic_progress_and_since _____________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    def test_lane_following_narrates_epic_progress_and_since() -> None:
        agent = _waiting_agent(wait_epic_follows=[_follow_view()])
        line = _agents_line(
            agent,
            wait_bead_statuses=(("sase-7k", "in_progress"),),
            epic_follow_progress={"sase-7k": _EpicFollowProgress(2, 5)},
        )
    
        assert "planner ✓" in line
        assert "↪ sase-7k ◐ in progress" in line
        assert "2/5 phases" in line
>       assert f"since {_SINCE_TEXT}" in line
E       AssertionError: assert 'since 14:32' in 'Wait: [agents] planner ✓ ↪ sase-7k ◐ in progress · 2/5 phases · since 10:32'

tests/ace/tui/test_agent_wait_epic_follow_tui.py:169: AssertionError
____________________ test_lane_launching_reads_pending_text ____________________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    def test_lane_launching_reads_pending_text() -> None:
        agent = _waiting_agent(
            wait_epic_follows=[_follow_view(state="launching", epic_ids=())],
        )
        line = _agents_line(agent)
    
        assert "↪ epic launching…" in line
>       assert f"since {_SINCE_TEXT}" in line
E       AssertionError: assert 'since 14:32' in 'Wait: [agents] planner ✓ ↪ epic launching… · since 10:32'

tests/ace/tui/test_agent_wait_epic_follow_tui.py:179: AssertionError
________________ test_fast_path_guards_mutations_but_not_reads _________________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_fast_path_guards_mutation0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7bd7ee2ab590>

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
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_fast_path_refuses_unsafe_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7bd7fd5b2de0>

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
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_fast_path_refuses_mutatio0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7bd7efd0f6e0>
capsys = <_pytest.capture.CaptureFixture object at 0x7bd81c16e270>

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
____ test_collapsed_presence_discovery_enriches_and_reuses_member_artifacts ____
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_collapsed_presence_discov0')

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
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_content_hin0')

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
E         At index 0 diff: {'/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt', '/var/tmp/sase-3573d744/pytest-of-brya...
E         
E         ...Full output truncated (2 lines hidden), use '-vv' to show

tests/ace/tui/widgets/test_agent_display_agent_session_hints.py:168: AssertionError
_____________ test_session_collapsed_detached_macro_skips_markers ______________
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_session_collapsed_detache0')

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
E       AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_session_collapsed_detache0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_session_collapsed_detache0/workspace/src/example.py'])
E        +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_session_collapsed_detache0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_session_collapsed_detache0/workspace') / 'src/example.py'))
E        +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_session_collapsed_detache0/workspace/src/example.py']) = <built-in method values of dict object at 0x70e4b31feb00>()
E        +    where <built-in method values of dict object at 0x70e4b31feb00> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_session_collapsed_detache0/workspace/src/example.py'}.values
E        +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_session_collapsed_detache0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_session_collapsed_detac... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints

tests/ace/tui/widgets/test_agent_display_agent_session_hints.py:290: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.COLLAPSED-overrides0] _
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_conversatio0')
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
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_conversatio1')
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
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_conversatio2')
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
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_conversatio3')
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
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_agent_session_conversatio4')
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
_____________ test_repeat_hint_render_reuses_result_and_renderable _____________
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_repeat_hint_render_reuses0')

    def test_repeat_hint_render_reuses_result_and_renderable(tmp_path: Path) -> None:
        workspace = tmp_path / "workspace"
        workspace.mkdir()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
        )
        Path(agent.response_path or "").write_text(
            "Open src/reused.py\n",
            encoding="utf-8",
        )
        panel = FakePromptPanel()
        cache_detail_header_summary(panel, agent, DetailHeaderSummary())
    
        first = panel.update_display_with_hints(agent)
        first_renderable = panel.captured[-1]
        second = panel.update_display_with_hints(agent)
    
        assert first is second
        assert panel.captured[-1] is first_renderable
        from rich.console import Group
        from sase.ace.tui.widgets.decks.card_part import CardPart
    
        assert isinstance(first_renderable, Group)
        assert any(isinstance(c, CardPart) for c in first_renderable.renderables)
>       assert first.file_hints == {
            1: str(workspace / "src/raw.py"),
            2: str(workspace / "src/reused.py"),
        }
E       AssertionError: assert {1: '/var/tmp...rc/reused.py'} == {1: '/var/tmp...rc/reused.py'}
E         
E         Omitting 1 identical items, use -vv to show
E         Differing items:
E         {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_repeat_hint_render_reuses0/workspace/src/raw.py'} != {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_repeat_hint_render_reuses0/workspace/src/reused.py'}
E         Left contains 1 more item:
E         {3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_repeat_hint_render_reuses0/workspace/src/reused.py'}
E         Use -v to get more diff

tests/ace/tui/widgets/test_agent_display_hint_cache.py:49: AssertionError
__________ test_changed_reply_invalidates_hint_document_and_mappings ___________
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw0/test_changed_reply_invalidates0')

    def test_changed_reply_invalidates_hint_document_and_mappings(tmp_path: Path) -> None:
        workspace = tmp_path / "workspace"
        workspace.mkdir()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
        )
        response_path = Path(agent.response_path or "")
        response_path.write_text("Open src/first.py\n", encoding="utf-8")
        panel = FakePromptPanel()
        cache_detail_header_summary(panel, agent, DetailHeaderSummary())
    
        first = panel.update_display_with_hints(agent)
        first_renderable = panel.captured[-1]
        response_path.write_text(
            "Open src/second-and-longer.py\n",
            encoding="utf-8",
        )
        second = panel.update_display_with_hints(agent)
    
        assert second is not first
        assert panel.captured[-1] is not first_renderable
        assert str(workspace / "src/first.py") not in second.file_hints.values()
        assert str(workspace / "src/second-and-longer.py") in second.file_hints.values()
>       assert "[2] src/second-and-longer.py" in plain_of(panel.captured[-1])
E       AssertionError: assert '[2] src/second-and-longer.py' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...────────────────────\n\nAGENT PROMPT\nLaunch from [2] @src/raw.py\n\nAGENT CHAT\nOpen [3] src/second-and-longer.py\n\n'
E        +  where 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...────────────────────\n\nAGENT PROMPT\nLaunch from [2] @src/raw.py\n\nAGENT CHAT\nOpen [3] src/second-and-longer.py\n\n' = plain_of(<rich.console.Group object at 0x70e4b1113bf0>)

tests/ace/tui/widgets/test_agent_display_hint_cache.py:111: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:130: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

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

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:859: DeprecationWarning: This process (pid=2807652) is multi-threaded, use of fork() may lead to deadlocks in the child.

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

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /usr/lib/python3.12/copy.py:210: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    y = tuple(y)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/keymaps/key_validation.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    return tuple(part.strip() for part in key.split(","))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /usr/lib/python3.12/pathlib.py:357: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    def __init__(self, *args):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_loads_an_unloaded_tail_then_opens_pager
  /usr/lib/python3.12/copy.py:208: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for k, j in zip(x, y):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_K_warns_when_finished_and_confirms_when_running
  /usr/lib/python3.12/copy.py:210: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    y = tuple(y)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/completion/command_line_grammar.py:231: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    result = self._handle.command_help(list(path))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/macro/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=2807513) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

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

tests/completion/test_zsh_smoke.py: 18 warnings
  /usr/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=2807460) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
201.91s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
201.24s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
90.67s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
67.63s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
65.06s teardown tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_other_main_screen_vim_hosts_contain_normal_space
62.35s teardown tests/ace/tui/widgets/test_prompt_tab_focus_steal.py::test_tab_with_focus_on_list_still_stays_on_agents
60.98s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
50.50s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
47.73s call     tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_other_main_screen_vim_hosts_contain_normal_space
42.75s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
36.85s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
35.26s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
33.35s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
31.50s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
30.56s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
28.21s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
27.81s call     tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly
27.62s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
27.50s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
26.52s call     tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_fresh_app_instance_hides_removed_rows
=========================== short test summary info ============================
FAILED tests/main/test_completion_candidates_contract.py::test_candidates_fast_path_child_cpu_budget[snippet]
FAILED tests/ace/tui/test_launch_context_bar.py::test_full_cluster_reads_label_chip_separator_label_chip
FAILED tests/test_finalizers_discard_guard_before_head.py::test_post_dispatch_foreign_race_on_external_is_exempt
FAILED tests/test_bead/test_claimed_status.py::test_default_list_includes_claimed_with_shared_glyph
FAILED tests/main/test_parser_command_help.py::test_memory_help_marks_primary_command_and_init_alias
FAILED tests/test_gate_cli_answer_detach.py::test_ordinary_gate_detaches_when_explicitly_asked
FAILED tests/test_sase_turn_terminology.py::test_current_source_avoids_stale_shell_concept_phrases
FAILED tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms
FAILED tests/tool/test_demand_runs.py::test_foreground_run_records_context_usage_and_grant
FAILED tests/test_models_panel_runner_limit.py::test_clear_preserves_cursor_and_requests_agents_refresh
FAILED tests/test_plan_approval_actions_archive.py::test_neutral_plan_archive_failure_is_retryable_without_duplicate_option_work
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt.py::TestAgentRawPromptRendering::test_done_agent_renders_raw_prompt
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt.py::TestAgentRawPromptRendering::test_agent_prompt_and_chat_use_logical_project_name
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py::TestAgentRawPromptHintMode::test_hint_mode_prompt_and_chat_use_logical_project_name
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py::TestAgentRawPromptHintMode::test_hint_mode_renders_raw_prompt_for_terminal_agent
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py::TestAgentRawPromptHintMode::test_hint_mode_keeps_typed_artifact_refs_semantic
FAILED tests/ace/tui/widgets/test_agent_header_panel_basic.py::test_hint_mode_keeps_collapsed_header_unchanged
FAILED tests/ace/tui/widgets/test_agent_header_panel_preview.py::test_collapsed_preview_shows_quote_bar_and_body_omits_raw_prompt
FAILED tests/ace/tui/widgets/test_agent_header_panel_preview.py::test_bottom_pinned_body_stays_pinned_across_row_count_change
FAILED tests/test_plan_gates_action_api.py::test_plan_action_api_executes_selected_approval_options
FAILED tests/test_plan_gates_action_api.py::test_plan_action_api_filters_coder_options_for_commit_preset
FAILED tests/test_plan_gates_execution.py::test_shared_host_executor_handles_feedback_rejection_and_races
FAILED tests/ace/tui/widgets/test_agent_prompt_semantic.py::test_agent_macro_and_prompt_receive_roles_replies_do_not
FAILED tests/ace/tui/widgets/test_agent_prompt_semantic.py::test_agent_session_pinned_and_workflow_authored_prompt_paths
FAILED tests/instructions/test_verify_cli.py::test_verify_help_documents_flags
FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers
FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_collapsed_detached_raw_prompt_skips_markers
FAILED tests/ace/tui/test_agent_wait_epic_follow_tui.py::test_lane_following_narrates_epic_progress_and_since
FAILED tests/ace/tui/test_agent_wait_epic_follow_tui.py::test_lane_launching_reads_pending_text
FAILED tests/main/test_bead_fast_path.py::test_fast_path_guards_mutations_but_not_reads
FAILED tests/main/test_bead_fast_path.py::test_fast_path_refuses_unsafe_resolved_location_before_rust
FAILED tests/main/test_bead_fast_path.py::test_fast_path_refuses_mutation_from_plain_checkout_sidecar_record
FAILED tests/ace/tui/widgets/test_agent_clan_aggregation_async.py::test_collapsed_presence_discovery_enriches_and_reuses_member_artifacts
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_hints.py::test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_hints.py::test_session_collapsed_detached_macro_skips_markers
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.COLLAPSED-overrides0]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides1]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.FULLY_EXPANDED-overrides2]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.EXHAUSTIVE-overrides3]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides4]
FAILED tests/ace/tui/widgets/test_agent_display_hint_cache.py::test_repeat_hint_render_reuses_result_and_renderable
FAILED tests/ace/tui/widgets/test_agent_display_hint_cache.py::test_changed_reply_invalidates_hint_document_and_mappings
=== 42 failed, 53449 passed, 31 skipped, 119 warnings in 2712.12s (0:45:12) ====
error: Recipe `test-scoped` failed on line 524 with exit code 1
error: Recipe `check` failed on line 774 with exit code 1
failed/1  3463524ms
triage lint (symvision): 51 KNOWN
triage test (scoped): 25 KNOWN 13 NEW
NEW test (scoped): FAILED tests/tool/test_demand_runs.py::test_foreground_run_records_context_usage_and_grant — recorded evidence; no owner
NEW test (scoped): FAILED tests/main/test_bead_fast_path.py::test_fast_path_guards_mutations_but_not_reads — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_sase_turn_terminology.py::test_current_source_avoids_stale_shell_concept_phrases — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_agent_header_panel_preview.py::test_collapsed_preview_shows_quote_bar_and_body_omits_raw_prompt — recorded evidence; no owner
NEW test (scoped): FAILED tests/main/test_completion_candidates_contract.py::test_candidates_fast_path_child_cpu_budget[snippet] — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/test_agent_wait_epic_follow_tui.py::test_lane_launching_reads_pending_text — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_bead/test_claimed_status.py::test_default_list_includes_claimed_with_shared_glyph — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_gate_cli_answer_detach.py::test_ordinary_gate_detaches_when_explicitly_asked — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_plan_gates_action_api.py::test_plan_action_api_executes_selected_approval_options — recorded evidence; no owner
KNOWN lint (symvision): ParityIssue in src/sase/instructions/parity.py — witness 680ab14d27d6e8ddbd8b92a109443aa7; no owner
KNOWN lint (symvision): ParityReport in src/sase/instructions/parity.py — witness 680ab14d27d6e8ddbd8b92a109443aa7; no owner
KNOWN lint (symvision): staged_sdd_files in src/sase/sdd/_commit_store.py — witness 680ab14d27d6e8ddbd8b92a109443aa7; no owner
sase tool show 6aa89307e436758279e81fc123358df2 -l
verdict: new_failures — 13 NEW, 76 KNOWN; exit 1

