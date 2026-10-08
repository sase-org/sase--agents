# Chat History - ace-run (sase-1h7.3--mon)

- **TIMESTAMP:** 2026-10-07 09:13:51 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1h7.3--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'finish check (joined run)'

## Response

sase tool run c2b50e46cc35ae8e1ea45d05b4409148
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
Error: Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!:
  _runs in src/sase/agents_sync/v2_snapshot_io.py
  _runs in src/sase/ace/tui/widgets/decks/final/overview_card.py
error: recipe `_lint-symvision` failed on line 407 with exit code 1
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.35.0 is missing 99 capability(s), and at least one has no containing sase-core release tag yet.
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
{"cache_hit": true, "capabilities": [{"commit": "12e012d", "name": "PromptPredictionCorpus", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "12e012d", "name": "PromptPredictionModel", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "28befcb", "name": "ack_agent_completions", "release": "v0.36.2", "subject": "feat(notifications): store generations, ack API, and lean unread index"}, {"commit": "1e51ff3", "name": "alternation_scan", "release": "v0.36.1", "subject": "feat(alternation): shared scanner, binding, diagnostic, and LSP tokens"}, {"commit": "2f16dc4", "name": "argument_list_continuation_edit", "release": "v0.36.6", "subject": "feat(editor): continue existing macro argument lists"}, {"commit": "7806f58", "name": "attachment_audience_decision", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_canonical_extension", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_object_digest_from_relpath", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "43f744b", "name": "attachment_placement", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "7806f58", "name": "attachment_public_object_relpath", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_scan_file", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_scanner_rules_version", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "43f744b", "name": "attachment_sensitive_path_reason", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "43f744b", "name": "attachment_should_auto_fetch", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "c448ed6", "name": "build_agent_tab_catalog", "release": "v0.36.0", "subject": "feat(agent-tab): core tab model with directive, typed units, and Python bindings"}, {"commit": "c448ed6", "name": "canonicalize_agent_tab_name", "release": "v0.36.0", "subject": "feat(agent-tab): core tab model with directive, typed units, and Python bindings"}, {"commit": "2838c7e", "name": "check_input_value", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "39324ac", "name": "classify_attachment", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "3d406d4", "name": "classify_deferred_prompt_obligation", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "16095fc", "name": "classify_model_value", "release": "v0.36.6", "subject": "feat(macros): add builtin model and effort types with one routing classifier"}, {"commit": "d7f2dbf", "name": "classify_session_manifest_files", "release": "v0.36.5", "subject": "feat(agent-session-manifest): canonical file-set derivation and classification"}, {"commit": "3b27df5", "name": "compare_prose", "release": "v0.36.2", "subject": "feat(prose-diff): add pure sase-core prose_diff module and Python binding"}, {"commit": "39324ac", "name": "compose_note_attachment_text", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "3d406d4", "name": "decide_publication_request_completion", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "a62699b", "name": "editor_snippet_catalog_wire_schema_version", "release": "v0.37.0", "subject": "feat(macros)!: emit canonical macro wires and snippet catalog schema 2"}, {"commit": "1ad57ea", "name": "evaluate_prompt_prediction_replay", "release": "v0.36.1", "subject": "feat(prompt-prediction): add per-point novel coverage and precision to sweep wire"}, {"commit": "33b0250", "name": "goal_card_markdown", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "33b0250", "name": "goal_card_view", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "33b0250", "name": "goal_citation_line", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "d2d9ec7", "name": "goal_fast_path", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "cbe70f6", "name": "goal_ledger_append", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_doctor", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_history", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_init", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_list", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_probe_list", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_show", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_store_schema_version", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_wire_schema_version", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_mint_id", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_projection_refresh", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_projection_status", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "d2d9ec7", "name": "goal_render_card", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "d2d9ec7", "name": "goal_render_list", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "fa39036", "name": "instruction_manifest_wire_schema_version", "release": null, "subject": "feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)"}, {"commit": "3adc01b", "name": "jinja_catalog", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "3adc01b", "name": "jinja_completion", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "3adc01b", "name": "jinja_scope_variables", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "297bc1e", "name": "launch_scratch_liveness_wire_schema_version", "release": "v0.36.0", "subject": "feat(core): launch_scratch_liveness module with procfs probe bindings"}, {"commit": "af5df61", "name": "load_macro_input_type_registry", "release": "v0.37.0", "subject": "feat(core): load plugin input_type registries with resolution, catalog, and LSP wiring"}, {"commit": "0d27dad", "name": "macro_argument_choice_candidates", "release": "v0.36.6", "subject": "feat(macros): carry resolved choice metadata and shared candidates"}, {"commit": "c4444ab", "name": "macro_argument_spans", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "0279de6", "name": "macro_completion_spacer_to_parentheses_edit", "release": "v0.36.6", "subject": "feat(macros): flip emitted wires to macro spellings, rename LSP crate"}, {"commit": "2838c7e", "name": "macro_input_type_catalog", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "0d27dad", "name": "macro_input_type_label", "release": "v0.36.6", "subject": "feat(macros): carry resolved choice metadata and shared candidates"}, {"commit": "c4444ab", "name": "macro_skill_definition_wire_schema_version", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "924884e", "name": "managed_tmp_roots_list", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "924884e", "name": "managed_tmp_roots_register", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "924884e", "name": "managed_tmp_roots_wire_schema_version", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "11f29c3", "name": "memory_history_compare", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_feed", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "c2a415e", "name": "memory_history_mark_reviewed", "release": "v0.36.4", "subject": "feat(memory-history): add review state store with query and mark-reviewed"}, {"commit": "11f29c3", "name": "memory_history_resolve", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "c2a415e", "name": "memory_history_review_state", "release": "v0.36.4", "subject": "feat(memory-history): add review state store with query and mark-reviewed"}, {"commit": "11f29c3", "name": "memory_history_subjects", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_sync", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_timeline", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_version", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_wire_schema_version", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "fa39036", "name": "normalize_instruction_manifest", "release": null, "subject": "feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)"}, {"commit": "4eb40d5", "name": "normalize_macro_config_layer", "release": "v0.36.4", "subject": "feat(compat): shared Rust config normalization contract"}, {"commit": "297bc1e", "name": "observe_launch_scratch_liveness", "release": "v0.36.0", "subject": "feat(core): launch_scratch_liveness module with procfs probe bindings"}, {"commit": "f52fa7c", "name": "project_finalizer_node_view", "release": "v0.35.1", "subject": "feat(finalizer): implement core-run-view-model run_view module"}, {"commit": "0ad6e44", "name": "prompt_looks_generated", "release": "v0.36.2", "subject": "feat(prompt-prediction): flag chop and job tribe origins as generated"}, {"commit": "12e012d", "name": "prompt_prediction_wire_schema_version", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "92a4fc4", "name": "prompt_proc_origin", "release": "v0.31.5", "subject": "feat(agent-launch): add native %proc dispatch helpers"}, {"commit": "df23cce", "name": "read_prompt_stash_archive", "release": "v0.36.1", "subject": "feat(prompt-stash): append-only archive for every permanent stash removal"}, {"commit": "28befcb", "name": "read_unread_completion_index", "release": "v0.36.2", "subject": "feat(notifications): store generations, ack API, and lean unread index"}, {"commit": "413511f", "name": "reconcile_notification_rows", "release": "v0.36.1", "subject": "feat(notifications): lock-held field-scoped reconcile write plus empty raw_suffix matcher parity"}, {"commit": "df23cce", "name": "recover_prompt_stash_archive", "release": "v0.36.1", "subject": "feat(prompt-stash): append-only archive for every permanent stash removal"}, {"commit": "2838c7e", "name": "resolve_input_type", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "c4444ab", "name": "resolve_macro_skill_definition", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "39324ac", "name": "sanitize_attachment_name", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "39324ac", "name": "scan_note_attachment_refs", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "3d406d4", "name": "select_publication_retries", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "9368ddf", "name": "tool_run_briefs", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "830e900", "name": "tool_run_detail", "release": "v0.36.0", "subject": "feat(tool-run): add tool_run_detail projection with stage timeline and witness counts"}, {"commit": "17b072b", "name": "tool_run_duration_calibration", "release": "v0.36.1", "subject": "feat(tool-run): add duration classes and inline-fit policy"}, {"commit": "17b072b", "name": "tool_run_duration_fit", "release": "v0.36.1", "subject": "feat(tool-run): add duration classes and inline-fit policy"}, {"commit": "cee9f49", "name": "tool_run_join", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "9368ddf", "name": "tool_run_live_glance", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "9368ddf", "name": "tool_run_node_summaries", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "7a9ffad", "name": "tool_run_record_demand", "release": "v0.36.2", "subject": "feat(tool-run): record per-run demand context, usage, and worker grants"}, {"commit": "cee9f49", "name": "tool_run_release_join", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "6e23783", "name": "tool_run_stats_report", "release": "v0.36.2", "subject": "feat(tool-run): implement core-stats report for sase-1dm.3"}, {"commit": "cee9f49", "name": "tool_run_sync_wait_budget", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "39324ac", "name": "unique_attachment_name", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "2838c7e", "name": "validate_enum_choices", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "4b4a052", "name": "wait_epic_follow_reduce", "release": null, "subject": "feat(wait): add pure wait_epic_follow reducer with Python binding (sase-1h7.4)"}], "declared_floor": "0.35.0", "exit_code": 4, "message": "sase-core-rs==0.35.0 is missing 99 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
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
test selection escalated to the full suite (rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 4917 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 3999 commits behind HEAD) matched 6 changed file(s) and contributed 114 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.12.3, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [27702 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
..........................................................s............. [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
.......s................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
...........s............................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
..............................................................s......... [ 69%]
ss...................................................................... [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
.................................................................s...... [ 79%]
........................................................................ [ 79%]
.........................s.............................................. [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
.......F................................................................ [ 99%]
........................................................................ [ 99%]
......................................................                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________________ test_block_spread_bracket_top_aligns _____________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    async def test_block_spread_bracket_top_aligns() -> None:
        app = _DetailApp()
        async with app.run_test(size=(100, 30)) as pilot:
            await pilot.pause()
            _pin(app, deck=0, blocks=1000)
            panel = await _panel(app)
            panel.show_main_document(
                _document("s1", _reply_card(3, lines_per_block=10), digest="spread-2"),
                "reply",
            )
            await wait_for(
                pilot, lambda: panel.block_mode_for_active_card() is RenderMode.SPREAD
            )
            view = panel.main_view
            await wait_for(pilot, lambda: view.block_header_row("b2") is not None)
            card = panel._main_document.card("reply")
            assert card is not None
            await wait_for(pilot, lambda: view.spread_landing_target(card) is not None)
            target = view.spread_landing_target(card)
            assert target is not None
            await wait_for(pilot, lambda: int(_scroll(panel).scroll_y) == target)
            assert panel.cycle_block(-1) is True
            assert view.active_block_id("reply") == "b1"
            header = view.block_header_row("b1")
            assert header is not None
>           await wait_for(pilot, lambda: int(_scroll(panel).scroll_y) == header)

tests/ace/tui/widgets/decks/test_deck_block_spread_pilot.py:153: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/wait.py:88: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function test_block_spread_bracket_top_aligns.<locals>.<lambda> at 0x7f88e1e09170>
is_success = <class 'bool'>
settle = <function wait_for.<locals>.<lambda> at 0x7f88e1e081a0>, timeout = 5.0
timeout_message = <function wait_for.<locals>.timeout_message at 0x7f88e1e0bed0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f890f084880>, backoff_after_misses = 3
backoff_seconds = 0.001

    async def _poll_until[T](
        predicate: Callable[[], T | None],
        *,
        is_success: Callable[[T | None], bool],
        settle: Callable[[], Awaitable[None]],
        timeout: float,
        timeout_message: Callable[[], str],
        clock: Callable[[], float] | None = None,
        sleep: Callable[[float], Awaitable[None]] | None = None,
        backoff_after_misses: int = _BACKOFF_AFTER_MISSES,
        backoff_seconds: float = _BACKOFF_SECONDS,
    ) -> T | None:
        """Poll a predicate with event-driven settling and a bounded backoff."""
    
        if clock is None:
            clock = asyncio.get_running_loop().time
        if sleep is None:
            sleep = asyncio.sleep
    
        deadline = clock() + timeout
        misses = 0
        while True:
            value = predicate()
            if is_success(value):
                return value
            if clock() >= deadline:
>               raise AssertionError(timeout_message())
E               AssertionError: wait_for(test_block_spread_bracket_top_aligns.<locals>.<lambda>) timed out after 5.0s waiting for it to return True

src/sase/ace/testing/wait.py:54: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

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

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=1682882) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:130: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
81.69s call     tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows
65.30s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
45.90s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
40.84s call     tests/test_run_pytest_main.py::test_main_serial_snapshot_mode_never_acquires
26.89s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
20.94s teardown tests/ace/tui/widgets/test_prompt_tab_focus_steal.py::test_tab_with_focus_on_list_still_stays_on_agents
19.90s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
18.29s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
15.53s call     tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_fresh_app_instance_hides_removed_rows
15.45s call     tests/test_agent_group_revival_e2e.py::test_saved_group_revive_restores_deleted_artifacts_and_tribe_real_loader
15.33s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
14.81s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
14.48s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
14.17s call     tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
14.04s call     tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
13.89s setup    tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
13.09s call     tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace
12.25s call     tests/test_gemini_active_surface_guard.py::test_no_gemini_cli_provider_surface_in_active_tree
11.28s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
10.92s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
=========================== short test summary info ============================
FAILED tests/ace/tui/widgets/decks/test_deck_block_spread_pilot.py::test_block_spread_bracket_top_aligns
===== 1 failed, 27693 passed, 8 skipped, 74 warnings in 1830.07s (0:30:30) =====
error: recipe `test-scoped` failed on line 521 with exit code 1
error: recipe `check` failed on line 771 with exit code 1
failed/1  2345879ms
triage lint (symvision): 2 KNOWN
triage test (scoped): 1 NEW
NEW test (scoped): FAILED tests/ace/tui/widgets/decks/test_deck_block_spread_pilot.py::test_block_spread_bracket_top_aligns — recorded evidence; no owner
KNOWN lint (symvision): _runs in src/sase/agents_sync/v2_snapshot_io.py — witness 05b9fc696a324977dde864aadd60a092; no owner
KNOWN lint (symvision): _runs in src/sase/ace/tui/widgets/decks/final/overview_card.py — witness 05b9fc696a324977dde864aadd60a092; no owner
sase tool show c2b50e46cc35ae8e1ea45d05b4409148 -l
verdict: new_failures — 1 NEW, 2 KNOWN; exit 1

