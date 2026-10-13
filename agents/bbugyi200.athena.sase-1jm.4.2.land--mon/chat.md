# Chat History - ace-run (sase-1jm.4.2.land--mon)

- **TIMESTAMP:** 2026-10-12 11:47:07 EDT
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1jm.4.2.land--mon

## Prompt

sase monitor start --command 'just install-venv; install_rc=$?; if [ "$install_rc" -ne 0 ]; then exit "$install_rc"; fi; pytest -q tests/ace/tui/widgets/decks; pytest_rc=$?; sase tool run check; check_rc=$?; TZ=UTC just fix-tui-screenshots -- tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py; visual_rc=$?; printf "RESULTS pytest=%s check=%s visual=%s\\n" "$pytest_rc" "$check_rc" "$visual_rc"; if [ "$pytest_rc" -ne 0 ] || [ "$check_rc" -ne 0 ] || [ "$visual_rc" -ne 0 ]; then exit 1; fi; exit 0' --reason 'Set up the workspace test environment, verify Record and deck changes, run the required check, and update the approved Record deck goldens'

## Response

sase tool run 1915bb3bbf616a685327e76c77c9bf79
[install-venv] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core for local dev.
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.38.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[rust-install] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev builds from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core ignore it. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
# Capture the source identity after the checkout refresh above and before
# the build below. It is written to the venv only after a successful
# install (wheel-cache hit or `maturin develop` alike), so an edit made
# during the build still reads as stale on the next check.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/4e9546c8699949cc32f9a4ecb8d4a8684915294da924bef38f03db05070d3c69/sase_core_rs-0.38.0-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 20ms
Prepared 1 package in 2ms
Uninstalled 1 package in 2ms
Installed 1 package in 9ms
 ~ sase-core-rs==0.38.0 (from file:///home/bryan/.sase/cache/sase-core-artifacts/4e9546c8699949cc32f9a4ecb8d4a8684915294da924bef38f03db05070d3c69/sase_core_rs-0.38.0-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/c8b32182b52a08fce1d14eacd943c8e13340f183eeff5dbf68f2b495a86ea630/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/sase-macro-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 99 packages in 318ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
Prepared 1 package in 628ms
Uninstalled 1 package in 8ms
Installed 1 package in 5ms
 ~ sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
ImportError while loading conftest '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/conftest.py'.
tests/ace/tui/conftest.py:7: in <module>
    from textual.pilot import Pilot
E   ModuleNotFoundError: No module named 'textual'
sase tool run 8f3135cbb81d4573fd941bc2d3375461
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.38.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
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
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.38.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol 'sase-1jm(archive_corpus_is_warm)' --epic-symbol 'sase-1jx.12(record_visibility_selection)' 
Error: Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!:
  _load_archive_bundle in src/sase/ace/tui/actions/agents/_archive_reader.py
error: recipe `_lint-symvision` failed on line 450 with exit code 1
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
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.38.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 5157 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 4290 commits behind HEAD) matched 0 changed file(s) and contributed 0 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.12.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [2170 items]

........................................................................ [  3%]
........................................................................ [  6%]
........................................................................ [  9%]
........................................................................ [ 13%]
........................................................................ [ 16%]
........................................................................ [ 19%]
........................................................................ [ 23%]
........................................................................ [ 26%]
........................................................................ [ 29%]
........................................................................ [ 33%]
........................................................................ [ 36%]
........................................................................ [ 39%]
........................................................................ [ 43%]
........................................................................ [ 46%]
........................................................................ [ 49%]
........................................................................ [ 53%]
..............................F......................................... [ 56%]
........................................................................ [ 59%]
........................................................................ [ 63%]
........................................................................ [ 66%]
........................................................................ [ 69%]
........................................................................ [ 72%]
........................................................................ [ 76%]
........................................................................ [ 79%]
........................................................................ [ 82%]
........................................................................ [ 86%]
.............................................F.......................... [ 89%]
........................................................................ [ 92%]
........................................................................ [ 96%]
........................................................................ [ 99%]
..........                                                               [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____ test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data ______
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-6/popen-gw2/test_workflow_snapshot_render_0')

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
_________ test_record_show_and_refresh_share_archive_and_live_subject __________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff4d8bc7850>

    async def test_record_show_and_refresh_share_archive_and_live_subject(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        from pathlib import Path
    
        from textual.app import App, ComposeResult
    
        from sase.ace.tui.widgets.agent_detail import AgentDetail
        from sase.ace.tui.widgets.decks.record.loader import record_cache_key
        from tests.ace.tui.widgets._agent_display_helpers import make_agent
    
        root = Path(__file__).resolve().parents[5]
    
        class _DetailApp(App[None]):
            CSS_PATH = root / "src/sase/ace/tui/styles.tcss"
    
            def compose(self) -> ComposeResult:
                yield AgentDetail(id="agent-detail-panel")
    
>       agent = make_agent(
            agent_name="archived",
            raw_suffix="archive-row",
            parent_timestamp="live-parent",
            retry_of_timestamp="live-retry",
            bundle_path="/tmp/archive.json",
            _archive_read_only=True,
        )

tests/ace/tui/widgets/decks/test_record_deck_shell.py:326: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

overrides = {'agent_name': 'archived', 'raw_suffix': 'archive-row', 'parent_timestamp': 'live-parent', 'retry_of_timestamp': 'live-retry', ...}

    def make_agent(**overrides: object) -> Agent:
        """Create a minimal Agent for testing."""
        defaults: dict[str, object] = {
            "agent_type": AgentType.RUNNING,
            "cl_name": "test_cl",
            "project_file": "/tmp/test.sase",
            "status": "RUNNING",
            "start_time": datetime(2024, 1, 1, 14, 23, 45),
        }
        defaults.update(overrides)
>       return Agent(**defaults)  # type: ignore[arg-type]
               ^^^^^^^^^^^^^^^^^
E       TypeError: Agent.__init__() got an unexpected keyword argument 'bundle_path'. Did you mean 'gate_bundle_path'?

tests/ace/tui/widgets/_agent_display_helpers.py:34: TypeError
=============================== warnings summary ===============================
tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/models/agent_archive_list.py:144: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    if all(isinstance(part, str) and part for part in (user, machine, run_id)):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_lookup.py::test_queued_explicit_open_drains_on_idle_tick
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:1725: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return ((p, type(p)) for p in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
18.93s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
18.39s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
11.57s call     tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
11.33s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
9.10s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
8.59s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
8.53s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
8.03s call     tests/test_project_display_presentation_audit.py::test_project_labels_never_derive_from_paths
7.87s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
7.58s call     tests/test_project_display_presentation_audit.py::test_path_label_exemptions_name_existing_sites_and_rationales
6.48s call     tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
6.36s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
6.26s call     tests/ace/tui/test_live_reply_follow_mounted_reply.py::test_gated_muse_stream_reaches_mounted_reply_before_terminal
6.12s call     tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
5.93s call     tests/ace/tui/test_agents_filter_bar_session.py::test_slash_opens_the_bar_and_commits_like_f
5.76s call     tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
5.51s call     tests/ace/tui/test_agents_filter_bar_session.py::test_f_opens_the_bar_and_typing_previews_then_commits
5.20s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
5.05s call     tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
4.94s call     tests/ace/tui/test_agents_filter_bar_session.py::test_escape_restores_the_prior_committed_query
=========================== short test summary info ============================
FAILED tests/ace/tui/widgets/test_agent_display_workflow_async.py::test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data
FAILED tests/ace/tui/widgets/decks/test_record_deck_shell.py::test_record_show_and_refresh_share_archive_and_live_subject
============ 2 failed, 2168 passed, 2 warnings in 150.69s (0:02:30) ============
error: recipe `test-scoped` failed on line 564 with exit code 1
error: recipe `check` failed on line 814 with exit code 1
failed  exit=1  duration=501002ms
unattrib  1m 4s
triage lint (symvision): 1 KNOWN continued
triage test (scoped): 1 KNOWN 1 NEW stopped
NEW test (scoped): FAILED tests/ace/tui/widgets/test_agent_display_workflow_async.py::test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data — recorded evidence; no owner
KNOWN lint (symvision): _load_archive_bundle in src/sase/ace/tui/actions/agents/_archive_reader.py — witness 0d0e7cc8a4cdd11885a1cc3a085839d9; no owner
KNOWN test (scoped): FAILED tests/ace/tui/widgets/decks/test_record_deck_shell.py::test_record_show_and_refresh_share_archive_and_live_subject — witness 0409af70242a4314f4aa519ba6c48ebb; no owner
verdict: new_failures — 1 NEW, 2 KNOWN; exit 1
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.38.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.12.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [15 items]

.............F.                                                          [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
________________________ test_archive_help_png_snapshot ________________________
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0269f8a9c0>

    async def test_archive_help_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The Agents help modal documents the read-only Archive surface."""
        patch_startup_loaders(monkeypatch, agents=[_inbox_agent()])
        pin_agents_visual_now(monkeypatch, NOW)
        with override_flags(agents_archive_view=True):
            async with AcePage(initial_tab="agents") as page:
                await wait_for_startup(page)
                await _open_archive(page, _list_history())
    
                await page.press("?")
                await page.expect_modal("HelpModal")
                await wait_for_visual_idle(page)
                # The Keymaps view is far taller than the modal viewport (the
                # Archive box sits two-thirds down), so scroll until the whole
                # box paints, title through last row.
                for _ in range(60):
                    if "Live actions stay in Inbox" in page_svg_text(page):
                        break
                    await page.press("ctrl+d")
                    await wait_for_visual_idle(page)
                await _settle_archive_detail(page)
                await wait_for_visual_idle(page)
>               assert_page_svg_contains(page, "Archive (read-only)")

tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py:498: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f026982c830>
text = 'Archive (read-only)'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:232: AssertionError
============================= slowest 20 durations =============================
10.08s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot
7.03s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_folded_banners_png_snapshot
6.49s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_marked_row_png_snapshot
6.38s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_list_png_snapshot
6.23s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_parked_marker_png_snapshot
6.06s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_unreadable_entry_png_snapshot
5.87s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_restored_overlay_png_snapshot
5.68s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_archived_lifecycle_png_snapshot
5.58s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archived_identity_reply_png_snapshot
5.20s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_links_png_snapshot
5.17s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_missing_content_png_snapshot
5.11s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_rebuilding_png_snapshot
5.07s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_inbox_lifecycle_png_snapshot
3.91s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_empty_png_snapshot
3.52s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_missing_index_png_snapshot
0.14s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_missing_index_png_snapshot
0.14s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_list_png_snapshot
0.14s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_folded_banners_png_snapshot
0.14s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_unreadable_entry_png_snapshot
0.13s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_marked_row_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot
======================== 1 failed, 14 passed in 18.96s =========================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.12.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

F                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
________________________ test_archive_help_png_snapshot ________________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f65c2102250>

    async def test_archive_help_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The Agents help modal documents the read-only Archive surface."""
        patch_startup_loaders(monkeypatch, agents=[_inbox_agent()])
        pin_agents_visual_now(monkeypatch, NOW)
        with override_flags(agents_archive_view=True):
            async with AcePage(initial_tab="agents") as page:
                await wait_for_startup(page)
                await _open_archive(page, _list_history())
    
                await page.press("?")
                await page.expect_modal("HelpModal")
                await wait_for_visual_idle(page)
                # The Keymaps view is far taller than the modal viewport (the
                # Archive box sits two-thirds down), so scroll until the whole
                # box paints, title through last row.
                for _ in range(60):
                    if "Live actions stay in Inbox" in page_svg_text(page):
                        break
                    await page.press("ctrl+d")
                    await wait_for_visual_idle(page)
                await _settle_archive_detail(page)
                await wait_for_visual_idle(page)
>               assert_page_svg_contains(page, "Archive (read-only)")

tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py:498: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f65c1ca7a10>
text = 'Archive (read-only)'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:232: AssertionError
============================= slowest 20 durations =============================
9.01s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot
0.12s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot
============================== 1 failed in 14.59s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.12.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

F                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
________________________ test_archive_help_png_snapshot ________________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6d28a72250>

    async def test_archive_help_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The Agents help modal documents the read-only Archive surface."""
        patch_startup_loaders(monkeypatch, agents=[_inbox_agent()])
        pin_agents_visual_now(monkeypatch, NOW)
        with override_flags(agents_archive_view=True):
            async with AcePage(initial_tab="agents") as page:
                await wait_for_startup(page)
                await _open_archive(page, _list_history())
    
                await page.press("?")
                await page.expect_modal("HelpModal")
                await wait_for_visual_idle(page)
                # The Keymaps view is far taller than the modal viewport (the
                # Archive box sits two-thirds down), so scroll until the whole
                # box paints, title through last row.
                for _ in range(60):
                    if "Live actions stay in Inbox" in page_svg_text(page):
                        break
                    await page.press("ctrl+d")
                    await wait_for_visual_idle(page)
                await _settle_archive_detail(page)
                await wait_for_visual_idle(page)
>               assert_page_svg_contains(page, "Archive (read-only)")

tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py:498: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f6d2861ba10>
text = 'Archive (read-only)'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:232: AssertionError
============================= slowest 20 durations =============================
9.18s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot
0.13s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot
============================== 1 failed in 15.31s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.12.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [3 items]

...                                                                      [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
5.75s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_archived_lifecycle_png_snapshot
4.97s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_unreadable_entry_png_snapshot
4.57s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_inbox_lifecycle_png_snapshot
0.14s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_archived_lifecycle_png_snapshot
0.13s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_inbox_lifecycle_png_snapshot
0.13s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_record.py::test_agents_record_unreadable_entry_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 3 passed in 12.04s ==============================
fix-tui-screenshots: update partial
scope: targeted
WARNING:
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/9f634da121b14377938666c346532f94/capture.log, .pytest_cache/sase-visual/runs/9f634da121b14377938666c346532f94/recover-1.log, .pytest_cache/sase-visual/runs/9f634da121b14377938666c346532f94/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot))
  Those goldens were left unchanged and are not known to be current.
counts: created=0 updated=3 unchanged=11 stale=0
manifest: .pytest_cache/sase-visual/runs/9f634da121b14377938666c346532f94/manifest.json
run-dir: .pytest_cache/sase-visual/runs/9f634da121b14377938666c346532f94
report: .pytest_cache/sase-visual/runs/9f634da121b14377938666c346532f94/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/9f634da121b14377938666c346532f94/report/summary.md
RESULTS pytest=4 check=1 visual=0
failed  exit=1  duration=592115ms

