# Chat History - ace-run (sase-1vy.1--mon)

- **TIMESTAMP:** 2026-11-28 04:13:18 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1vy.1--mon

## Prompt

sase monitor start --command 'just check' --reason 'Verify producer-first config drain before host completion'

## Response

sase tool run 277bae2e2d43fff37d91491c0cff4d8c
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.45.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.44.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ epic-symbol freshness
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
✓ lint (eager annotations)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (docs contract)
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.44.2 is missing 60 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] agent_artifact_list_wire_schema_version: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); release v0.45.0 contains it.
[core-floor-probe] agent_hijack_decide: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); release v0.45.0 contains it.
[core-floor-probe] agent_hijack_eligibility_wire_schema_version: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); release v0.45.0 contains it.
[core-floor-probe] agent_hijack_latch_observe: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); release v0.45.0 contains it.
[core-floor-probe] agent_hijack_latch_wire_schema_version: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); release v0.45.0 contains it.
[core-floor-probe] agent_hijack_select_occupant: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); release v0.45.0 contains it.
[core-floor-probe] append_notification_counts_with_options: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); release v0.45.0 contains it.
[core-floor-probe] append_notification_with_options: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); release v0.45.0 contains it.
[core-floor-probe] apply_chop_batch_transition: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); release v0.45.0 contains it.
[core-floor-probe] artifact_file_association_query: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); release v0.45.0 contains it.
[core-floor-probe] artifact_file_association_query_wire_schema_version: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); release v0.45.0 contains it.
[core-floor-probe] artifact_read_audit_query: first appears in sase-core 3992fce (feat(audit-query): query artifact-read audit logs); release v0.45.0 contains it.
[core-floor-probe] artifact_read_audit_query_wire_schema_version: first appears in sase-core 3992fce (feat(audit-query): query artifact-read audit logs); release v0.45.0 contains it.
[core-floor-probe] axe_error_wire_schema_version: first appears in sase-core 3a32a23 (feat(axe-error): add volatile-token normalizer and signature grouping); release v0.45.0 contains it.
[core-floor-probe] bead_touch_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); release v0.45.0 contains it.
[core-floor-probe] bead_touch_member_query_wire_schema_version: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); release v0.45.0 contains it.
[core-floor-probe] bead_triage_owner_candidates: first appears in sase-core cb76eb2 (feat(bead): project triage owner candidates from the read model); release v0.45.0 contains it.
[core-floor-probe] bead_view_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); release v0.45.0 contains it.
[core-floor-probe] chop_batch_generation_matches: first appears in sase-core b1a0363 (feat(axe-chop): add clan-scoped generation match and cancelled settlement); release v0.45.0 contains it.
[core-floor-probe] compact_notification_store: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); release v0.45.0 contains it.
[core-floor-probe] decide_local_command_trust: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); release v0.45.0 contains it.
[core-floor-probe] decide_publication_standing: first appears in sase-core 3c3263f (feat(publication): add standing-alert decider with capped backoff); release v0.45.0 contains it.
[core-floor-probe] detect_question_copy_candidates: first appears in sase-core 8cb07c3 (feat(question-copy): add conservative text candidate detector); release v0.45.0 contains it.
[core-floor-probe] digest_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); release v0.45.0 contains it.
[core-floor-probe] display_question_copy: first appears in sase-core 76638b5 (feat(questions): add question copy contracts); release v0.45.0 contains it.
[core-floor-probe] evaluate_inactive_staged_handoff: first appears in sase-core 34461b7 (fix(staged-handoff): ignore inactive failed-origin ownership); no release tag contains it yet.
[core-floor-probe] filter_trusted_local_layer: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); release v0.45.0 contains it.
[core-floor-probe] gate_failure_resurface_decision: first appears in sase-core f0034a7 (feat(agent-scan,notifications): project gate failure and dismissal timestamps with shared resurface policy); release v0.45.0 contains it.
[core-floor-probe] group_axe_errors: first appears in sase-core 3a32a23 (feat(axe-error): add volatile-token normalizer and signature grouping); release v0.45.0 contains it.
[core-floor-probe] hijack_latch_force_eligibility: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); release v0.45.0 contains it.
[core-floor-probe] hijack_latch_reconcile: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); release v0.45.0 contains it.
[core-floor-probe] local_command_trust_store_allow: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); release v0.45.0 contains it.
[core-floor-probe] local_command_trust_store_get: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); release v0.45.0 contains it.
[core-floor-probe] local_command_trust_store_revoke: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); release v0.45.0 contains it.
[core-floor-probe] local_command_trust_wire_schema_version: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); release v0.45.0 contains it.
[core-floor-probe] lookup_agent_artifacts: first appears in sase-core a4b1c84 (feat(agent-scan): add read-only indexed artifact identity lookups); release v0.45.0 contains it.
[core-floor-probe] lookup_named_dismissed_bundle: first appears in sase-core d201086 (feat(agent-scan): add bounded named lookup selection); release v0.45.0 contains it.
[core-floor-probe] memory_audit_query: first appears in sase-core c5e60d7 (feat(audit-query): add targeted memory audit query over JSONL); release v0.45.0 contains it.
[core-floor-probe] memory_audit_query_wire_schema_version: first appears in sase-core c5e60d7 (feat(audit-query): add targeted memory audit query over JSONL); release v0.45.0 contains it.
[core-floor-probe] normalize_error_signature: first appears in sase-core 3a32a23 (feat(axe-error): add volatile-token normalizer and signature grouping); release v0.45.0 contains it.
[core-floor-probe] normalize_question_copy: first appears in sase-core 76638b5 (feat(questions): add question copy contracts); release v0.45.0 contains it.
[core-floor-probe] plan_prompt_command_substitution: first appears in sase-core 1191f9a (feat: add prompt command-substitution source policy); release v0.45.0 contains it.
[core-floor-probe] project_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); release v0.45.0 contains it.
[core-floor-probe] project_monitor_turn_state: first appears in sase-core 1fb9701 (feat(staged-handoff): project held staged monitors as first-class state); release v0.45.0 contains it.
[core-floor-probe] prompt_command_substitution_wire_schema_version: first appears in sase-core 1191f9a (feat: add prompt command-substitution source policy); release v0.45.0 contains it.
[core-floor-probe] query_agent_artifact_index_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); release v0.45.0 contains it.
[core-floor-probe] query_agent_artifact_index_reusable: first appears in sase-core 575d430 (fix(agent-scan): validate reusable full index payloads); release v0.45.0 contains it.
[core-floor-probe] reconcile_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); release v0.45.0 contains it.
[core-floor-probe] reconcile_notification_rows_with_options: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); release v0.45.0 contains it.
[core-floor-probe] resolve_notification_payloads: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); release v0.45.0 contains it.
[core-floor-probe] scan_agent_artifact_dirs_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); release v0.45.0 contains it.
[core-floor-probe] scan_agent_artifacts_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); release v0.45.0 contains it.
[core-floor-probe] select_agent_artifact_group: first appears in sase-core b9f33b0 (feat(agent-scan): select indexed session and clan generations); release v0.45.0 contains it.
[core-floor-probe] select_named_agent: first appears in sase-core d201086 (feat(agent-scan): add bounded named lookup selection); release v0.45.0 contains it.
[core-floor-probe] select_unscanned_coverage: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); release v0.45.0 contains it.
[core-floor-probe] suggest_unscanned_repair: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); release v0.45.0 contains it.
[core-floor-probe] summarize_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); release v0.45.0 contains it.
[core-floor-probe] unscanned_wire_schema_version: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); release v0.45.0 contains it.
[core-floor-probe] upsert_notification_with_options: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); release v0.45.0 contains it.
[core-floor-probe] validate_chop_batch_manifest: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); release v0.45.0 contains it.
{"cache_hit": true, "capabilities": [{"commit": "8cedd45", "name": "agent_artifact_list_wire_schema_version", "release": "v0.45.0", "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "9940715", "name": "agent_hijack_decide", "release": "v0.45.0", "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "9940715", "name": "agent_hijack_eligibility_wire_schema_version", "release": "v0.45.0", "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_observe", "release": "v0.45.0", "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_wire_schema_version", "release": "v0.45.0", "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "9940715", "name": "agent_hijack_select_occupant", "release": "v0.45.0", "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "6524f37", "name": "append_notification_counts_with_options", "release": "v0.45.0", "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "6524f37", "name": "append_notification_with_options", "release": "v0.45.0", "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "6cd9a0c", "name": "apply_chop_batch_transition", "release": "v0.45.0", "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "19b89ac", "name": "artifact_file_association_query", "release": "v0.45.0", "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "19b89ac", "name": "artifact_file_association_query_wire_schema_version", "release": "v0.45.0", "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "3992fce", "name": "artifact_read_audit_query", "release": "v0.45.0", "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "3992fce", "name": "artifact_read_audit_query_wire_schema_version", "release": "v0.45.0", "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "3a32a23", "name": "axe_error_wire_schema_version", "release": "v0.45.0", "subject": "feat(axe-error): add volatile-token normalizer and signature grouping"}, {"commit": "9f9341e", "name": "bead_touch_member_query", "release": "v0.45.0", "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "9f9341e", "name": "bead_touch_member_query_wire_schema_version", "release": "v0.45.0", "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "cb76eb2", "name": "bead_triage_owner_candidates", "release": "v0.45.0", "subject": "feat(bead): project triage owner candidates from the read model"}, {"commit": "9f9341e", "name": "bead_view_member_query", "release": "v0.45.0", "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "b1a0363", "name": "chop_batch_generation_matches", "release": "v0.45.0", "subject": "feat(axe-chop): add clan-scoped generation match and cancelled settlement"}, {"commit": "6524f37", "name": "compact_notification_store", "release": "v0.45.0", "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "e7647bf", "name": "decide_local_command_trust", "release": "v0.45.0", "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "3c3263f", "name": "decide_publication_standing", "release": "v0.45.0", "subject": "feat(publication): add standing-alert decider with capped backoff"}, {"commit": "8cb07c3", "name": "detect_question_copy_candidates", "release": "v0.45.0", "subject": "feat(question-copy): add conservative text candidate detector"}, {"commit": "e7647bf", "name": "digest_local_commands", "release": "v0.45.0", "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "76638b5", "name": "display_question_copy", "release": "v0.45.0", "subject": "feat(questions): add question copy contracts"}, {"commit": "34461b7", "name": "evaluate_inactive_staged_handoff", "release": null, "subject": "fix(staged-handoff): ignore inactive failed-origin ownership"}, {"commit": "e7647bf", "name": "filter_trusted_local_layer", "release": "v0.45.0", "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "f0034a7", "name": "gate_failure_resurface_decision", "release": "v0.45.0", "subject": "feat(agent-scan,notifications): project gate failure and dismissal timestamps with shared resurface policy"}, {"commit": "3a32a23", "name": "group_axe_errors", "release": "v0.45.0", "subject": "feat(axe-error): add volatile-token normalizer and signature grouping"}, {"commit": "e9b1cf0", "name": "hijack_latch_force_eligibility", "release": "v0.45.0", "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "hijack_latch_reconcile", "release": "v0.45.0", "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "233cb41", "name": "local_command_trust_store_allow", "release": "v0.45.0", "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_get", "release": "v0.45.0", "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_revoke", "release": "v0.45.0", "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "e7647bf", "name": "local_command_trust_wire_schema_version", "release": "v0.45.0", "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "a4b1c84", "name": "lookup_agent_artifacts", "release": "v0.45.0", "subject": "feat(agent-scan): add read-only indexed artifact identity lookups"}, {"commit": "d201086", "name": "lookup_named_dismissed_bundle", "release": "v0.45.0", "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "c5e60d7", "name": "memory_audit_query", "release": "v0.45.0", "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "c5e60d7", "name": "memory_audit_query_wire_schema_version", "release": "v0.45.0", "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "3a32a23", "name": "normalize_error_signature", "release": "v0.45.0", "subject": "feat(axe-error): add volatile-token normalizer and signature grouping"}, {"commit": "76638b5", "name": "normalize_question_copy", "release": "v0.45.0", "subject": "feat(questions): add question copy contracts"}, {"commit": "1191f9a", "name": "plan_prompt_command_substitution", "release": "v0.45.0", "subject": "feat: add prompt command-substitution source policy"}, {"commit": "e7647bf", "name": "project_local_commands", "release": "v0.45.0", "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "1fb9701", "name": "project_monitor_turn_state", "release": "v0.45.0", "subject": "feat(staged-handoff): project held staged monitors as first-class state"}, {"commit": "1191f9a", "name": "prompt_command_substitution_wire_schema_version", "release": "v0.45.0", "subject": "feat: add prompt command-substitution source policy"}, {"commit": "8cedd45", "name": "query_agent_artifact_index_list", "release": "v0.45.0", "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "575d430", "name": "query_agent_artifact_index_reusable", "release": "v0.45.0", "subject": "fix(agent-scan): validate reusable full index payloads"}, {"commit": "6cd9a0c", "name": "reconcile_chop_batch", "release": "v0.45.0", "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "6524f37", "name": "reconcile_notification_rows_with_options", "release": "v0.45.0", "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "6524f37", "name": "resolve_notification_payloads", "release": "v0.45.0", "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "8cedd45", "name": "scan_agent_artifact_dirs_list", "release": "v0.45.0", "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "8cedd45", "name": "scan_agent_artifacts_list", "release": "v0.45.0", "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "b9f33b0", "name": "select_agent_artifact_group", "release": "v0.45.0", "subject": "feat(agent-scan): select indexed session and clan generations"}, {"commit": "d201086", "name": "select_named_agent", "release": "v0.45.0", "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "7ac2081", "name": "select_unscanned_coverage", "release": "v0.45.0", "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "7ac2081", "name": "suggest_unscanned_repair", "release": "v0.45.0", "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "6cd9a0c", "name": "summarize_chop_batch", "release": "v0.45.0", "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "7ac2081", "name": "unscanned_wire_schema_version", "release": "v0.45.0", "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "6524f37", "name": "upsert_notification_with_options", "release": "v0.45.0", "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "6cd9a0c", "name": "validate_chop_batch_manifest", "release": "v0.45.0", "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}], "declared_floor": "0.44.2", "exit_code": 4, "message": "sase-core-rs==0.44.2 is missing 60 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.45.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.44.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: root-conftest); 6006 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: root-conftest)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [63996 items]

........................................................................ [  0%]
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
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
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
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
................................s....................................... [  4%]
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
........................................................................ [  6%]
........................................................................ [  7%]
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
........................................................................ [  8%]
........................................................................ [  9%]
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
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
.............................s.......................................... [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
....................................................................s... [ 11%]
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
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
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
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
.............s.......................................................... [ 15%]
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
........................................................................ [ 16%]
........................................................................ [ 17%]
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
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
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
........................................................................ [ 20%]
........................................................................ [ 21%]
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
........................................................................ [ 23%]
........................................................................ [ 24%]
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
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
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
........................................................................ [ 29%]
........................................................................ [ 30%]
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
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
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
..................................................................F..... [ 36%]
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
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
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
........................................................................ [ 40%]
........................................................................ [ 41%]
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
.......................................................s................ [ 42%]
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
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
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
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
...................s.................................................... [ 48%]
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
........................................................................ [ 49%]
........................................................................ [ 50%]
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
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
.F.F........................s........................................... [ 52%]
.....................................s.s................................ [ 52%]
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
................................................FFF.F...FF.............. [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
.F..F.F..F..FF..FF.F...F.F....F.....F..F................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
......................................F................................. [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
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
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
..............................F...F...F..F...F..F..................F.... [ 58%]
....F....F....F...F...F.....F..................................F........ [ 58%]
..............F...........................................F............. [ 58%]
........................................................................ [ 58%]
....................F................................................... [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
............................F..F........................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
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
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
............................................................F........... [ 62%]
........................................................................ [ 62%]
............................F........................................... [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
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
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
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
........................................................................ [ 66%]
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
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
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
.................................................ssss................... [ 69%]
........................................................................ [ 69%]
.......s................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
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
.........................F.FF.F......................................... [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
....F...........F.F..................................................... [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
....................................................F................... [ 74%]
..F....................F....................F......................F.... [ 74%]
..................F....................F.............F.................F [ 75%]
...........................F........................F...............F... [ 75%]
.........F.................F............................................ [ 75%]
......................F................................................. [ 75%]
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
F.....F....F....F....F......F.............................F............. [ 76%]
......................F..F.....................FF....F.................. [ 76%]
............F..........................F............................F... [ 77%]
......F................................................................. [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
......F................................................................. [ 77%]
..............................F...F...F....F..F.........F......F........ [ 77%]
...F............F...F........F........F.....F.........................F. [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
F...............................................F........F..........F... [ 78%]
F.....F...F.....F..F...................F..............F.......F.F.F.F... [ 78%]
..F..F.F.......F..F..F..F..F.F...F..................F................... [ 78%]
....F................................................................... [ 78%]
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
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
......................................................................s. [ 83%]
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
........................................................................ [ 84%]
........................................................................ [ 85%]
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
........................................F............................... [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
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
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
...........................................................F............ [ 92%]
........................................................................ [ 92%]
..........................................................s............. [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
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
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
...................................................F......F............. [ 96%]
........................................................................ [ 96%]
F....................................................................... [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
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
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
................................................F....................... [ 99%]
.......F.....................F....FFFF.F.F.FF.FF..FFFF..F.FFFF..F.F....F [ 99%]
FFF.F.F.F.FFF...FF.....FF.F.F....F...FF.....................             [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________ test_nested_agent_check_keeps_parent_and_never_queues _____________
[gw13] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

world = <function world.<locals>.make at 0x7f5ecfb0b690>

    def test_nested_agent_check_keeps_parent_and_never_queues(world: Any) -> None:
        w: _World = world(1, nested_check=True, max_wait_seconds=0)
        outer = w.start(
            "nested",
            SASE_AGENT="1",
            SASE_AGENT_NAME="fixture-agent",
            # There is no artifacts directory or agent_meta.json, so an attempted
            # inline escalation has no usable starter and falls back to foreground.
            SASE_PROVIDER_SYNC_SOFT_CEILING_SECONDS="8",
        )
        outer_run = _wait_for(lambda: _wrapper_run(outer.pid), "outer check wrapper")
        assert outer_run.get("parent_run_id") is None
        inner_run = _wait_for(
            lambda: next(
                (run for run in _runs() if run.get("parent_run_id") == outer_run["run_id"]),
                None,
            ),
            "inner check with a durable parent relationship",
        )
        assert _record(inner_run) is None
>       assert len(_started_children(w)) == 1
E       AssertionError: assert 0 == 1
E        +  where 0 = len([])
E        +    where [] = _started_children(_World(root=PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw13/test_nested_agent_check_keeps_0/proj...d_agent_check_keeps_0/logs'), procs=[<Popen: returncode: None args: ['/home/bryan/.local/state/sase/workspaces/sa...>]))

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/tool/test_admission_processes.py:472: AssertionError
__________ test_hook_builtin_uses_shared_runner_and_emits_noop_result __________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_hook_builtin_uses_shared_0')

    def test_hook_builtin_uses_shared_runner_and_emits_noop_result(tmp_path: Path) -> None:
>       importlib.import_module("sase.scripts.sase_chop_hook_checks")

tests/test_chop_sdk.py:407: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
<frozen importlib._bootstrap>:1406: in _gcd_import
    ???
<frozen importlib._bootstrap>:1371: in _find_and_load
    ???
<frozen importlib._bootstrap>:1342: in _find_and_load_unlocked
    ???
<frozen importlib._bootstrap>:938: in _load_unlocked
    ???
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff053097e00>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.scripts.sase_chop_hook_checks

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________________ test_all_builtin_chop_modules_use_the_registry ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    def test_all_builtin_chop_modules_use_the_registry() -> None:
        modules = {
            "artifact_retention",
            "artifact_run_prune",
            "bead_stale_cleanup",
            "comment_checks",
            "comment_zombie_checks",
            "epic_launch_flush",
            "error_digest",
            "hook_checks",
            "managed_tmp_reap",
            "mentor_checks",
            "notification_store_compact",
            "orphan_cleanup",
            "pending_checks_poll",
            "plugins_required",
            "proc_runtime_sweep",
            "pr_submitted_checks",
            "refresh_docs",
            "stale_running_cleanup",
            "state_retention",
            "suffix_transforms",
            "wait_checks",
            "workflow_checks",
        }
        for name in modules:
>           importlib.import_module(f"sase.scripts.sase_chop_{name}")

tests/test_chop_sdk.py:451: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
<frozen importlib._bootstrap>:1406: in _gcd_import
    ???
<frozen importlib._bootstrap>:1371: in _find_and_load
    ???
<frozen importlib._bootstrap>:1342: in _find_and_load_unlocked
    ???
<frozen importlib._bootstrap>:938: in _load_unlocked
    ???
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff05976d1d0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.scripts.sase_chop_pending_checks_poll

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________________ test_colon_opens_command_line_from_agents_tab _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_colon_opens_command_line_from_agents_tab() -> None:
        """Pressing ``:`` from the Agents tab opens the Command Line panel."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_e2e.py:27: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff083af6350>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________________ test_colon_opens_command_line_from_axe_tab __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_colon_opens_command_line_from_axe_tab() -> None:
        """Pressing ``:`` from the AXE tab opens the Command Line panel."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_e2e.py:47: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07512a780>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_semicolon_opens_command_palette_from_agents_and_axe_tabs _________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_semicolon_opens_command_palette_from_agents_and_axe_tabs() -> None:
        """Pressing ``;`` opens the palette from each non-Patch tab."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_e2e.py:67: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0473d8510>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________________ test_palette_executes_refresh_from_agents_tab _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_executes_refresh_from_agents_tab() -> None:
        """Selecting refresh from the Agents-tab palette calls ``action_refresh``."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
            patch.object(AceApp, "action_refresh") as refresh_mock,
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_e2e.py:99: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047f179b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________________ test_palette_executes_refresh_from_axe_tab __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_executes_refresh_from_axe_tab() -> None:
        """Selecting refresh from the AXE-tab palette calls ``action_refresh``."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
            patch.object(AceApp, "action_refresh") as refresh_mock,
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_e2e.py:123: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff064242580>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_palette_escape_dismisses_from_each_tab __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_escape_dismisses_from_each_tab() -> None:
        """Esc dismisses the palette on every tab without side effects."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_e2e.py:146: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff04789ef10>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________________ test_colon_opens_command_line_modal ______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_colon_opens_command_line_modal() -> None:
        """Pressing ``:`` from the Patches tab opens the Command Line panel."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_wiring.py:28: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047832d50>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________________ test_semicolon_opens_command_palette_modal __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_semicolon_opens_command_palette_modal() -> None:
        """Pressing ``;`` from the Patches tab opens the same palette modal."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_wiring.py:43: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0475c8050>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________________ test_palette_colon_hops_to_command_line ____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_colon_hops_to_command_line() -> None:
        """Typing ``:`` into an empty palette filter restores its exact draft."""
        from sase.ace.tui.command_line.input import CommandLineInput
        from sase.ace.tui.command_line.session import command_line_session_for
    
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_wiring.py:61: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07474cc80>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_palette_no_match_fallback_prefills_command_line _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_no_match_fallback_prefills_command_line() -> None:
        """Enter on a matchless filter opens the Command Line pre-filled."""
        from sase.ace.tui.command_line.input import CommandLineInput
    
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_wiring.py:88: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07474cc80>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_palette_escape_dismisses_without_side_effects ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_escape_dismisses_without_side_effects() -> None:
        """Esc closes the palette and leaves no app-state changes behind."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_wiring.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0479cd630>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________________ test_palette_executes_refresh_via_action ___________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_executes_refresh_via_action() -> None:
        """Filtering to refresh + Enter dispatches ``action_refresh``."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
            patch.object(AceApp, "action_refresh") as refresh_mock,
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_wiring.py:124: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047125b70>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________ test_palette_omits_inapplicable_axe_only_command_on_cls_tab __________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_omits_inapplicable_axe_only_command_on_cls_tab() -> None:
        """Stop-axe-and-quit is AXE-scoped — it must not appear from Patches filter."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_wiring.py:145: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074a446d0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_palette_context_uses_current_tab_badge __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_context_uses_current_tab_badge() -> None:
        """Switching to the Services tab and opening the palette shows the Services badge."""
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_wiring.py:175: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0751b1610>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_palette_filter_input_swallows_typing_no_action_dispatched ________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_palette_filter_input_swallows_typing_no_action_dispatched() -> None:
        """Typing 'q' into the palette filter must not dispatch ``action_quit``.
    
        Acceptance: ``;`` does not interfere with input widgets — the
        palette's filter input absorbs printable keys.
        """
        with (
            patch.object(AceApp, "_load_agents"),
            patch.object(AceApp, "_load_axe_status"),
            patch.object(AceApp, "action_quit") as quit_mock,
        ):
>           async with AcePage(
                query="test_feature",
                patches=[make_patch()],
            ) as page:

tests/test_command_palette_wiring.py:208: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0751b22d0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_action_open_command_palette_uses_real_catalog ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    def test_action_open_command_palette_uses_real_catalog() -> None:
        """The action filters the catalog through the live applicability."""
>       app = AceApp(auto_start_axe=False)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_command_palette_wiring.py:223: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff04859fcd0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_action_open_command_palette_dispatches_selection _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    def test_action_open_command_palette_dispatches_selection() -> None:
        """The on-dismiss callback resolves the spec id and runs the executor."""
>       app = AceApp(auto_start_axe=False)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_command_palette_wiring.py:244: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045508520>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________ test_action_open_command_palette_noop_on_cancel ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    def test_action_open_command_palette_noop_on_cancel() -> None:
        """Cancelling the palette (None result) runs no action."""
>       app = AceApp(auto_start_axe=False)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_command_palette_wiring.py:292: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074af82d0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_action_open_command_palette_unknown_id_is_silent _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    def test_action_open_command_palette_unknown_id_is_silent() -> None:
        """Selecting an id not in the catalog is a no-op (defensive)."""
>       app = AceApp(auto_start_axe=False)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_command_palette_wiring.py:311: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0457594f0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_extract_command_context_smoke_against_real_app ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    def test_extract_command_context_smoke_against_real_app() -> None:
        """Confirm the extractor works against a real AceApp instance."""
>       app = AceApp(auto_start_axe=False, initial_tab="changespecs")  # legacy tab id
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_command_palette_wiring.py:326: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074613260>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____ test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning ____
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

inline_publication = _Fixture(primary=PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_tagged_commit_publishes_a0/...th('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_tagged_commit_publishes_a0/plans/202608/inline.md'))

    def test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning(
        inline_publication: _Fixture,
    ) -> None:
        fixture = inline_publication
        cp = CommitCheckpoint(
            method="create_commit",
            payload={"message": _MESSAGE},
            cwd=str(fixture.primary),
            primary_revision=_REVISION,
            commit_sha=_REVISION,
            publication_agent=_AGENT,
        )
    
>       assert run_agent_publication_step(
            cp,
            "create_commit",
            checkpoint_save=lambda _cp: None,
            get_vcs_provider=lambda _cwd: pytest.fail("revision is already resolved"),
        )
E       AssertionError: assert False
E        +  where False = run_agent_publication_step(CommitCheckpoint(method='create_commit', payload={'message': 'feat: publish inline\n\nSASE_BEAD=sase-fa.1\nSASE_PLAN=p..._id=None, run_id=None, completed_steps=['publish_bead_pages', 'publish_prompt_archive'], created_at=1795856750.9828308), 'create_commit', checkpoint_save=<function test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning.<locals>.<lambda> at 0x7ff0746bdbc0>, get_vcs_provider=<function test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning.<locals>.<lambda> at 0x7ff0746be6c0>)

tests/test_commit_publication_inline.py:327: AssertionError
----------------------------- Captured stdout call -----------------------------
ℹ️ Commit publication selected inline: axe is not running.
❌ The primary commit succeeded, but agent publication failed before a retry 
could be confirmed: no committed first-party module named 
sase.agents_sync.inventory_scope. Run `sase stitch create --resume` to retry 
without creating another primary commit.
____________ TestGetMetaChangespecName.test_meta_changespec_direct _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

self = <tests.test_commit_workflow_changespec.TestGetMetaChangespecName object at 0x7ff0539042d0>

    def test_meta_changespec_direct(self) -> None:
>       from sase.ace.tui.actions.agents._notification_actions import (
            get_meta_changespec_name,
        )

tests/test_commit_workflow_changespec.py:414: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044a152c0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._notification_actions

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______ TestGetMetaChangespecName.test_meta_changespec_strips_whitespace _______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

self = <tests.test_commit_workflow_changespec.TestGetMetaChangespecName object at 0x7ff053904550>

    def test_meta_changespec_strips_whitespace(self) -> None:
>       from sase.ace.tui.actions.agents._notification_actions import (
            get_meta_changespec_name,
        )

tests/test_commit_workflow_changespec.py:422: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044b381e0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._notification_actions

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ TestGetMetaChangespecName.test_legacy_meta_new_cl _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

self = <tests.test_commit_workflow_changespec.TestGetMetaChangespecName object at 0x7ff0538ec8a0>

    def test_legacy_meta_new_cl(self) -> None:
>       from sase.ace.tui.actions.agents._notification_actions import (
            get_meta_changespec_name,
        )

tests/test_commit_workflow_changespec.py:430: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044a156d0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._notification_actions

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______ TestGetMetaChangespecName.test_legacy_meta_new_pr_with_changespec _______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

self = <tests.test_commit_workflow_changespec.TestGetMetaChangespecName object at 0x7ff0538ec9d0>

    def test_legacy_meta_new_pr_with_changespec(self) -> None:
>       from sase.ace.tui.actions.agents._notification_actions import (
            get_meta_changespec_name,
        )

tests/test_commit_workflow_changespec.py:438: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044a15400>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._notification_actions

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________ TestGetMetaChangespecName.test_returns_none_for_empty_output _________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

self = <tests.test_commit_workflow_changespec.TestGetMetaChangespecName object at 0x7ff053aa2450>

    def test_returns_none_for_empty_output(self) -> None:
>       from sase.ace.tui.actions.agents._notification_actions import (
            get_meta_changespec_name,
        )

tests/test_commit_workflow_changespec.py:452: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044a162b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._notification_actions

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________ TestGetMetaChangespecName.test_returns_none_for_none_output __________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

self = <tests.test_commit_workflow_changespec.TestGetMetaChangespecName object at 0x7ff053a11370>

    def test_returns_none_for_none_output(self) -> None:
>       from sase.ace.tui.actions.agents._notification_actions import (
            get_meta_changespec_name,
        )

tests/test_commit_workflow_changespec.py:460: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044a14820>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._notification_actions

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_run_detects_conflict_and_returns_conflict_code ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669972520912'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_run_detects_conflict_and_0')

    @patch(_PROVIDER_TARGET)
    def test_run_detects_conflict_and_returns_conflict_code(
        mock_get: MagicMock, artifacts_dir: Path
    ) -> None:
        provider = make_provider(
            dispatch_result=(False, "merge conflict"), is_conflict=False
        )
        provider.is_sync_in_progress.side_effect = [False, True]
        mock_get.return_value = provider
    
        payload: dict[str, Any] = {"message": "fix: bug", "files": ["a.py"]}
        wf = CommitWorkflow(payload, "create_commit")
    
>       assert wf.run() == RunResult.CONFLICT
               ^^^^^^^^

tests/test_commit_workflow_checkpointing.py:45: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044a155e0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
🔄 Dispatching create_commit to VCS provider...
____ test_no_staged_changes_conflict_checkpoint_marks_no_commit_dispatched _____
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669972528304'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_no_staged_changes_conflic0')

    @patch(_PROVIDER_TARGET)
    def test_no_staged_changes_conflict_checkpoint_marks_no_commit_dispatched(
        mock_get: MagicMock, artifacts_dir: Path
    ) -> None:
        provider = make_provider(
            dispatch_result=(False, "No staged changes to commit"), is_conflict=False
        )
        provider.is_sync_in_progress.side_effect = [False, True]
        mock_get.return_value = provider
    
        wf = CommitWorkflow({"message": "fix: bug"}, "create_commit")
    
>       assert wf.run() == RunResult.CONFLICT
               ^^^^^^^^

tests/test_commit_workflow_checkpointing.py:134: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046183fc0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
🔄 Dispatching create_commit to VCS provider...
_____________ test_run_failure_without_conflict_deletes_checkpoint _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669934230832'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_run_failure_without_confl0')

    @patch(_PROVIDER_TARGET)
    def test_run_failure_without_conflict_deletes_checkpoint(
        mock_get: MagicMock, artifacts_dir: Path
    ) -> None:
        provider = make_provider(
            dispatch_result=(False, "git add failed"), is_conflict=False
        )
        mock_get.return_value = provider
    
        wf = CommitWorkflow({"message": "fix: bug"}, "create_commit")
    
        with patch("sase.logs.run_log.log_event") as mock_log:
>           assert wf.run() == RunResult.FAILED
                   ^^^^^^^^

tests/test_commit_workflow_checkpointing.py:153: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044b39400>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
🔄 Dispatching create_commit to VCS provider...
_______ test_run_push_failure_after_local_commit_records_unpushed_marker _______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669978825056'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_run_push_failure_after_lo0')

    @patch(_PROVIDER_TARGET)
    def test_run_push_failure_after_local_commit_records_unpushed_marker(
        mock_get: MagicMock, artifacts_dir: Path
    ) -> None:
        provider = make_provider(
            dispatch_result=(
                False,
                "commit 1111111111111111111111111111111111111111 "
                "created locally; git push failed: refused",
            ),
            is_conflict=False,
        )
        provider.revision_id.side_effect = [
            "0" * 40,
            "1" * 40,
            "2" * 40,
        ]
        mock_get.return_value = provider
    
        with patch(
            "sase.workflows.commit.commit_tracking._resolve_commit_created_at",
            return_value=None,
        ):
>           assert CommitWorkflow({"message": "fix: bug"}, "create_commit").run() == (
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                RunResult.FAILED
            )

tests/test_commit_workflow_checkpointing.py:184: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046182530>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
🔄 Dispatching create_commit to VCS provider...
___ test_run_push_failure_reports_checkpoint_write_failure_but_keeps_marker ____
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669920852832'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_run_push_failure_reports_0')

    @patch(_PROVIDER_TARGET)
    def test_run_push_failure_reports_checkpoint_write_failure_but_keeps_marker(
        mock_get: MagicMock, artifacts_dir: Path
    ) -> None:
        provider = make_provider(
            dispatch_result=(
                False,
                "commit 1111111111111111111111111111111111111111 "
                "created locally; git push failed: refused",
            ),
            is_conflict=False,
        )
        provider.revision_id.side_effect = [
            "0" * 40,
            "1" * 40,
            "2" * 40,
        ]
        mock_get.return_value = provider
        real_save = checkpoint.checkpoint_save
    
        def save_until_unpushed(
            cp: checkpoint.CommitCheckpoint, path: str | None = None
        ) -> str | None:
            if cp.pushed is False:
                return None
            return real_save(cp, path)
    
        with (
            patch(
                "sase.workflows.commit.commit_tracking._resolve_commit_created_at",
                return_value=None,
            ),
            patch(
                "sase.workflows.commit._workflow_tracking.checkpoint_save",
                side_effect=save_until_unpushed,
            ),
            patch("sase.workflows.commit.workflow.print_status") as status,
        ):
>           assert CommitWorkflow({"message": "fix: bug"}, "create_commit").run() == (
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                RunResult.FAILED
            )

tests/test_commit_workflow_checkpointing.py:250: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044b38320>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
___ test_run_push_failure_reports_marker_write_failure_but_keeps_checkpoint ____
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669920841408'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_run_push_failure_reports_1')

    @patch(_PROVIDER_TARGET)
    def test_run_push_failure_reports_marker_write_failure_but_keeps_checkpoint(
        mock_get: MagicMock, artifacts_dir: Path
    ) -> None:
        provider = make_provider(
            dispatch_result=(
                False,
                "commit 1111111111111111111111111111111111111111 "
                "created locally; git push failed: refused",
            ),
            is_conflict=False,
        )
        provider.revision_id.side_effect = [
            "0" * 40,
            "1" * 40,
            "2" * 40,
        ]
        mock_get.return_value = provider
    
        with (
            patch(
                "sase.workflows.commit._workflow_tracking.write_result_marker",
                return_value=False,
            ),
            patch("sase.workflows.commit.workflow.print_status") as status,
        ):
>           assert CommitWorkflow({"message": "fix: bug"}, "create_commit").run() == (
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                RunResult.FAILED
            )

tests/test_commit_workflow_checkpointing.py:290: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044a15720>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
___ test_run_push_failure_reports_when_no_durable_recovery_evidence_written ____
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669920837712'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_run_push_failure_reports_2')

    @patch(_PROVIDER_TARGET)
    def test_run_push_failure_reports_when_no_durable_recovery_evidence_written(
        mock_get: MagicMock, artifacts_dir: Path
    ) -> None:
        provider = make_provider(
            dispatch_result=(
                False,
                "commit 1111111111111111111111111111111111111111 "
                "created locally; git push failed: refused",
            ),
            is_conflict=False,
        )
        provider.revision_id.side_effect = [
            "0" * 40,
            "1" * 40,
            "2" * 40,
        ]
        mock_get.return_value = provider
    
        with (
            patch(
                "sase.workflows.commit._workflow_tracking.checkpoint_save",
                return_value=None,
            ),
            patch(
                "sase.workflows.commit._workflow_tracking.write_result_marker",
                return_value=False,
            ),
            patch("sase.workflows.commit.workflow.print_status") as status,
        ):
>           assert CommitWorkflow({"message": "fix: bug"}, "create_commit").run() == (
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                RunResult.FAILED
            )

tests/test_commit_workflow_checkpointing.py:334: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0461df2f0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
________ test_pre_dispatch_checkpoint_has_post_mutation_payload_for_pr _________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669971545264'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_pre_dispatch_checkpoint_h0')

    @patch(_PROVIDER_TARGET)
    def test_pre_dispatch_checkpoint_has_post_mutation_payload_for_pr(
        mock_get: MagicMock,
        artifacts_dir: Path,
    ) -> None:
        """Checkpoint payload reflects PR prefix / tags applied before dispatch."""
        provider = make_provider(
            dispatch_result=(False, "merge conflict"), is_conflict=False
        )
        provider.is_sync_in_progress.side_effect = [False, True]
        mock_get.return_value = provider
    
        payload: dict[str, Any] = {"name": "feat", "message": "feat: x"}
        wf = CommitWorkflow(payload, "create_pull_request")
    
        def _mark_mutation(payload: dict, parent: str | None) -> None:
            payload["_mutated"] = True
    
        with (
            patch(_PROJECT_NAME_TARGET, return_value=None),
            patch("sase.workflows.commit.workflow.apply_project_pr_prefix"),
            patch(
                "sase.workflows.commit.workflow.append_pr_tags",
                side_effect=_mark_mutation,
            ),
            patch("sase.workflows.commit.workflow.build_pr_body"),
        ):
>           assert wf.run() == RunResult.CONFLICT
                   ^^^^^^^^

tests/test_commit_workflow_checkpointing.py:500: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044b6a2b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
🔄 Dispatching create_pull_request to VCS provider...
_____________ test_pre_dispatch_checkpoint_written_before_dispatch _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669966857088'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_pre_dispatch_checkpoint_w0')

    @patch(_PROVIDER_TARGET)
    def test_pre_dispatch_checkpoint_written_before_dispatch(
        mock_get: MagicMock, artifacts_dir: Path
    ) -> None:
        """The first save() is the pre-dispatch snapshot with no completed steps."""
        provider = make_provider(
            dispatch_result=(False, "merge conflict"), is_conflict=False
        )
        provider.is_sync_in_progress.side_effect = [False, True]
        mock_get.return_value = provider
    
        saves_before_dispatch: list[list[str]] = []
        dispatch_called = False
        real_save = checkpoint.checkpoint_save
    
        def spy_save(
            cp: checkpoint.CommitCheckpoint, path: str | None = None
        ) -> str | None:
            if not dispatch_called:
                saves_before_dispatch.append(list(cp.completed_steps))
            return real_save(cp, path)
    
        def _dispatch(*_args: object, **_kwargs: object) -> tuple[bool, str | None]:
            nonlocal dispatch_called
            dispatch_called = True
            return (False, "merge conflict")
    
        provider.create_commit.side_effect = _dispatch
    
        wf = CommitWorkflow({"message": "fix: checkpoint"}, "create_commit")
    
        with patch(
            "sase.workflows.commit._workflow_tracking.checkpoint_save", side_effect=spy_save
        ):
>           assert wf.run() == RunResult.CONFLICT
                   ^^^^^^^^

tests/test_commit_workflow_checkpointing.py:624: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0461e97c0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
🔄 Dispatching create_commit to VCS provider...
________ TestCommitWorkflowDispatch.test_provider_failure_returns_false ________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

self = <tests.test_commit_workflow_dispatch.TestCommitWorkflowDispatch object at 0x7ff0539016d0>
mock_get = <MagicMock name='get_vcs_provider' id='140669966857760'>
mock_provider = <MagicMock name='get_vcs_provider()' id='140670727805248'>

    @patch(_PROVIDER_TARGET)
    def test_provider_failure_returns_false(
        self, mock_get: MagicMock, mock_provider: MagicMock
    ) -> None:
        mock_provider.create_commit.return_value = (False, "git add failed")
        mock_provider.is_sync_in_progress.return_value = False
        mock_provider.get_conflicted_files.return_value = []
        mock_get.return_value = mock_provider
        wf = CommitWorkflow({"message": "test: provider failure"}, "create_commit")
    
        with patch(
            "sase.workflows.commit._workflow_tracking.close_assigned_bead_after_commit"
        ) as close_bead:
>           assert wf.run() == RunResult.FAILED
                   ^^^^^^^^

tests/test_commit_workflow_dispatch.py:258: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047a316d0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
🔄 Dispatching create_commit to VCS provider...
_ test_after_hook_skipped_for_proposals_and_failed_dispatches[create_commit-dispatch_result1] _
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140669935062384'>
method = 'create_commit', dispatch_result = (False, 'git add failed')
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_after_hook_skipped_for_pr0')

    @pytest.mark.parametrize(
        ("method", "dispatch_result"),
        [
            ("create_proposal", (True, "proposal.diff")),
            ("create_commit", (False, "git add failed")),
        ],
    )
    @patch(_PROVIDER_TARGET)
    def test_after_hook_skipped_for_proposals_and_failed_dispatches(
        mock_get: MagicMock,
        method: str,
        dispatch_result: tuple[bool, str],
        artifacts_dir: Path,
    ) -> None:
        provider = make_provider(dispatch_result=dispatch_result)
        mock_get.return_value = provider
    
        with patch("sase.workflows.commit.workflow.run_after_commit_hook") as after_hook:
>           CommitWorkflow({"message": "fix: bug"}, method).run()

tests/test_commit_workflow_hooks.py:123: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:303: in run
    from sase.workflows.commit.rebase_gate_coordinator import is_gate_blocked
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044ca6a80>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stdout call -----------------------------
⚠️ Local commands in 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml 
were skipped; run `sase config trust allow 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/sase.yml` 
after review.
🔄 Dispatching create_commit to VCS provider...
__________________ test_resume_failed_finalize_returns_failed __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140670723615984'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_resume_failed_finalize_re0')
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_resume_failed_finalize_re0')

    @patch(PROVIDER_TARGET)
    def test_resume_failed_finalize_returns_failed(
        mock_get: MagicMock, artifacts_dir: Path, tmp_path: Path
    ) -> None:
        provider = make_resume_provider(
            head_subject="fix: bug", finalize_result=(False, "push rejected")
        )
        mock_get.return_value = provider
    
        save_resume_checkpoint(cwd=str(tmp_path), payload={"message": "fix: bug"})
    
>       assert CommitWorkflow.resume() == RunResult.FAILED
               ^^^^^^^^^^^^^^^^^^^^^^^

tests/test_commit_workflow_resume_recovery.py:127: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:420: in resume
    return resume_commit_workflow(
src/sase/workflows/commit/workflow_resume.py:144: in resume_commit_workflow
    from sase.workflows.commit.rebase_gate_coordinator import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074bef250>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________ test_resume_push_failure_records_unpushed_marker _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

mock_get = <MagicMock name='get_vcs_provider' id='140670723735040'>
artifacts_dir = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_resume_push_failure_recor0')
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_resume_push_failure_recor0')

    @patch(PROVIDER_TARGET)
    def test_resume_push_failure_records_unpushed_marker(
        mock_get: MagicMock, artifacts_dir: Path, tmp_path: Path
    ) -> None:
        provider = make_resume_provider(
            head_subject="fix: bug",
            finalize_result=(
                False,
                "commit " + "1" * 40 + " created locally; git push failed: refused",
            ),
        )
        provider.revision_id.side_effect = ["1" * 40, "2" * 40]
        mock_get.return_value = provider
        save_resume_checkpoint(
            cwd=str(tmp_path),
            payload={"message": "fix: bug"},
            primary_revision="0" * 40,
            operation_id="op-resume-1",
        )
    
        with patch(
            "sase.workflows.commit.commit_tracking._resolve_commit_created_at",
            return_value=None,
        ):
>           assert CommitWorkflow.resume() == RunResult.FAILED
                   ^^^^^^^^^^^^^^^^^^^^^^^

tests/test_commit_workflow_resume_recovery.py:156: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workflows/commit/workflow.py:420: in resume
    return resume_commit_workflow(
src/sase/workflows/commit/workflow_resume.py:144: in resume_commit_workflow
    from sase.workflows.commit.rebase_gate_coordinator import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0747cd8b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.workflows.commit.rebase_gate_coordinator

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________________ test_bare_config_trust_prints_help ______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

capsys = <_pytest.capture.CaptureFixture object at 0x7ff046706750>

    def test_bare_config_trust_prints_help(
        capsys: pytest.CaptureFixture[str],
    ) -> None:
>       from sase.main.config_handler import handle_config_command

tests/test_config_local_trust_management.py:338: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045071db0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.main.config_handler

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________________ test_config_show_projects_public_axe_contract _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_config_show_projects_publ0')
capsys = <_pytest.capture.CaptureFixture object at 0x7ff0447a0d50>

    def test_config_show_projects_public_axe_contract(
        tmp_path: Path, capsys: pytest.CaptureFixture[str]
    ) -> None:
        """``sase config show`` prints the public AXE contract, not raw aliases."""
        global_config = tmp_path / "global"
        global_config.mkdir()
        (global_config / "sase.yml").write_text(
            yaml.dump({"axe": {"routines": {"checks": {"interval": 19}}}}),
            encoding="utf-8",
        )
        default = {
            "axe": {
                "lumberjacks": {
                    "checks": {
                        "description": "Run checks",
                        "interval": 5,
                        "chops": {},
                    }
                }
            }
        }
    
>       from sase.main.config_handler import handle_config_command

tests/test_config_merge.py:195: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0450b4b90>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.main.config_handler

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________________________ test_cli_health_human_ok ___________________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff083b9fb60>
capsys = <_pytest.capture.CaptureFixture object at 0x7ff0743e9f50>

    def test_cli_health_human_ok(
        monkeypatch: pytest.MonkeyPatch, capsys: pytest.CaptureFixture[str]
    ) -> None:
        _install_fake_extension(monkeypatch)
        monkeypatch.setattr(sys, "argv", ["sase", "core", "health"])
    
>       code = _run_cli()
               ^^^^^^^^^^

tests/test_core_health.py:347: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/test_core_health.py:335: in _run_cli
    main()
src/sase/main/entry.py:19: in main
    _main(hit)
src/sase/main/entry.py:116: in _main
    from ._dispatch_initial import dispatch_initial_commands
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff088fa30c0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.main._dispatch_initial

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________________________ test_cli_health_json_ok ____________________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff083b9faf0>
capsys = <_pytest.capture.CaptureFixture object at 0x7ff0743e8e50>

    def test_cli_health_json_ok(
        monkeypatch: pytest.MonkeyPatch, capsys: pytest.CaptureFixture[str]
    ) -> None:
        _install_fake_extension(monkeypatch, version="9.9.9")
        monkeypatch.setattr(sys, "argv", ["sase", "core", "health", "--json"])
    
>       code = _run_cli()
               ^^^^^^^^^^

tests/test_core_health.py:361: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/test_core_health.py:335: in _run_cli
    main()
src/sase/main/entry.py:19: in main
    _main(hit)
src/sase/main/entry.py:116: in _main
    from ._dispatch_initial import dispatch_initial_commands
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044d05040>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.main._dispatch_initial

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________________ test_cli_health_short_json_flag ________________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff083b9fe70>
capsys = <_pytest.capture.CaptureFixture object at 0x7ff0743ea750>

    def test_cli_health_short_json_flag(
        monkeypatch: pytest.MonkeyPatch, capsys: pytest.CaptureFixture[str]
    ) -> None:
        _install_fake_extension(monkeypatch)
        monkeypatch.setattr(sys, "argv", ["sase", "core", "health", "-j"])
    
>       code = _run_cli()
               ^^^^^^^^^^

tests/test_core_health.py:376: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/test_core_health.py:335: in _run_cli
    main()
src/sase/main/entry.py:19: in main
    _main(hit)
src/sase/main/entry.py:116: in _main
    from ._dispatch_initial import dispatch_initial_commands
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044d071b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.main._dispatch_initial

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________________ test_cli_health_rust_missing_exits_nonzero __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff083b9fe00>
capsys = <_pytest.capture.CaptureFixture object at 0x7ff0472b2750>

    def test_cli_health_rust_missing_exits_nonzero(
        monkeypatch: pytest.MonkeyPatch, capsys: pytest.CaptureFixture[str]
    ) -> None:
        _force_import_failure(monkeypatch, ImportError("no sase_core_rs"))
        monkeypatch.setattr(sys, "argv", ["sase", "core", "health", "-j"])
    
>       code = _run_cli()
               ^^^^^^^^^^

tests/test_core_health.py:390: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/test_core_health.py:335: in _run_cli
    main()
src/sase/main/entry.py:19: in main
    _main(hit)
src/sase/main/entry.py:116: in _main
    from ._dispatch_initial import dispatch_initial_commands
tests/test_core_health.py:139: in _raising
    return real_import(name, *args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044d05400>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.main._dispatch_initial

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_goal_fast_path_uses_shared_fetch_spawn __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff04584ea50>

    def test_goal_fast_path_uses_shared_fetch_spawn(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        import sase.goals.fetch_worker as fetch_module
>       import sase.main.goal_fast_path as fast_path_module

tests/test_detach_scope_background_workers.py:447: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07464d4f0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.main.goal_fast_path

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_monitor_supervisor_bootstrap_uses_detach_scope ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047206ac0>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_monitor_supervisor_bootst0')

    def test_monitor_supervisor_bootstrap_uses_detach_scope(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
>       import sase.monitor.spawn as spawn_module

tests/test_detach_scope_bootstrap.py:121: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07463b890>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.monitor.spawn

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______ test_monitor_supervisor_bootstrap_uses_pid_file_for_systemd_scope _______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff04584c910>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_monitor_supervisor_bootst1')

    def test_monitor_supervisor_bootstrap_uses_pid_file_for_systemd_scope(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
>       import sase.monitor.spawn as spawn_module

tests/test_detach_scope_bootstrap.py:171: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07463a080>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.monitor.spawn

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_reported_ace_proc_prompt_uses_typed_admission ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047204ad0>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_reported_ace_proc_prompt_0')

    def test_reported_ace_proc_prompt_uses_typed_admission(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pytest.importorskip("sase_core_rs")
        prompt = '#gh:sase %proc("echo hello && sleep 20 && world")'
>       captured = _run_launch_query(
            monkeypatch, tmp_path, prompt, payload={"allow_force_reuse": True}
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:174: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
_______ test_direct_proc_forms_yield_proc_unit[%proc("echo positional")] _______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047206660>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_direct_proc_forms_yield_p0')
prompt = '%proc("echo positional")'

    @pytest.mark.parametrize(
        "prompt",
        [
            '%proc("echo positional")',
            '%proc(python="print(\'ready\')", timeout="20m", label="Preflight")',
            '%proc(timeout="20m", idle_timeout="5m")::\n\n```bash\necho fenced\n```\n',
        ],
    )
    def test_direct_proc_forms_yield_proc_unit(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path, prompt: str
    ) -> None:
        pytest.importorskip("sase_core_rs")
>       captured = _run_launch_query(monkeypatch, tmp_path, prompt)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:210: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
_ test_direct_proc_forms_yield_proc_unit[%proc(python="print('ready')", timeout="20m", label="Preflight")] _
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047206ac0>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_direct_proc_forms_yield_p1')
prompt = '%proc(python="print(\'ready\')", timeout="20m", label="Preflight")'

    @pytest.mark.parametrize(
        "prompt",
        [
            '%proc("echo positional")',
            '%proc(python="print(\'ready\')", timeout="20m", label="Preflight")',
            '%proc(timeout="20m", idle_timeout="5m")::\n\n```bash\necho fenced\n```\n',
        ],
    )
    def test_direct_proc_forms_yield_proc_unit(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path, prompt: str
    ) -> None:
        pytest.importorskip("sase_core_rs")
>       captured = _run_launch_query(monkeypatch, tmp_path, prompt)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:210: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
_ test_direct_proc_forms_yield_proc_unit[%proc(timeout="20m", idle_timeout="5m")::\n\n```bash\necho fenced\n```\n] _
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047204440>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_direct_proc_forms_yield_p2')
prompt = '%proc(timeout="20m", idle_timeout="5m")::\n\n```bash\necho fenced\n```\n'

    @pytest.mark.parametrize(
        "prompt",
        [
            '%proc("echo positional")',
            '%proc(python="print(\'ready\')", timeout="20m", label="Preflight")',
            '%proc(timeout="20m", idle_timeout="5m")::\n\n```bash\necho fenced\n```\n',
        ],
    )
    def test_direct_proc_forms_yield_proc_unit(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path, prompt: str
    ) -> None:
        pytest.importorskip("sase_core_rs")
>       captured = _run_launch_query(monkeypatch, tmp_path, prompt)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:210: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
______________ test_direct_proc_queue_fields_round_trip_from_rust ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0457f1240>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_direct_proc_queue_fields_0')

    def test_direct_proc_queue_fields_round_trip_from_rust(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pytest.importorskip("sase_core_rs")
>       captured = _run_launch_query(
            monkeypatch,
            tmp_path,
            '%q(1, priority=4, weight=0.25)\n%proc("just check")',
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:220: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
_______________________ test_direct_if_admits_agent_unit _______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0457f06e0>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_direct_if_admits_agent_un0')

    def test_direct_if_admits_agent_unit(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pytest.importorskip("sase_core_rs")
        prompt = "%if::\n\n```bash\ntest -f pyproject.toml\n```\nDo the review"
>       captured = _run_launch_query(monkeypatch, tmp_path, prompt)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:281: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
_______________________ test_mixed_agent_proc_wait_graph _______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0457f01a0>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_mixed_agent_proc_wait_gra0')

    def test_mixed_agent_proc_wait_graph(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pytest.importorskip("sase_core_rs")
        prompt = '%proc("echo first")\n---\n%wait\n%id:reviewer\nReview'
>       captured = _run_launch_query(monkeypatch, tmp_path, prompt)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:293: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
_____________ test_invalid_typed_syntax_fails_before_agent_launch ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044deb850>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_invalid_typed_syntax_fail0')

    def test_invalid_typed_syntax_fails_before_agent_launch(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pytest.importorskip("sase_core_rs")
>       captured = _run_launch_query(
            monkeypatch, tmp_path, "%proc\nDo work", capture_typed=True
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:305: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
_________________ test_literal_proc_mentions_keep_legacy_path __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044de9a90>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_literal_proc_mentions_kee0')

    def test_literal_proc_mentions_keep_legacy_path(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        fenced = '```text\n%proc("echo hello")\n```\nDo work'
>       captured = _run_launch_query(
            monkeypatch, tmp_path, fenced, expect_launch_agents=True
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:318: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
_______________ test_plain_prompt_keeps_legacy_and_launch_units ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044de9400>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_plain_prompt_keeps_legacy0')

    def test_plain_prompt_keeps_legacy_and_launch_units(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
>       captured = _run_launch_query(
            monkeypatch,
            tmp_path,
            "one\n---\ntwo",
            payload={
                "launch_units": [
                    {
                        "prompt": "one",
                        "template_group": "macro:team:0",
                        "swarm_macros": ["team"],
                    }
                ]
            },
            expect_launch_agents=True,
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:342: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
___________________ test_force_reuse_without_typed_directive ___________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
>           module_name, attr = _LAZY_EXPORTS[name]
                                ^^^^^^^^^^^^^^^^^^^
E           KeyError: 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:58: KeyError

The above exception was the direct cause of the following exception:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff083971e80>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_force_reuse_without_typed0')

    def test_force_reuse_without_typed_directive(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        from types import SimpleNamespace
    
        monkeypatch.setattr(
            "sase.agent.force_reuse_launch.plan_force_reuse_launch",
            lambda query: SimpleNamespace(
                rewritten_prompt="%id:foo\nDo work", segment_envs=None
            ),
        )
        monkeypatch.setattr(
            "sase.agent.force_reuse_launch.apply_force_reuse_launch", lambda plan: None
        )
>       captured = _run_launch_query(
            monkeypatch,
            tmp_path,
            "%id:!foo\nDo work",
            payload={"allow_force_reuse": True},
            expect_launch_agents=True,
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:377: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:145: in _run_launch_query
    stack.enter_context(
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:530: in enter_context
    result = _enter(cm)
             ^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1494: in __enter__
    self.target = self.getter()
                  ^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pkgutil.py:473: in resolve_name
    result = getattr(result, p)
             ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'direct_typed_launch'

    def __getattr__(name: str) -> Any:
        try:
            module_name, attr = _LAZY_EXPORTS[name]
        except KeyError as error:
>           raise AttributeError(
                f"module {__name__!r} has no attribute {name!r}"
            ) from error
E           AttributeError: module 'sase.agent' has no attribute 'direct_typed_launch'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/__init__.py:60: AttributeError
_______________ test_explicit_vcs_target_wins_over_home_context ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047206ac0>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_explicit_vcs_target_wins_0')

    def test_explicit_vcs_target_wins_over_home_context(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pytest.importorskip("sase_core_rs")
        from sase.agent.launch_cwd_common import _KnownProjectVcsLaunchRef
    
        monkeypatch.setattr(
            "sase.agent.launch_cwd_common.resolve_known_project_vcs_launch_ref",
            lambda prompt: (
                _KnownProjectVcsLaunchRef(
                    "gh", "sase", str(tmp_path), str(tmp_path / "sase.sase")
                )
                if "#gh:sase" in prompt
                else None
            ),
        )
        monkeypatch.setattr(
            "sase.main.utils.ensure_project_file_and_get_workspace_num",
            lambda create_missing=False: (None, None, None),
        )
>       captured = _run_launch_query(
            monkeypatch,
            tmp_path,
            '#gh:sase %proc("echo hello")',
            selected_project=None,
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:409: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:159: in _run_launch_query
    launch_query(query)
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/main/query_handler/_launch.py:311: in launch_query
    _dispatch_direct_typed_launch_if_active(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/main/query_handler/_launch.py:443: in _dispatch_direct_typed_launch_if_active
    from sase.agent.direct_typed_launch import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0475f3d90>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.agent.direct_typed_launch

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tools/_check_rebase_imports.py:235: ModuleNotFoundError
________________ test_direct_bundle_resumes_after_blocked_wait _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_direct_bundle_resumes_aft0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff083973540>

    def test_direct_bundle_resumes_after_blocked_wait(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        pytest.importorskip("sase_core_rs")
>       from sase.agent.direct_typed_launch import _write_direct_typed_launch_bundle

tests/test_direct_typed_launch.py:424: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074fda940>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.agent.direct_typed_launch

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_direct_proc_bundle_coordinator_completion_does_not_notify ________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_direct_proc_bundle_coordi0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff083973b60>

    def test_direct_proc_bundle_coordinator_completion_does_not_notify(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pytest.importorskip("sase_core_rs")
>       from sase.agent.direct_typed_launch import _write_direct_typed_launch_bundle

tests/test_direct_typed_launch.py:505: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0475f2710>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.agent.direct_typed_launch

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_isolated_direct_bash_proc_settles_without_agent _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0485c00c0>
tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_isolated_direct_bash_proc0')

    def test_isolated_direct_bash_proc_settles_without_agent(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pytest.importorskip("sase_core_rs")
        from sase.main.query_handler._launch import launch_query
        from sase.procs import wait_for_proc
    
        monkeypatch.setenv("SASE_HOME", str(tmp_path / "home"))
        monkeypatch.chdir(tmp_path)
        monkeypatch.delenv("SASE_AGENT", raising=False)
        monkeypatch.delenv("SASE_AGENT_NAME", raising=False)
        marker = tmp_path / "ran.txt"
        prompt = (
            f'%proc(bash="printf ready > {marker}", workspace="false", cwd="{tmp_path}")'
        )
        emit = MagicMock()
        request = DurableOperationRequest(operation=RUN_LAUNCH, payload={"prompt": prompt})
        with (
            patch("sase.ops.cli.load_request", return_value=request),
            patch(
                "sase.agent.prompt_inputs.missing_required_input_names",
                return_value=[],
            ),
            patch(
                "sase.macro.unresolved.scan_query_for_unresolved_references",
                return_value=[],
            ),
            patch("sase.ops.commands.run.emit_run_launch_result", emit),
            patch(
                "sase.notification_gates.service.create_gate",
                side_effect=AssertionError("LaunchApproval must not be created"),
            ),
            patch(
                "sase.agent.launcher.spawn_agent_subprocess",
                side_effect=AssertionError("LLM must not be invoked"),
            ),
        ):
            with pytest.raises(SystemExit) as exc_info:
>               launch_query(prompt)

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_direct_typed_launch.py:616: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/main/query_handler/_launch.py:311: in launch_query
    _dispatch_direct_typed_launch_if_active(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/main/query_handler/_launch.py:443: in _dispatch_direct_typed_launch_if_active
    from sase.agent.direct_typed_launch import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074d0d540>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.agent.direct_typed_launch

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tools/_check_rebase_imports.py:235: ModuleNotFoundError
______ test_hydrate_ref_resolves_exact_commit_bypassing_collection_window ______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0485723c0>

    async def test_hydrate_ref_resolves_exact_commit_bypassing_collection_window(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A never-collected commit's facts are stored without touching the display.
    
        The Acquire step keeps hydrated facts outside the displayed timeline so
        the later Context step can build a repo-and-day window whose
        re-collection fetches the commit through the normal collection path.
        """
        result = _result()
>       page, pane = await _mounted_pane(monkeypatch, result)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_commits_pane_grouping.py:117: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/test_commits_pane_grouping.py:30: in _mounted_pane
    await page.__aenter__()
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff075150d70>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_hydrate_ref_reports_absent_for_unresolvable_sha _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff048570d00>

    async def test_hydrate_ref_reports_absent_for_unresolvable_sha(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """An ambiguous/unknown sha is an authoritative miss, not a load failure."""
        result = _result()
>       page, pane = await _mounted_pane(monkeypatch, result)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_commits_pane_grouping.py:193: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/test_commits_pane_grouping.py:30: in _mounted_pane
    await page.__aenter__()
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07516aad0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______ test_commits_pilot_drives_live_filter_bar_detail_copy_and_toggles _______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044de84b0>

    async def test_commits_pilot_drives_live_filter_bar_detail_copy_and_toggles(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        result = _result()
        calls: list[dict[str, Any]] = []
        collector_threads: list[int] = []
        diff_calls: list[str] = []
        copied: list[str] = []
        event_loop_thread = threading.get_ident()
    
        def collect(**kwargs: Any) -> VcsLogResult:
            collector_threads.append(threading.get_ident())
            calls.append(kwargs)
            return result
    
        def load_diff(spec: Any) -> str:
            diff_calls.append(spec.sha)
            return _DIFF
    
        monkeypatch.setattr(commits_module, "run_vcs_log", collect)
        monkeypatch.setattr(commits_module, "load_commit_diff_text", load_diff)
        monkeypatch.setattr(
            "sase.ace.tui.actions.clipboard._delivery.copy_to_system_clipboard",
            lambda value: copied.append(value) or True,
        )
    
>       async with AcePage(initial_tab="patches") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_commits_pane_interactions.py:66: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07462dc20>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________ test_commits_refresh_override_drives_action_footer_and_help __________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044de95c0>

    async def test_commits_refresh_override_drives_action_footer_and_help(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        result = _result()
        calls: list[dict[str, Any]] = []
        monkeypatch.setattr(
            "sase.config.load_merged_config",
            lambda: {"ace": {"keymaps": {"app": {"commits_refresh": "f2"}}}},
        )
        monkeypatch.setattr(
            commits_module,
            "run_vcs_log",
            lambda **kwargs: calls.append(kwargs) or result,
        )
        monkeypatch.setattr(commits_module, "load_commit_diff_text", lambda _spec: _DIFF)
    
>       async with AcePage(initial_tab="patches") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_commits_pane_interactions.py:261: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0751f8be0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______ test_commit_fetch_task_uses_visible_project_name_and_matching_file ______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044deb230>

    async def test_commit_fetch_task_uses_visible_project_name_and_matching_file(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        result = _result()
        calls: list[dict[str, Any]] = []
    
        def collect(**kwargs: Any) -> VcsLogResult:
            calls.append(kwargs)
            return result
    
        monkeypatch.setattr(commits_module, "run_vcs_log", collect)
        monkeypatch.setattr(commits_module, "load_commit_diff_text", lambda _spec: "")
    
>       async with AcePage(initial_tab="patches") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_commits_pane_interactions.py:312: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff075124b90>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_commits_cycle_merges_updates_query_and_recollects ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044dea970>

    async def test_commits_cycle_merges_updates_query_and_recollects(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        result = _result()
        calls: list[dict[str, Any]] = []
        monkeypatch.setattr(
            commits_module,
            "run_vcs_log",
            lambda **kwargs: calls.append(kwargs) or result,
        )
        monkeypatch.setattr(commits_module, "load_commit_diff_text", lambda _spec: _DIFF)
    
>       async with AcePage(initial_tab="patches") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_commits_pane_interactions.py:351: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff075124960>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______ test_commits_timeline_mounted_rows_stay_one_line_with_jump_hints _______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047f42890>

    async def test_commits_timeline_mounted_rows_stay_one_line_with_jump_hints(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        result = _result()
        monkeypatch.setattr(commits_module, "run_vcs_log", lambda **_kwargs: result)
        monkeypatch.setattr(commits_module, "load_commit_diff_text", lambda _spec: "")
    
>       async with AcePage(initial_tab="patches", size=(80, 30)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_commits_pane_rendering.py:356: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff048107890>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_alternate_opener_ping_pongs_between_exactly_two_sections _________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047f42350>

    async def test_alternate_opener_ping_pongs_between_exactly_two_sections(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _created, calls = _patch_stub_panes(monkeypatch)
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_alternate_tab.py:25: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074b274d0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________ test_single_section_visited_leaves_opener_inert ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047f42a50>

    async def test_single_section_visited_leaves_opener_inert(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _created, calls = _patch_stub_panes(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_alternate_tab.py:53: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07460bd90>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________ test_seeded_alternate_survives_close_and_reopen ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff048522d60>

    async def test_seeded_alternate_survives_close_and_reopen(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_stub_panes(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_alternate_tab.py:74: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074b27f70>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______ test_custom_opener_drives_alternate_jump_and_is_shown_in_footer ________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0485225f0>

    async def test_custom_opener_drives_alternate_jump_and_is_shown_in_footer(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setattr(
            "sase.config.load_merged_config",
            lambda: {"ace": {"keymaps": {"app": {"open_config_center": "f2"}}}},
        )
        monkeypatch.setattr(AceApp, "_schedule_axe_async_refresh", lambda self: None)
        _patch_stub_panes(monkeypatch)
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_alternate_tab.py:110: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff07433d1d0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____ test_literal_opener_with_alternate_available_still_types_and_stays_put ____
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0457f3bd0>

    async def test_literal_opener_with_alternate_available_still_types_and_stays_put(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setattr(
            ConfigCenterModal,
            "_create_pane",
            lambda _self, tab: _InputPane(tab),
        )
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_alternate_tab.py:139: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044dc5f40>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____ test_failed_alternate_jump_leaves_history_unchanged_and_is_retryable _____
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0457f33f0>

    async def test_failed_alternate_jump_leaves_history_unchanged_and_is_retryable(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        attempts = 0
    
        def create(_self: ConfigCenterModal, tab: CenterTab) -> _StubPane:
            nonlocal attempts
            attempts += 1
            if attempts == 2:
                raise RuntimeError("synthetic alternate-jump failure")
            return _StubPane(tab)
    
        monkeypatch.setattr(ConfigCenterModal, "_create_pane", create)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_alternate_tab.py:173: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074b16760>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____ test_footer_hidden_on_home_and_reflects_alternate_once_a_tab_is_active ____
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0457f2c10>

    async def test_footer_hidden_on_home_and_reflects_alternate_once_a_tab_is_active(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_stub_panes(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_alternate_tab.py:205: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff075138640>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_footer_click_navigates_to_the_alternate_section _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff07519a2e0>

    async def test_footer_click_navigates_to_the_alternate_section(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_stub_panes(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_alternate_tab.py:232: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff074b16940>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________ test_persisted_file_contains_both_lines_in_order _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0456b8670>

    async def test_persisted_file_contains_both_lines_in_order(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_stub_panes(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_alternate_tab.py:251: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047421220>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_repeated_opener_without_history_keeps_one_zero_pane_home _________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044d52350>

    async def test_repeated_opener_without_history_keeps_one_zero_pane_home(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        def fail_create(_self: ConfigCenterModal, _tab: CenterTab) -> _StubPane:
            raise AssertionError("an absent resume target must not construct a pane")
    
        monkeypatch.setattr(ConfigCenterModal, "_create_pane", fail_create)
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:35: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02ee3e490>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_generic_reopen_is_home_first_then_repeated_opener_resumes ________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff048290910>

    async def test_generic_reopen_is_home_first_then_repeated_opener_resumes(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _created, calls = _patch_stub_panes(monkeypatch)
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:69: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0454c3b10>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____ test_switching_changes_resume_target_and_home_only_close_retains_it ______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047f90ad0>

    async def test_switching_changes_resume_target_and_home_only_close_retains_it(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_stub_panes(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0454ed090>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________ test_direct_entry_establishes_resume_target_after_success ___________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff074b02970>

    async def test_direct_entry_establishes_resume_target_after_success(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_stub_panes(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:136: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02ee52bc0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_new_process_loads_remembered_admin_center_section ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0745155c0>

    async def test_new_process_loads_remembered_admin_center_section(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_stub_panes(monkeypatch)
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:158: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0454dc320>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________ test_persisted_tab_seeds_home_and_repeated_opener_resume ___________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0464b0b40>

    async def test_persisted_tab_seeds_home_and_repeated_opener_resume(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        save_admin_center_tab_history(AdminCenterTabHistory(current="procs"))
        _created, calls = _patch_stub_panes(monkeypatch)
    
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:198: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02ee53fc0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________ test_invalid_persisted_tab_keeps_no_history_home _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0449c2900>

    async def test_invalid_persisted_tab_keeps_no_history_home(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        path = config_center_state._admin_center_last_tab_path()
        path.parent.mkdir(parents=True, exist_ok=True)
        path.write_text("missing\n")
    
        def _fail_create(_self: ConfigCenterModal, _tab: CenterTab) -> _StubPane:
            raise AssertionError("invalid persisted state must not construct a pane")
    
        monkeypatch.setattr(ConfigCenterModal, "_create_pane", _fail_create)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:228: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0454babc0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______ test_blocked_write_keeps_navigation_responsive_and_persists_latest ______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0485eb770>

    async def test_blocked_write_keeps_navigation_responsive_and_persists_latest(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_stub_panes(monkeypatch)
        started = threading.Event()
        release = threading.Event()
        writes: list[AdminCenterTabHistory] = []
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:251: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0454ed900>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_write_failure_is_nonfatal_and_same_tab_can_retry _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0449c03d0>

    async def test_write_failure_is_nonfatal_and_same_tab_can_retry(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_stub_panes(monkeypatch)
        attempts: list[AdminCenterTabHistory] = []
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:299: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0454d0d70>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_failed_resume_retains_prior_target_and_remains_retryable _________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0449c3070>

    async def test_failed_resume_retains_prior_target_and_remains_retryable(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        attempts = 0
    
        def create(_self: ConfigCenterModal, tab: CenterTab) -> _StubPane:
            nonlocal attempts
            attempts += 1
            if attempts == 1:
                raise RuntimeError("synthetic resume failure")
            return _StubPane(tab)
    
        monkeypatch.setattr(ConfigCenterModal, "_create_pane", create)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:352: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046625540>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_custom_opener_opens_home_resumes_and_is_displayed ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0449c3700>

    async def test_custom_opener_opens_home_resumes_and_is_displayed(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setattr(
            "sase.config.load_merged_config",
            lambda: {"ace": {"keymaps": {"app": {"open_config_center": "f2"}}}},
        )
        monkeypatch.setattr(AceApp, "_schedule_axe_async_refresh", lambda self: None)
        _patch_stub_panes(monkeypatch)
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:379: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0454d3c00>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________ test_literal_opener_remains_typeable_and_cannot_nest_modal __________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0449c37e0>

    async def test_literal_opener_remains_typeable_and_cannot_nest_modal(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setattr(
            ConfigCenterModal,
            "_create_pane",
            lambda _self, tab: _InputPane(tab),
        )
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_center_resume.py:402: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0466830c0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_ace_app_reuses_one_session_state_across_modals ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_ace_app_reuses_one_session_state_across_modals() -> None:
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_session.py:37: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0464d50e0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_home_only_open_does_not_create_panes_or_mutate_bookmarks _________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_home_only_open_does_not_create_panes_or_mutate_bookmarks() -> None:
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_session.py:57: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0466884b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_distinct_ace_apps_do_not_share_session_state _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_distinct_ace_apps_do_not_share_session_state() -> None:
>       async with AcePage(initial_tab="agents") as first_page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_session.py:75: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046688230>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_home_tab_directions_and_digits_mount_only_requested_panes ________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff02ef630e0>

    async def test_home_tab_directions_and_digits_mount_only_requested_panes(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        created, calls = _patch_stub_panes(monkeypatch)
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_tabs.py:265: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0464dc4b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________ test_landing_compact_class_tracks_viewport_size ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_landing_compact_class_tracks_viewport_size() -> None:
>       async with AcePage(query="!!!", patches=[], size=(120, 40)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_center_tabs.py:369: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045f8a8a0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_chezmoi_write_applies_home_target_not_source _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_chezmoi_write_applies_hom0')

    async def test_chezmoi_write_applies_home_target_not_source(tmp_path: Path) -> None:
        """A chezmoi-backed write runs ``chezmoi apply`` on the home target path.
    
        Regression: the modal previously handed the chezmoi *source* path to
        ``chezmoi apply``, which rejects it as "not in source state". The apply must
        receive the original home target (``plan.write_plan.file``).
        """
        view, user_file = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
        field = view.fields_by_path["timezone"]
        home_target = str(user_file)
        source_path = str(
            tmp_path / "chezmoi" / "home" / "dot_config" / "sase" / "sase.yml"
        )
    
        plan = EditPlanResult(
            schema_version=1,
            write_plan=ConfigWritePlan(
                file=home_target,
                layer="user",
                key_path=("timezone",),
                op="set",
                has_value=True,
                new_value="UTC",
            ),
            candidate_config={},
            effective_preview=ConfigEffectivePreview(
                path="timezone",
                has_before=True,
                before="US/Pacific",
                has_after=True,
                after="UTC",
                changed=True,
            ),
            validation=(),
            diagnostics=(),
            target_path=source_path,
            used_chezmoi=True,
            current_text="timezone: US/Pacific\n",
            new_text="timezone: UTC\n",
            text_diff="@@ -1 +1 @@\n-timezone: US/Pacific\n+timezone: UTC\n",
        )
        applied = AppliedResult(
            path=source_path,
            op="set",
            key_path=("timezone",),
            created=False,
            used_chezmoi=True,
        )
        apply_chezmoi_mock = MagicMock(
            return_value=subprocess.CompletedProcess([], 0, stdout="", stderr="")
        )
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_chezmoi_widget.py:79: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045d6f6b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________________ test_edit_string_writes_to_target _______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_edit_string_writes_to_tar0')

    async def test_edit_string_writes_to_target(tmp_path: Path) -> None:
        view, user_file = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
        field = view.fields_by_path["timezone"]
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_editors_widget.py:27: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0460f2b20>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_edit_back_from_preview_returns_to_edit __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_edit_back_from_preview_re0')

    async def test_edit_back_from_preview_returns_to_edit(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_editors_widget.py:49: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045f19040>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_preview_scroll_keys_move_preview_region _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_preview_scroll_keys_move_0')

    async def test_preview_scroll_keys_move_preview_region(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage(size=(120, 24)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_edit_modal_editors_widget.py:63: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045dbc870>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________________________ test_bool_toggle_and_write __________________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_bool_toggle_and_write0')

    async def test_bool_toggle_and_write(tmp_path: Path) -> None:
        view, user_file = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
        field = view.fields_by_path["use_chezmoi"]
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_editors_widget.py:98: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0460e6300>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________________ test_enum_navigation_digits_and_space _____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_enum_navigation_digits_an0')

    async def test_enum_navigation_digits_and_space(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {})
        field = view.fields_by_path["mode"]
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_editors_widget.py:116: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045d1c8c0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________________ test_bool_digit_picks_visible_option _____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_bool_digit_picks_visible_0')

    async def test_bool_digit_picks_visible_option(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {})
        field = view.fields_by_path["use_chezmoi"]
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_editors_widget.py:136: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045d4a3a0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________________ test_scalar_input_selects_all_on_open _____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_scalar_input_selects_all_0')

    async def test_scalar_input_selects_all_on_open(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_editors_widget.py:148: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045de9130>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________________ test_multiline_string_uses_textarea ______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_multiline_string_uses_tex0')

    async def test_multiline_string_uses_textarea(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_editors_widget.py:157: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045dea1c0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________________ test_yaml_textarea_uses_yaml_language _____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_yaml_textarea_uses_yaml_l0')

    async def test_yaml_textarea_uses_yaml_language(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"linked_repos": [{"name": "core"}]})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_editors_widget.py:167: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045cf0280>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_large_yaml_value_keeps_editor_and_hints_visible _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_large_yaml_value_keeps_ed0')

    async def test_large_yaml_value_keeps_editor_and_hints_visible(
        tmp_path: Path,
    ) -> None:
        large_value = large_lumberjack_value()
        view, _ = config_edit_view(tmp_path, {"ace": {"lumberjack": large_value}})
>       async with AcePage(size=(120, 40)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_edit_modal_layout_widget.py:27: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045cf31b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________ test_expanded_class_tracks_multiline_preview_and_reset_states _________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_expanded_class_tracks_mul0')

    async def test_expanded_class_tracks_multiline_preview_and_reset_states(
        tmp_path: Path,
    ) -> None:
        large_value = large_lumberjack_value()
        view, _ = config_edit_view(tmp_path, {"ace": {"lumberjack": large_value}})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_layout_widget.py:50: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045c0da40>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________________ test_cycle_scope_changes_target ________________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_cycle_scope_changes_targe0')

    async def test_cycle_scope_changes_target(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_scope_widget.py:21: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045c75130>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_scope_selector_row_pick_changes_target __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_scope_selector_row_pick_c0')

    async def test_scope_selector_row_pick_changes_target(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_scope_widget.py:38: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045c77ed0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_new_overlay_switches_scope_to_created_overlay ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_new_overlay_switches_scop0')

    async def test_new_overlay_switches_scope_to_created_overlay(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_scope_widget.py:50: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045c89ae0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________________ test_reset_to_default_plans_unset _______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_reset_to_default_plans_un0')

    async def test_reset_to_default_plans_unset(tmp_path: Path) -> None:
        view, user_file = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_validation_widget.py:24: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045ce9220>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________________ test_client_constraint_blocks_plan ______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_client_constraint_blocks_0')

    async def test_client_constraint_blocks_plan(tmp_path: Path) -> None:
        """An out-of-range number is rejected client-side before any plan/preview."""
        view, _ = config_edit_view(tmp_path, {"axe": {"max_hook_runners": 3}})
        field = view.fields_by_path["axe.max_hook_runners"]
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_validation_widget.py:45: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045ce8a00>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________________ test_live_validation_error_appears_and_clears _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_live_validation_error_app0')

    async def test_live_validation_error_appears_and_clears(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"axe": {"max_hook_runners": 3}})
        field = view.fields_by_path["axe.max_hook_runners"]
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_validation_widget.py:61: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045c89180>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________________ test_schema_validation_blocks_write ______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_schema_validation_blocks_0')

    async def test_schema_validation_blocks_write(tmp_path: Path) -> None:
        """A candidate that fails schema validation cannot be written."""
        view, user_file = config_edit_view(tmp_path, {"linked_repos": [{"name": "core"}]})
        field = view.fields_by_path["linked_repos"]
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_validation_widget.py:76: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045c89180>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________________ test_two_stage_escape_backs_out_of_modal ___________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_two_stage_escape_backs_ou0')

    async def test_two_stage_escape_backs_out_of_modal(tmp_path: Path) -> None:
        """Esc enters NORMAL mode; a second Esc (nothing pending) backs out."""
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_vim_widget.py:23: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045cc8aa0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________________ test_enter_submits_from_normal_mode ______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_enter_submits_from_normal0')

    async def test_enter_submits_from_normal_mode(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_vim_widget.py:39: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045cb9540>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_normal_mode_edit_fires_live_validation __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_normal_mode_edit_fires_li0')

    async def test_normal_mode_edit_fires_live_validation(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"axe": {"max_hook_runners": 3}})
        field = view.fields_by_path["axe.max_hook_runners"]
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_vim_widget.py:57: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045c9c280>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________________ test_normal_mode_dd_edits_yaml_editor _____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_normal_mode_dd_edits_yaml0')

    async def test_normal_mode_dd_edits_yaml_editor(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"linked_repos": [{"name": "core"}]})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_vim_widget.py:75: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045ccb020>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________________ test_ctrl_s_confirms_from_yaml_editor _____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_ctrl_s_confirms_from_yaml0')

    async def test_ctrl_s_confirms_from_yaml_editor(tmp_path: Path) -> None:
        view, _ = config_edit_view(tmp_path, {"linked_repos": [{"name": "core"}]})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_vim_widget.py:92: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045cba300>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________________ test_ctrl_r_toggles_reset_from_insert_mode __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_ctrl_r_toggles_reset_from0')

    async def test_ctrl_r_toggles_reset_from_insert_mode(tmp_path: Path) -> None:
        """NORMAL-mode ``ctrl+r`` is vim redo, but INSERT-mode reaches the modal."""
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_edit_modal_vim_widget.py:105: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045bb32f0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_ test_embedded_memory_glossary_bare_digit_selects_admin_tab_prefixed_follows __
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044e2b620>

    async def test_embedded_memory_glossary_bare_digit_selects_admin_tab_prefixed_follows(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        ref = scope_ref("sase", "sase")
        web = memory_web_with_mentioning_strands()
        descriptor = memory_note(
            "glossary", note_type="core", description="Glossary.", body="Glossary body."
        )
        snapshot = scope_snapshot(ref, (descriptor,), webs=(web,))
        install_memory_load(monkeypatch, (ref,), {"sase": snapshot})
        install_fake_strand_read(monkeypatch)
        _keep_real_config_stub_other_tabs(monkeypatch)
    
        async with _HostApp().run_test(size=(120, 40)) as pilot:
            modal = ConfigCenterModal(
                initial_tab="config",
                config_entry=ConfigHubEntry(subtab="memory", note="glossary:alpha"),
            )
            pilot.app.push_screen(modal)
            await wait_for(pilot, lambda: modal._active_tab == "config")
            hub = modal.query_one("#config", ConfigHubPane)
            await wait_for(pilot, lambda: "memory" in hub._panes)
            pane = hub.query_one("#memory", MemoryPane)
            await wait_for(
                pilot,
                lambda: not pane._loading and pane._current_note == "glossary:alpha",
            )
    
            await pilot.press("2")
>           await wait_for(pilot, lambda: modal._active_tab == "logs")

tests/ace/tui/test_config_hub_numbered_links.py:88: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/wait.py:98: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function test_embedded_memory_glossary_bare_digit_selects_admin_tab_prefixed_follows.<locals>.<lambda> at 0x7ff02eeb16f0>
is_success = <class 'bool'>
settle = <function wait_for.<locals>.<lambda> at 0x7ff02eeb1f30>, timeout = 60.0
timeout_message = <function wait_for.<locals>.timeout_message at 0x7ff02eeb2090>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7ff0837701a0>, backoff_after_misses = 3
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
E               AssertionError: wait_for(test_embedded_memory_glossary_bare_digit_selects_admin_tab_prefixed_follows.<locals>.<lambda>) timed out after 60.0s waiting for it to return True

src/sase/ace/testing/wait.py:64: AssertionError

During handling of the above exception, another exception occurred:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff044e2b620>

    async def test_embedded_memory_glossary_bare_digit_selects_admin_tab_prefixed_follows(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        ref = scope_ref("sase", "sase")
        web = memory_web_with_mentioning_strands()
        descriptor = memory_note(
            "glossary", note_type="core", description="Glossary.", body="Glossary body."
        )
        snapshot = scope_snapshot(ref, (descriptor,), webs=(web,))
        install_memory_load(monkeypatch, (ref,), {"sase": snapshot})
        install_fake_strand_read(monkeypatch)
        _keep_real_config_stub_other_tabs(monkeypatch)
    
>       async with _HostApp().run_test(size=(120, 40)) as pilot:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_hub_numbered_links.py:72: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:235: in __aexit__
    await self.gen.athrow(value)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:654: in _process_messages_loop
    await self._dispatch_message(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
.venv/lib/python3.14/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/modals/memory_pane.py:305: in on_key
    from .config_hub_keys import handle_config_hub_subtab_select_key
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02ed023a0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.modals.config_hub_keys

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/ │
│ tui/modals/memory_pane.py:305 in on_key                                      │
│                                                                              │
│   302 │   │   self._instruction_body_worker: Worker[Any] | None = None       │
│   303 │                                                                      │
│   304 │   def on_key(self, event: events.Key) -> None:                       │
│ ❱ 305 │   │   from .config_hub_keys import handle_config_hub_subtab_select_k │
│   306 │   │                                                                  │
│   307 │   │   if handle_config_hub_subtab_select_key(self, event):           │
│   308 │   │   │   return                                                     │
│                                                                              │
│ ╭───────────────────────────── locals ─────────────────────────────╮         │
│ │ event = Key(key='2', character='2', name='2', is_printable=True) │         │
│ │  self = MemoryPane(id='memory', classes='-embedded')             │         │
│ ╰──────────────────────────────────────────────────────────────────╯         │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tools/_check_ │
│ rebase_imports.py:235 in exec_module                                         │
│                                                                              │
│   232 │                                                                      │
│   233 │   def exec_module(self, module: Any) -> None:                        │
│   234 │   │   del module                                                     │
│ ❱ 235 │   │   raise ModuleNotFoundError(f"no committed first-party module na │
│   236                                                                        │
│   237                                                                        │
│   238 class _CommittedSourceFinder(importlib.abc.MetaPathFinder):            │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │ self = <_check_rebase_imports._MissingFirstPartyLoader object at         │ │
│ │        0x7ff02ed023a0>                                                   │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
╰──────────────────────────────────────────────────────────────────────────────╯
ModuleNotFoundError: no committed first-party module named 
sase.ace.tui.modals.config_hub_keys
______ test_embedded_memory_bare_digit_selects_admin_tab_prefixed_follows ______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff046808c90>

    async def test_embedded_memory_bare_digit_selects_admin_tab_prefixed_follows(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        ref = scope_ref("sase", "sase")
        install_memory_load(
            monkeypatch, (ref,), {"sase": scope_snapshot(ref, _linked_notes())}
        )
        _keep_real_config_stub_other_tabs(monkeypatch)
    
        async with _HostApp().run_test(size=(120, 40)) as pilot:
            modal = ConfigCenterModal(
                initial_tab="config",
                config_entry=ConfigHubEntry(subtab="memory", note="sase/memory/hub.md"),
            )
            pilot.app.push_screen(modal)
            await wait_for(pilot, lambda: modal._active_tab == "config")
            hub = modal.query_one("#config", ConfigHubPane)
            await wait_for(pilot, lambda: "memory" in hub._panes)
            pane = hub.query_one("#memory", MemoryPane)
            await wait_for(
                pilot,
                lambda: not pane._loading and pane._current_note == "sase/memory/hub.md",
            )
    
            await pilot.press("2")
>           await wait_for(pilot, lambda: modal._active_tab == "logs")

tests/ace/tui/test_config_hub_numbered_links.py:137: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/wait.py:98: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function test_embedded_memory_bare_digit_selects_admin_tab_prefixed_follows.<locals>.<lambda> at 0x7ff0758a1220>
is_success = <class 'bool'>
settle = <function wait_for.<locals>.<lambda> at 0x7ff045686ae0>, timeout = 60.0
timeout_message = <function wait_for.<locals>.timeout_message at 0x7ff045684a90>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7ff0837701a0>, backoff_after_misses = 3
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
E               AssertionError: wait_for(test_embedded_memory_bare_digit_selects_admin_tab_prefixed_follows.<locals>.<lambda>) timed out after 60.0s waiting for it to return True

src/sase/ace/testing/wait.py:64: AssertionError

During handling of the above exception, another exception occurred:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff046808c90>

    async def test_embedded_memory_bare_digit_selects_admin_tab_prefixed_follows(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        ref = scope_ref("sase", "sase")
        install_memory_load(
            monkeypatch, (ref,), {"sase": scope_snapshot(ref, _linked_notes())}
        )
        _keep_real_config_stub_other_tabs(monkeypatch)
    
>       async with _HostApp().run_test(size=(120, 40)) as pilot:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_hub_numbered_links.py:121: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:235: in __aexit__
    await self.gen.athrow(value)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:654: in _process_messages_loop
    await self._dispatch_message(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
.venv/lib/python3.14/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/modals/memory_pane.py:305: in on_key
    from .config_hub_keys import handle_config_hub_subtab_select_key
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044962990>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.modals.config_hub_keys

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/ │
│ tui/modals/memory_pane.py:305 in on_key                                      │
│                                                                              │
│   302 │   │   self._instruction_body_worker: Worker[Any] | None = None       │
│   303 │                                                                      │
│   304 │   def on_key(self, event: events.Key) -> None:                       │
│ ❱ 305 │   │   from .config_hub_keys import handle_config_hub_subtab_select_k │
│   306 │   │                                                                  │
│   307 │   │   if handle_config_hub_subtab_select_key(self, event):           │
│   308 │   │   │   return                                                     │
│                                                                              │
│ ╭───────────────────────────── locals ─────────────────────────────╮         │
│ │ event = Key(key='2', character='2', name='2', is_printable=True) │         │
│ │  self = MemoryPane(id='memory', classes='-embedded')             │         │
│ ╰──────────────────────────────────────────────────────────────────╯         │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tools/_check_ │
│ rebase_imports.py:235 in exec_module                                         │
│                                                                              │
│   232 │                                                                      │
│   233 │   def exec_module(self, module: Any) -> None:                        │
│   234 │   │   del module                                                     │
│ ❱ 235 │   │   raise ModuleNotFoundError(f"no committed first-party module na │
│   236                                                                        │
│   237                                                                        │
│   238 class _CommittedSourceFinder(importlib.abc.MetaPathFinder):            │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │ self = <_check_rebase_imports._MissingFirstPartyLoader object at         │ │
│ │        0x7ff044962990>                                                   │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
╰──────────────────────────────────────────────────────────────────────────────╯
ModuleNotFoundError: no committed first-party module named 
sase.ace.tui.modals.config_hub_keys
___________ test_embedded_snippets_bare_digit_still_follows_locally ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff04a93a270>

    async def test_embedded_snippets_bare_digit_still_follows_locally(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        ref = snippets_project_ref("sase", "sase")
        entries = (
            snippet_entry("alpha", outbound=("beta", "gamma"), inbound=("delta",)),
            snippet_entry("beta"),
            snippet_entry("gamma"),
            snippet_entry("delta"),
        )
        install_snippets_load(
            monkeypatch, (ref,), {"sase": snippets_project_snapshot(ref, entries)}
        )
        _keep_real_config_stub_other_tabs(monkeypatch)
    
        async with _HostApp().run_test(size=(120, 40)) as pilot:
            modal = ConfigCenterModal(
                initial_tab="config",
                config_entry=ConfigHubEntry(subtab="snippets", trigger="alpha"),
            )
            pilot.app.push_screen(modal)
            await wait_for(pilot, lambda: modal._active_tab == "config")
            hub = modal.query_one("#config", ConfigHubPane)
            await wait_for(pilot, lambda: "snippets" in hub._panes)
            pane = hub.query_one("#snippets", SnippetsPane)
            await wait_for(
                pilot, lambda: not pane._loading and pane._current_trigger == "alpha"
            )
    
            await pilot.press("2")
>           await wait_for(pilot, lambda: pane._current_trigger == "gamma")

tests/ace/tui/test_config_hub_numbered_links.py:191: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/wait.py:98: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function test_embedded_snippets_bare_digit_still_follows_locally.<locals>.<lambda> at 0x7ff045686140>
is_success = <class 'bool'>
settle = <function wait_for.<locals>.<lambda> at 0x7ff0456d4ca0>, timeout = 60.0
timeout_message = <function wait_for.<locals>.timeout_message at 0x7ff0456d49e0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7ff0837701a0>, backoff_after_misses = 3
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
E               AssertionError: wait_for(test_embedded_snippets_bare_digit_still_follows_locally.<locals>.<lambda>) timed out after 60.0s waiting for it to return True

src/sase/ace/testing/wait.py:64: AssertionError

During handling of the above exception, another exception occurred:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff04a93a270>

    async def test_embedded_snippets_bare_digit_still_follows_locally(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        ref = snippets_project_ref("sase", "sase")
        entries = (
            snippet_entry("alpha", outbound=("beta", "gamma"), inbound=("delta",)),
            snippet_entry("beta"),
            snippet_entry("gamma"),
            snippet_entry("delta"),
        )
        install_snippets_load(
            monkeypatch, (ref,), {"sase": snippets_project_snapshot(ref, entries)}
        )
        _keep_real_config_stub_other_tabs(monkeypatch)
    
>       async with _HostApp().run_test(size=(120, 40)) as pilot:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_hub_numbered_links.py:176: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:235: in __aexit__
    await self.gen.athrow(value)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:654: in _process_messages_loop
    await self._dispatch_message(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
.venv/lib/python3.14/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/modals/snippets_panel.py:197: in on_key
    from .config_hub_keys import handle_config_hub_subtab_select_key
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0462efb60>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.modals.config_hub_keys

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/ │
│ tui/modals/snippets_panel.py:197 in on_key                                   │
│                                                                              │
│   194 │   │   self._pending_draft: SnippetFormDraft | None = None            │
│   195 │                                                                      │
│   196 │   def on_key(self, event: events.Key) -> None:                       │
│ ❱ 197 │   │   from .config_hub_keys import handle_config_hub_subtab_select_k │
│   198 │   │                                                                  │
│   199 │   │   if handle_config_hub_subtab_select_key(self, event):           │
│   200 │   │   │   return                                                     │
│                                                                              │
│ ╭───────────────────────────── locals ─────────────────────────────╮         │
│ │ event = Key(key='2', character='2', name='2', is_printable=True) │         │
│ │  self = SnippetsPane(id='snippets', classes='-embedded')         │         │
│ ╰──────────────────────────────────────────────────────────────────╯         │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tools/_check_ │
│ rebase_imports.py:235 in exec_module                                         │
│                                                                              │
│   232 │                                                                      │
│   233 │   def exec_module(self, module: Any) -> None:                        │
│   234 │   │   del module                                                     │
│ ❱ 235 │   │   raise ModuleNotFoundError(f"no committed first-party module na │
│   236                                                                        │
│   237                                                                        │
│   238 class _CommittedSourceFinder(importlib.abc.MetaPathFinder):            │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │ self = <_check_rebase_imports._MissingFirstPartyLoader object at         │ │
│ │        0x7ff0462efb60>                                                   │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
╰──────────────────────────────────────────────────────────────────────────────╯
ModuleNotFoundError: no committed first-party module named 
sase.ace.tui.modals.config_hub_keys
_____________ test_opening_config_constructs_only_the_active_child _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff04525e660>

    async def test_opening_config_constructs_only_the_active_child(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        created, calls = _patch_hub_children(monkeypatch)
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_hub_pane.py:62: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff044c4b890>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______ test_resize_switches_caption_variant_without_reloading_children ________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff046033310>

    async def test_resize_switches_caption_variant_without_reloading_children(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _created, calls = _patch_hub_children(monkeypatch)
>       async with AcePage(initial_tab="agents", size=(120, 40)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_hub_pane.py:207: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047f84640>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________________ test_filter_brackets_cycle_config_subtabs ___________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff06db17690>

    async def test_filter_brackets_cycle_config_subtabs(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        calls: list[str] = []
    
        def create(_self: ConfigHubPane, subtab: str) -> _FilterChild:
            calls.append(subtab)
            return _FilterChild(subtab)
    
        monkeypatch.setattr(ConfigHubPane, "_create_pane", create)
        async with _HostApp().run_test() as pilot:
            modal = ConfigCenterModal(
                initial_tab="config",
                config_entry=ConfigHubEntry(subtab="macros"),
            )
            pilot.app.push_screen(modal)
            await wait_for(pilot, lambda: modal._active_tab == "config")
            hub = modal.query_one("#config", ConfigHubPane)
            await wait_for(pilot, lambda: "macros" in hub._panes)
            await wait_for(pilot, lambda: isinstance(pilot.app.focused, Input))
    
            await pilot.press("right_square_bracket")
>           await wait_for(pilot, lambda: hub._active_subtab == "misc")

tests/ace/tui/test_config_hub_pane_navigation.py:73: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/wait.py:98: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function test_filter_brackets_cycle_config_subtabs.<locals>.<lambda> at 0x7ff0442109e0>
is_success = <class 'bool'>
settle = <function wait_for.<locals>.<lambda> at 0x7ff02fd97b60>, timeout = 60.0
timeout_message = <function wait_for.<locals>.timeout_message at 0x7ff02fd97c10>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7ff0837701a0>, backoff_after_misses = 3
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
E               AssertionError: wait_for(test_filter_brackets_cycle_config_subtabs.<locals>.<lambda>) timed out after 60.0s waiting for it to return True

src/sase/ace/testing/wait.py:64: AssertionError

During handling of the above exception, another exception occurred:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff06db17690>

    async def test_filter_brackets_cycle_config_subtabs(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        calls: list[str] = []
    
        def create(_self: ConfigHubPane, subtab: str) -> _FilterChild:
            calls.append(subtab)
            return _FilterChild(subtab)
    
        monkeypatch.setattr(ConfigHubPane, "_create_pane", create)
>       async with _HostApp().run_test() as pilot:
                   ^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_hub_pane_navigation.py:61: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:235: in __aexit__
    await self.gen.athrow(value)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:654: in _process_messages_loop
    await self._dispatch_message(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
.venv/lib/python3.14/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
tests/ace/tui/_config_hub_pane_helpers.py:61: in on_key
    from sase.ace.tui.modals.config_hub_keys import handle_config_hub_bracket_key
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046306620>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.modals.config_hub_keys

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui │
│ /_config_hub_pane_helpers.py:61 in on_key                                    │
│                                                                              │
│    58                                                                        │
│    59 class _ForwardingFilter(Input):                                        │
│    60 │   def on_key(self, event: object) -> None:                           │
│ ❱  61 │   │   from sase.ace.tui.modals.config_hub_keys import handle_config_ │
│    62 │   │                                                                  │
│    63 │   │   handle_config_hub_bracket_key(self, event)  # type: ignore[arg │
│    64                                                                        │
│                                                                              │
│ ╭────────────────── locals ──────────────────╮                               │
│ │ event = Key(                               │                               │
│ │         │   key='right_square_bracket',    │                               │
│ │         │   character=']',                 │                               │
│ │         │   name='right_square_bracket',   │                               │
│ │         │   is_printable=True              │                               │
│ │         )                                  │                               │
│ │  self = _ForwardingFilter(id='hub-filter') │                               │
│ ╰────────────────────────────────────────────╯                               │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tools/_check_ │
│ rebase_imports.py:235 in exec_module                                         │
│                                                                              │
│   232 │                                                                      │
│   233 │   def exec_module(self, module: Any) -> None:                        │
│   234 │   │   del module                                                     │
│ ❱ 235 │   │   raise ModuleNotFoundError(f"no committed first-party module na │
│   236                                                                        │
│   237                                                                        │
│   238 class _CommittedSourceFinder(importlib.abc.MetaPathFinder):            │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │ self = <_check_rebase_imports._MissingFirstPartyLoader object at         │ │
│ │        0x7ff046306620>                                                   │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
╰──────────────────────────────────────────────────────────────────────────────╯
ModuleNotFoundError: no committed first-party module named 
sase.ace.tui.modals.config_hub_keys
________________ test_config_filter_keeps_prefix_digits_as_text ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0744aae40>

    async def test_config_filter_keeps_prefix_digits_as_text(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        def create(_self: ConfigHubPane, subtab: str) -> _FilterChild:
            return _FilterChild(subtab)
    
        monkeypatch.setattr(ConfigHubPane, "_create_pane", create)
        async with _HostApp().run_test() as pilot:
            modal = ConfigCenterModal(
                initial_tab="config",
                config_entry=ConfigHubEntry(subtab="macros"),
            )
            pilot.app.push_screen(modal)
            await wait_for(pilot, lambda: modal._active_tab == "config")
            hub = modal.query_one("#config", ConfigHubPane)
            await wait_for(pilot, lambda: "macros" in hub._panes)
            await wait_for(pilot, lambda: isinstance(pilot.app.focused, Input))
    
            input_widget = hub.query_one("#hub-filter", Input)
            await pilot.press("0", "1")
    
>           assert input_widget.value == "01"
E           AssertionError: assert '' == '01'
E             
E             - 01

tests/ace/tui/test_config_hub_pane_navigation.py:214: AssertionError

During handling of the above exception, another exception occurred:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0744aae40>

    async def test_config_filter_keeps_prefix_digits_as_text(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        def create(_self: ConfigHubPane, subtab: str) -> _FilterChild:
            return _FilterChild(subtab)
    
        monkeypatch.setattr(ConfigHubPane, "_create_pane", create)
>       async with _HostApp().run_test() as pilot:
                   ^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_hub_pane_navigation.py:200: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:235: in __aexit__
    await self.gen.athrow(value)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:654: in _process_messages_loop
    await self._dispatch_message(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
.venv/lib/python3.14/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
tests/ace/tui/_config_hub_pane_helpers.py:61: in on_key
    from sase.ace.tui.modals.config_hub_keys import handle_config_hub_bracket_key
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff04605d4f0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.modals.config_hub_keys

tools/_check_rebase_imports.py:235: ModuleNotFoundError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui │
│ /_config_hub_pane_helpers.py:61 in on_key                                    │
│                                                                              │
│    58                                                                        │
│    59 class _ForwardingFilter(Input):                                        │
│    60 │   def on_key(self, event: object) -> None:                           │
│ ❱  61 │   │   from sase.ace.tui.modals.config_hub_keys import handle_config_ │
│    62 │   │                                                                  │
│    63 │   │   handle_config_hub_bracket_key(self, event)  # type: ignore[arg │
│    64                                                                        │
│                                                                              │
│ ╭───────────────────────────── locals ─────────────────────────────╮         │
│ │ event = Key(key='0', character='0', name='0', is_printable=True) │         │
│ │  self = _ForwardingFilter(id='hub-filter')                       │         │
│ ╰──────────────────────────────────────────────────────────────────╯         │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tools/_check_ │
│ rebase_imports.py:235 in exec_module                                         │
│                                                                              │
│   232 │                                                                      │
│   233 │   def exec_module(self, module: Any) -> None:                        │
│   234 │   │   del module                                                     │
│ ❱ 235 │   │   raise ModuleNotFoundError(f"no committed first-party module na │
│   236                                                                        │
│   237                                                                        │
│   238 class _CommittedSourceFinder(importlib.abc.MetaPathFinder):            │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │ self = <_check_rebase_imports._MissingFirstPartyLoader object at         │ │
│ │        0x7ff04605d4f0>                                                   │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
╰──────────────────────────────────────────────────────────────────────────────╯
ModuleNotFoundError: no committed first-party module named 
sase.ace.tui.modals.config_hub_keys
__________________ test_config_pane_loads_and_populates_tree ___________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff046d0c600>

    async def test_config_pane_loads_and_populates_tree(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget.py:23: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff045acbd40>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_config_pane_restores_session_bookmark_by_path ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff045fdf620>

    async def test_config_pane_restores_session_bookmark_by_path(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
        state = AdminCenterSessionState()
        state.config.record("timezone", 2)
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget.py:44: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02f85eb20>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________________ test_config_pane_filter_narrows_tree _____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0751957f0>

    async def test_config_pane_filter_narrows_tree(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget.py:66: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046dfb2f0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_config_pane_filter_updates_title_match_count _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0464c46e0>

    async def test_config_pane_filter_updates_title_match_count(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget.py:82: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046dfb200>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____ test_config_filter_brackets_cycle_subtabs_and_tab_switches_main_tab ______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff046d14750>

    async def test_config_filter_brackets_cycle_subtabs_and_tab_switches_main_tab(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget.py:95: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046d8d630>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________________ test_config_pane_modified_only_toggle _____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0464b3e00>

    async def test_config_pane_modified_only_toggle(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        view = _patch_loaders(monkeypatch)
        modified = view.modified_paths()
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget.py:120: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff04605d400>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________ test_config_pane_j_k_wrap_visible_tree_and_arrows_clamp ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff02fc0c670>

    async def test_config_pane_j_k_wrap_visible_tree_and_arrows_clamp(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_navigation.py:132: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046d9ba20>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________________ test_config_pane_j_k_cycle_single_visible_row _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff046d16c10>

    async def test_config_pane_j_k_cycle_single_visible_row(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_navigation.py:170: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046d97e80>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________________ test_config_pane_g_and_G_jump_tree_cursor ___________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0464c4590>

    async def test_config_pane_g_and_G_jump_tree_cursor(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_navigation.py:193: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046d975c0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________ test_config_pane_h_l_collapse_expand_and_descend _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff045b43e70>

    async def test_config_pane_h_l_collapse_expand_and_descend(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_navigation.py:205: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470f5130>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_config_pane_ctrl_d_and_ctrl_u_scroll_detail_only _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff045b40210>

    async def test_config_pane_ctrl_d_and_ctrl_u_scroll_detail_only(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage(size=(120, 30)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_config_pane_widget_navigation.py:230: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470f48c0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________________ test_config_center_cycles_all_tabs ______________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff045e45390>

    async def test_config_center_cycles_all_tabs(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(monkeypatch, catalog=_catalog())
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_loading.py:490: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff046d95d10>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______ test_plugin_mark_survives_filter_hide_and_is_consumed_by_install _______
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff045e477e0>

    async def test_plugin_mark_survives_filter_hide_and_is_consumed_by_install(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(monkeypatch, catalog=_catalog(), uv_tool=_uv_tool())
        batch_plans: list[tuple[str, ...]] = []
        monkeypatch.setattr(
            pbp,
            "_plan_install_many_preview",
            lambda names, *, offline: (
                batch_plans.append(names)
                or pbp._InstallManyPreview(plan=_ready_many_plan(names))
            ),
        )
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:53: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047090fa0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_cli_mark_consumed_by_update_when_cli_rows_hidden _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470f10f0>

    async def test_cli_mark_consumed_by_update_when_cli_rows_hidden(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            agent_cli_statuses=_agent_cli_statuses(),
            uv_tool=_uv_tool(),
        )
        recorded: list[tuple[tuple[str, ...] | None, bool]] = []
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:81: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470dc280>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_plugin_marks_do_not_constrain_unmarked_cli_update ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470a5630>

    async def test_plugin_marks_do_not_constrain_unmarked_cli_update(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            agent_cli_statuses=_agent_cli_statuses(),
            uv_tool=_uv_tool(),
        )
        recorded: list[tuple[tuple[str, ...] | None, bool]] = []
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:115: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470dc1e0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_escape_clears_plugin_and_cli_marks_in_one_press _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff02ed2a820>

    async def test_escape_clears_plugin_and_cli_marks_in_one_press(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            agent_cli_statuses=_agent_cli_statuses(),
            uv_tool=_uv_tool(),
        )
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:144: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047059ea0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_mark_all_respects_filter_and_section_capabilities ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff045e45e10>

    async def test_mark_all_respects_filter_and_section_capabilities(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            agent_cli_statuses=_agent_cli_statuses(),
            uv_tool=_uv_tool(),
        )
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:346: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470df890>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________ test_mark_all_keeps_builtin_and_community_plugins_apart ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470f38c0>

    async def test_mark_all_keeps_builtin_and_community_plugins_apart(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            agent_cli_statuses=_agent_cli_statuses(),
            uv_tool=_uv_tool(),
        )
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:370: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047011450>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________________ test_mark_all_unmarkable_row_warns_like_space _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470f0e50>

    async def test_mark_all_unmarkable_row_warns_like_space(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            agent_cli_statuses=_agent_cli_statuses(),
            uv_tool=_uv_tool(),
        )
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:397: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047012b20>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________________ test_pane_bindings_have_no_duplicate_keys ___________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470f0bb0>

    async def test_pane_bindings_have_no_duplicate_keys(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(monkeypatch, catalog=_catalog(), uv_tool=_uv_tool())
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:414: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470d8280>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________ test_asterisk_press_marks_all_without_saved_query_picker ___________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470f1710>

    async def test_asterisk_press_marks_all_without_saved_query_picker(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            agent_cli_statuses=_agent_cli_statuses(),
            uv_tool=_uv_tool(),
        )
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:431: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470d84b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_overview_revalidation_tick_never_paints_loading _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470d1470>

    async def test_overview_revalidation_tick_never_paints_loading(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        calls: list[tuple[StatisticsView, StatsRange, str | None, str | None]] = []
        _patch_center(monkeypatch, calls)
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_statistics_pane_loading.py:384: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047012da0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_retry_after_failed_discovery_retains_generation _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_retry_after_failed_discovery_retains_generation() -> None:
        """A failed pass keeps the bootstrap generation; an explicit retry heals."""
    
        from sase.ace.tui.actions._artifacts_publication import (
            ArtifactsPublicationMixin,
        )
    
        first_entered = threading.Event()
        first_release = threading.Event()
        second_entered = threading.Event()
        second_release = threading.Event()
        calls = {"count": 0}
    
        def _flaky() -> tuple[Any, int, tuple[Any, ...], str]:
            from sase.ace.tui._artifact_tab_descriptors import (
                build_artifacts_strip,
                provider_descriptors,
            )
    
            from sase.ace.tui.artifact_tabs import artifacts_tab_cache_epoch
    
            calls["count"] += 1
            if calls["count"] == 1:
                first_entered.set()
                assert first_release.wait(timeout=LOAD_TOLERANT_TIMEOUT)
                return (
                    None,
                    int(artifacts_tab_cache_epoch()),
                    build_artifacts_strip(()),
                    "failed",
                )
            second_entered.set()
            assert second_release.wait(timeout=LOAD_TOLERANT_TIMEOUT)
            providers = provider_descriptors(plan_records(), ())
            return (
                ("test-token",),
                int(artifacts_tab_cache_epoch()),
                build_artifacts_strip(providers),
                "completed",
            )
    
        with patch(publication_path(), _flaky):
>           async with AcePage(initial_tab="artifacts", startup_policy="real") as page:
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/_artifacts_post_paint_publication_recovery.py:74: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047040d70>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_shutdown_before_completion_discards_late_result _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_shutdown_before_completion_discards_late_result() -> None:
        """Results landing after teardown must not mutate the app."""
    
        from sase.ace.tui.actions._artifacts_publication import (
            ArtifactsPublicationMixin,
        )
    
        entered = threading.Event()
        release = threading.Event()
        with patch(
            publication_path(),
            gated_blocking_factory(entered, release, records=plan_records()),
        ):
>           async with AcePage(initial_tab="artifacts", startup_policy="real") as page:
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/_artifacts_post_paint_publication_recovery.py:160: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff04703f430>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_healthy_provider_is_replaced_when_it_degrades ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_healthy_provider_is_replaced_when_it_degrades() -> None:
        entered = threading.Event()
        release = threading.Event()
        with patch(
            publication_path(),
            gated_blocking_factory(entered, release, records=plan_records()),
        ):
>           async with AcePage(initial_tab="artifacts", startup_policy="real") as page:
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/_artifacts_post_paint_publication_replacement.py:47: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff047040780>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
______________ test_open_palette_selects_newly_published_command _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_open_palette_selects_newly_published_command() -> None:
        from sase.ace.tui.commands.types import CommandPaletteResult
        from sase.ace.tui.modals.command_palette_modal import CommandPaletteModal
    
        entered = threading.Event()
        release = threading.Event()
        with patch(
            publication_path(),
            gated_blocking_factory(entered, release, records=plan_records()),
        ):
>           async with AcePage(initial_tab="artifacts", startup_policy="real") as page:
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/_artifacts_post_paint_publication_staging.py:139: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470e96d0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________ test_scope_change_during_staging_is_applied_before_commit ___________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_scope_change_during_staging_is_applied_before_commit() -> None:
        entered = threading.Event()
        release = threading.Event()
        with patch(
            publication_path(),
            gated_blocking_factory(entered, release, records=plan_records()),
        ):
>           async with AcePage(initial_tab="artifacts", startup_policy="real") as page:
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/_artifacts_post_paint_publication_staging.py:241: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470a0910>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_stale_epoch_is_rejected_then_coalesced __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

    async def test_stale_epoch_is_rejected_then_coalesced() -> None:
        from sase.ace.tui.actions._artifacts_publication import ArtifactsPublicationMixin
        from sase.ace.tui.artifact_tabs import reset_artifacts_subtabs_cache
    
        first_entered = threading.Event()
        first_release = threading.Event()
        second_entered = threading.Event()
        second_release = threading.Event()
        calls = {"count": 0}
        committed_epochs: list[int] = []
        original_commit = ArtifactsPublicationMixin._commit_artifacts_snapshot
    
        def _commit(
            self: Any,
            new_snapshot: Any,
            *args: Any,
            **kwargs: Any,
        ) -> None:
            committed_epochs.append(int(new_snapshot.source_epoch))
            return original_commit(self, new_snapshot, *args, **kwargs)
    
        def _stale_then_fresh() -> tuple[Any, int, tuple[Any, ...], str]:
            from sase.ace.tui._artifact_tab_descriptors import (
                build_artifacts_strip,
                provider_descriptors,
            )
            from sase.ace.tui.artifact_tabs import artifacts_tab_cache_epoch
    
            calls["count"] += 1
            providers = provider_descriptors(plan_records(), ())
            descriptors = build_artifacts_strip(providers)
            if calls["count"] == 1:
                first_entered.set()
                assert first_release.wait(timeout=LOAD_TOLERANT_TIMEOUT)
                epoch = int(artifacts_tab_cache_epoch())
                reset_artifacts_subtabs_cache()
                return ("test-token",), epoch, descriptors, "completed"
            second_entered.set()
            assert second_release.wait(timeout=LOAD_TOLERANT_TIMEOUT)
            return (
                ("test-token",),
                int(artifacts_tab_cache_epoch()),
                descriptors,
                "completed",
            )
    
        with (
            patch.object(ArtifactsPublicationMixin, "_commit_artifacts_snapshot", _commit),
            patch(publication_path(), _stale_then_fresh),
        ):
>           async with AcePage(initial_tab="artifacts", startup_policy="real") as page:
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/_artifacts_post_paint_publication_staging.py:83: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff04709d130>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_____________ test_plugins_pane_uninstall_hint_gated_on_installed ______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470ed630>

    async def test_plugins_pane_uninstall_hint_gated_on_installed(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(monkeypatch, catalog=_catalog())
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_uninstall.py:64: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff04709f7f0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______________ test_plugins_pane_uninstall_not_installed_toasts _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470623c0>

    async def test_plugins_pane_uninstall_not_installed_toasts(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(monkeypatch, catalog=_catalog())
        planned: list[int] = []
        monkeypatch.setattr(
            pbp, "_plan_uninstall_preview", lambda *a, **k: planned.append(1)
        )
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_uninstall.py:88: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470bc280>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_plugins_pane_uninstall_disabled_when_not_uv_tool _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047061e80>

    async def test_plugins_pane_uninstall_disabled_when_not_uv_tool(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(monkeypatch, catalog=_catalog(), uv_tool=_not_uv_tool())
        planned: list[int] = []
        monkeypatch.setattr(
            pbp, "_plan_uninstall_preview", lambda *a, **k: planned.append(1)
        )
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_uninstall.py:108: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff0470bca50>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________ test_updates_pane_reload_clears_freshness_while_in_progress __________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470635b0>

    async def test_updates_pane_reload_clears_freshness_while_in_progress(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        fresh_roots = frozenset({"/repo/sase"})
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            fresh_editable_roots=fresh_roots,
        )
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_loading.py:443: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff04700c5f0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
__________ test_updates_pane_offline_reload_does_not_retain_freshness __________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047015b00>

    async def test_updates_pane_offline_reload_does_not_retain_freshness(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        fresh_roots = frozenset({"/repo/sase"})
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            fresh_editable_roots=fresh_roots,
        )
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_loading.py:475: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02fe89130>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
____________ test_config_pane_confirm_submits_actual_written_source ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470ec1a0>

    async def test_config_pane_confirm_submits_actual_written_source(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
        offer = _config_offer()
        monkeypatch.setattr(cp, "_build_config_commit_offer", lambda *_a, **_kw: offer)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_commit.py:149: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02fe88370>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______ test_config_pane_cancelled_failed_clean_and_non_git_skip_prompt ________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470ee6d0>

    async def test_config_pane_cancelled_failed_clean_and_non_git_skip_prompt(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_commit.py:185: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02fe89f90>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________ test_config_jump_paints_hints_over_visible_rows_in_order ___________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047017620>

    async def test_config_jump_paints_hints_over_visible_rows_in_order(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_jump.py:35: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02fe16ad0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
___________ test_i_on_drifted_project_submits_check_and_sets_status ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470164a0>

    async def test_i_on_drifted_project_submits_check_and_sets_status(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_panes(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_projects_pane_init_flow_single.py:45: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02fee31b0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
________________ test_current_payload_opens_no_modal_and_toasts ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff047015390>

    async def test_current_payload_opens_no_modal_and_toasts(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_panes(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_projects_pane_init_flow_single.py:115: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02fec8230>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_______ test_deep_archive_coverage_label_is_visible_in_idle_status_lane ________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f7d384d3/pytest-of-bryan/pytest-5/popen-gw9/test_deep_archive_coverage_lab0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff0470ee660>

    async def test_deep_archive_coverage_label_is_visible_in_idle_status_lane(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        value = replace(_snapshot(tmp_path), archive_truncated=True)
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            plans_pane,
            "load_plans_snapshot",
            lambda _project, **_kwargs: value,
        )
    
>       async with AcePage(initial_tab="patches") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_artifacts_plans_filtering.py:215: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02fee0aa0>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_config_pane_successful_write_toast_text _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff02fe81ef0>

    async def test_config_pane_successful_write_toast_text(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_commit.py:259: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02fec0d20>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
_________________ test_mark_all_updatable_clis_share_one_verb __________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff02fe803d0>

    async def test_mark_all_updatable_clis_share_one_verb(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_other_panes(monkeypatch)
        _patch_catalog(
            monkeypatch,
            catalog=_catalog(),
            agent_cli_statuses=_agent_cli_statuses(),
            uv_tool=_uv_tool(),
        )
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_plugins_browser_pane_marks.py:322: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:310: in __aenter__
    self._app = AceApp(
src/sase/ace/tui/app.py:354: in __init__
    self._init_app_state(
src/sase/ace/tui/actions/_state_init.py:53: in _init_app_state
    init_agent_state(self)
src/sase/ace/tui/actions/_state_init_agents.py:505: in init_agent_state
    from .agents._types import PlanFeedbackContext
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <_check_rebase_imports._MissingFirstPartyLoader object at 0x7ff02fec3840>

    def exec_module(self, module: Any) -> None:
        del module
>       raise ModuleNotFoundError(f"no committed first-party module named {self.name}")
E       ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types

tools/_check_rebase_imports.py:235: ModuleNotFoundError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/ace/tui/test_agent_archive_controller_lookup.py::test_lookup_miss_clears_pending_and_publishes_missing
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/models/agent_archive_list.py:445: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    applied = frozenset(applied_expanded)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_prewarm.py::test_prewarm_waits_for_idle_ui
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/inspect.py:668: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    def unwrap(func, *, stop=None):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/macro/workflow_runner_execute.py:254: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/macro/workflow_runner_flatten.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/macro/workflow_runner_flatten.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = flatten_anonymous_workflow(workflow)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=3029751) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=3029772) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorHostFinalizer::test_genuine_provider_500_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorHostFinalizer::test_genuine_provider_500_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/config/loading.py:92: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object _record_history_async.<locals>._record at 0x7f5bf85eec30>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=3029745) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object CommandLineScreenSubmissionMixin._submit_worker at 0x7f5c29cdaa70>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  <frozen os>:709: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_bootstrap_errors.py::test_preprocessing_failure_records_failed_done_and_finalizes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_bootstrap_errors.py::test_preprocessing_failure_records_failed_done_and_finalizes changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_bootstrap_errors.py::test_refreshed_bootstrap_preserves_phase_launch_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_bootstrap_errors.py::test_refreshed_bootstrap_preserves_phase_launch_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_bootstrap_errors.py::test_user_kill_during_bootstrap_preserves_exit_and_skips_error_recording
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_bootstrap_errors.py::test_user_kill_during_bootstrap_preserves_exit_and_skips_error_recording changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=3029742) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=3029772) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=3029780) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/_agent_archive_column_helpers.py:49: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    "last_activity_at": f"{day}T{hour:02d}:00:00Z",
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/actions/_launchable_mru.py:308: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_axe_chop_batch_store.py::test_stale_and_live_ownership
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/axe/test_axe_chop_batch_store.py:220: DeprecationWarning: This process (pid=3029742) is multi-threaded, use of fork() may lead to deadlocks in the child.
    pid = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
90.88s call     tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows
63.44s call     tests/test_launch_request_staging.py::test_typed_plan_and_continuation_survive_adoption
60.44s call     tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_memory_glossary_bare_digit_selects_admin_tab_prefixed_follows
60.31s call     tests/ace/tui/test_config_hub_pane_navigation.py::test_filter_brackets_cycle_config_subtabs
60.31s call     tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_memory_bare_digit_selects_admin_tab_prefixed_follows
60.28s call     tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_snippets_bare_digit_still_follows_locally
53.65s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
45.30s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
42.09s call     tests/continuation/test_launch_local_capture_chain.py::test_twenty_launch_agent_monitor_cycles_keep_only_local_authored_text
33.83s call     tests/monitor/test_monitor_start_ack.py::test_startup_sigterm_settles_stopped_without_running_command
32.34s call     tests/monitor/test_monitor_start_stage_adopt.py::test_session_member_staged_join_reserves_env_starter_identity
30.39s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
27.07s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
26.26s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
23.41s call     tests/test_ace_testing.py::test_ace_page_real_startup_update_status_is_hermetic
22.93s call     tests/ace/tui/test_refresh_warmup_gc.py::test_auto_refresh_merge_live_hints_and_warmup_release_obsolete_payloads
21.10s call     tests/test_ace_testing.py::test_ace_page_real_startup_preserves_caller_update_status_fake
20.84s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
20.79s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
20.68s call     tests/test_axe_error_groups.py::test_loud_signature_cannot_evict_rare_ones
=========================== short test summary info ============================
FAILED tests/tool/test_admission_processes.py::test_nested_agent_check_keeps_parent_and_never_queues
FAILED tests/test_chop_sdk.py::test_hook_builtin_uses_shared_runner_and_emits_noop_result
FAILED tests/test_chop_sdk.py::test_all_builtin_chop_modules_use_the_registry
FAILED tests/test_command_palette_e2e.py::test_colon_opens_command_line_from_agents_tab
FAILED tests/test_command_palette_e2e.py::test_colon_opens_command_line_from_axe_tab
FAILED tests/test_command_palette_e2e.py::test_semicolon_opens_command_palette_from_agents_and_axe_tabs
FAILED tests/test_command_palette_e2e.py::test_palette_executes_refresh_from_agents_tab
FAILED tests/test_command_palette_e2e.py::test_palette_executes_refresh_from_axe_tab
FAILED tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
FAILED tests/test_command_palette_wiring.py::test_colon_opens_command_line_modal
FAILED tests/test_command_palette_wiring.py::test_semicolon_opens_command_palette_modal
FAILED tests/test_command_palette_wiring.py::test_palette_colon_hops_to_command_line
FAILED tests/test_command_palette_wiring.py::test_palette_no_match_fallback_prefills_command_line
FAILED tests/test_command_palette_wiring.py::test_palette_escape_dismisses_without_side_effects
FAILED tests/test_command_palette_wiring.py::test_palette_executes_refresh_via_action
FAILED tests/test_command_palette_wiring.py::test_palette_omits_inapplicable_axe_only_command_on_cls_tab
FAILED tests/test_command_palette_wiring.py::test_palette_context_uses_current_tab_badge
FAILED tests/test_command_palette_wiring.py::test_palette_filter_input_swallows_typing_no_action_dispatched
FAILED tests/test_command_palette_wiring.py::test_action_open_command_palette_uses_real_catalog
FAILED tests/test_command_palette_wiring.py::test_action_open_command_palette_dispatches_selection
FAILED tests/test_command_palette_wiring.py::test_action_open_command_palette_noop_on_cancel
FAILED tests/test_command_palette_wiring.py::test_action_open_command_palette_unknown_id_is_silent
FAILED tests/test_command_palette_wiring.py::test_extract_command_context_smoke_against_real_app
FAILED tests/test_commit_publication_inline.py::test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning
FAILED tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_meta_changespec_direct
FAILED tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_meta_changespec_strips_whitespace
FAILED tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_legacy_meta_new_cl
FAILED tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_legacy_meta_new_pr_with_changespec
FAILED tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_returns_none_for_empty_output
FAILED tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_returns_none_for_none_output
FAILED tests/test_commit_workflow_checkpointing.py::test_run_detects_conflict_and_returns_conflict_code
FAILED tests/test_commit_workflow_checkpointing.py::test_no_staged_changes_conflict_checkpoint_marks_no_commit_dispatched
FAILED tests/test_commit_workflow_checkpointing.py::test_run_failure_without_conflict_deletes_checkpoint
FAILED tests/test_commit_workflow_checkpointing.py::test_run_push_failure_after_local_commit_records_unpushed_marker
FAILED tests/test_commit_workflow_checkpointing.py::test_run_push_failure_reports_checkpoint_write_failure_but_keeps_marker
FAILED tests/test_commit_workflow_checkpointing.py::test_run_push_failure_reports_marker_write_failure_but_keeps_checkpoint
FAILED tests/test_commit_workflow_checkpointing.py::test_run_push_failure_reports_when_no_durable_recovery_evidence_written
FAILED tests/test_commit_workflow_checkpointing.py::test_pre_dispatch_checkpoint_has_post_mutation_payload_for_pr
FAILED tests/test_commit_workflow_checkpointing.py::test_pre_dispatch_checkpoint_written_before_dispatch
FAILED tests/test_commit_workflow_dispatch.py::TestCommitWorkflowDispatch::test_provider_failure_returns_false
FAILED tests/test_commit_workflow_hooks.py::test_after_hook_skipped_for_proposals_and_failed_dispatches[create_commit-dispatch_result1]
FAILED tests/test_commit_workflow_resume_recovery.py::test_resume_failed_finalize_returns_failed
FAILED tests/test_commit_workflow_resume_recovery.py::test_resume_push_failure_records_unpushed_marker
FAILED tests/test_config_local_trust_management.py::test_bare_config_trust_prints_help
FAILED tests/test_config_merge.py::test_config_show_projects_public_axe_contract
FAILED tests/test_core_health.py::test_cli_health_human_ok - ModuleNotFoundEr...
FAILED tests/test_core_health.py::test_cli_health_json_ok - ModuleNotFoundErr...
FAILED tests/test_core_health.py::test_cli_health_short_json_flag - ModuleNot...
FAILED tests/test_core_health.py::test_cli_health_rust_missing_exits_nonzero
FAILED tests/test_detach_scope_background_workers.py::test_goal_fast_path_uses_shared_fetch_spawn
FAILED tests/test_detach_scope_bootstrap.py::test_monitor_supervisor_bootstrap_uses_detach_scope
FAILED tests/test_detach_scope_bootstrap.py::test_monitor_supervisor_bootstrap_uses_pid_file_for_systemd_scope
FAILED tests/test_direct_typed_launch.py::test_reported_ace_proc_prompt_uses_typed_admission
FAILED tests/test_direct_typed_launch.py::test_direct_proc_forms_yield_proc_unit[%proc("echo positional")]
FAILED tests/test_direct_typed_launch.py::test_direct_proc_forms_yield_proc_unit[%proc(python="print('ready')", timeout="20m", label="Preflight")]
FAILED tests/test_direct_typed_launch.py::test_direct_proc_forms_yield_proc_unit[%proc(timeout="20m", idle_timeout="5m")::\n\n```bash\necho fenced\n```\n]
FAILED tests/test_direct_typed_launch.py::test_direct_proc_queue_fields_round_trip_from_rust
FAILED tests/test_direct_typed_launch.py::test_direct_if_admits_agent_unit - ...
FAILED tests/test_direct_typed_launch.py::test_mixed_agent_proc_wait_graph - ...
FAILED tests/test_direct_typed_launch.py::test_invalid_typed_syntax_fails_before_agent_launch
FAILED tests/test_direct_typed_launch.py::test_literal_proc_mentions_keep_legacy_path
FAILED tests/test_direct_typed_launch.py::test_plain_prompt_keeps_legacy_and_launch_units
FAILED tests/test_direct_typed_launch.py::test_force_reuse_without_typed_directive
FAILED tests/test_direct_typed_launch.py::test_explicit_vcs_target_wins_over_home_context
FAILED tests/test_direct_typed_launch.py::test_direct_bundle_resumes_after_blocked_wait
FAILED tests/test_direct_typed_launch.py::test_direct_proc_bundle_coordinator_completion_does_not_notify
FAILED tests/test_direct_typed_launch.py::test_isolated_direct_bash_proc_settles_without_agent
FAILED tests/ace/tui/test_commits_pane_grouping.py::test_hydrate_ref_resolves_exact_commit_bypassing_collection_window
FAILED tests/ace/tui/test_commits_pane_grouping.py::test_hydrate_ref_reports_absent_for_unresolvable_sha
FAILED tests/ace/tui/test_commits_pane_interactions.py::test_commits_pilot_drives_live_filter_bar_detail_copy_and_toggles
FAILED tests/ace/tui/test_commits_pane_interactions.py::test_commits_refresh_override_drives_action_footer_and_help
FAILED tests/ace/tui/test_commits_pane_interactions.py::test_commit_fetch_task_uses_visible_project_name_and_matching_file
FAILED tests/ace/tui/test_commits_pane_interactions.py::test_commits_cycle_merges_updates_query_and_recollects
FAILED tests/ace/tui/test_commits_pane_rendering.py::test_commits_timeline_mounted_rows_stay_one_line_with_jump_hints
FAILED tests/ace/tui/test_config_center_alternate_tab.py::test_alternate_opener_ping_pongs_between_exactly_two_sections
FAILED tests/ace/tui/test_config_center_alternate_tab.py::test_single_section_visited_leaves_opener_inert
FAILED tests/ace/tui/test_config_center_alternate_tab.py::test_seeded_alternate_survives_close_and_reopen
FAILED tests/ace/tui/test_config_center_alternate_tab.py::test_custom_opener_drives_alternate_jump_and_is_shown_in_footer
FAILED tests/ace/tui/test_config_center_alternate_tab.py::test_literal_opener_with_alternate_available_still_types_and_stays_put
FAILED tests/ace/tui/test_config_center_alternate_tab.py::test_failed_alternate_jump_leaves_history_unchanged_and_is_retryable
FAILED tests/ace/tui/test_config_center_alternate_tab.py::test_footer_hidden_on_home_and_reflects_alternate_once_a_tab_is_active
FAILED tests/ace/tui/test_config_center_alternate_tab.py::test_footer_click_navigates_to_the_alternate_section
FAILED tests/ace/tui/test_config_center_alternate_tab.py::test_persisted_file_contains_both_lines_in_order
FAILED tests/ace/tui/test_config_center_resume.py::test_repeated_opener_without_history_keeps_one_zero_pane_home
FAILED tests/ace/tui/test_config_center_resume.py::test_generic_reopen_is_home_first_then_repeated_opener_resumes
FAILED tests/ace/tui/test_config_center_resume.py::test_switching_changes_resume_target_and_home_only_close_retains_it
FAILED tests/ace/tui/test_config_center_resume.py::test_direct_entry_establishes_resume_target_after_success
FAILED tests/ace/tui/test_config_center_resume.py::test_new_process_loads_remembered_admin_center_section
FAILED tests/ace/tui/test_config_center_resume.py::test_persisted_tab_seeds_home_and_repeated_opener_resume
FAILED tests/ace/tui/test_config_center_resume.py::test_invalid_persisted_tab_keeps_no_history_home
FAILED tests/ace/tui/test_config_center_resume.py::test_blocked_write_keeps_navigation_responsive_and_persists_latest
FAILED tests/ace/tui/test_config_center_resume.py::test_write_failure_is_nonfatal_and_same_tab_can_retry
FAILED tests/ace/tui/test_config_center_resume.py::test_failed_resume_retains_prior_target_and_remains_retryable
FAILED tests/ace/tui/test_config_center_resume.py::test_custom_opener_opens_home_resumes_and_is_displayed
FAILED tests/ace/tui/test_config_center_resume.py::test_literal_opener_remains_typeable_and_cannot_nest_modal
FAILED tests/ace/tui/test_config_center_session.py::test_ace_app_reuses_one_session_state_across_modals
FAILED tests/ace/tui/test_config_center_session.py::test_home_only_open_does_not_create_panes_or_mutate_bookmarks
FAILED tests/ace/tui/test_config_center_session.py::test_distinct_ace_apps_do_not_share_session_state
FAILED tests/ace/tui/test_config_center_tabs.py::test_home_tab_directions_and_digits_mount_only_requested_panes
FAILED tests/ace/tui/test_config_center_tabs.py::test_landing_compact_class_tracks_viewport_size
FAILED tests/ace/tui/test_config_edit_modal_chezmoi_widget.py::test_chezmoi_write_applies_home_target_not_source
FAILED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_edit_string_writes_to_target
FAILED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_edit_back_from_preview_returns_to_edit
FAILED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_preview_scroll_keys_move_preview_region
FAILED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_bool_toggle_and_write
FAILED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_enum_navigation_digits_and_space
FAILED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_bool_digit_picks_visible_option
FAILED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_scalar_input_selects_all_on_open
FAILED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_multiline_string_uses_textarea
FAILED tests/ace/tui/test_config_edit_modal_editors_widget.py::test_yaml_textarea_uses_yaml_language
FAILED tests/ace/tui/test_config_edit_modal_layout_widget.py::test_large_yaml_value_keeps_editor_and_hints_visible
FAILED tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
FAILED tests/ace/tui/test_config_edit_modal_scope_widget.py::test_cycle_scope_changes_target
FAILED tests/ace/tui/test_config_edit_modal_scope_widget.py::test_scope_selector_row_pick_changes_target
FAILED tests/ace/tui/test_config_edit_modal_scope_widget.py::test_new_overlay_switches_scope_to_created_overlay
FAILED tests/ace/tui/test_config_edit_modal_validation_widget.py::test_reset_to_default_plans_unset
FAILED tests/ace/tui/test_config_edit_modal_validation_widget.py::test_client_constraint_blocks_plan
FAILED tests/ace/tui/test_config_edit_modal_validation_widget.py::test_live_validation_error_appears_and_clears
FAILED tests/ace/tui/test_config_edit_modal_validation_widget.py::test_schema_validation_blocks_write
FAILED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_two_stage_escape_backs_out_of_modal
FAILED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_enter_submits_from_normal_mode
FAILED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_normal_mode_edit_fires_live_validation
FAILED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_normal_mode_dd_edits_yaml_editor
FAILED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_ctrl_s_confirms_from_yaml_editor
FAILED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_ctrl_r_toggles_reset_from_insert_mode
FAILED tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_memory_glossary_bare_digit_selects_admin_tab_prefixed_follows
FAILED tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_memory_bare_digit_selects_admin_tab_prefixed_follows
FAILED tests/ace/tui/test_config_hub_numbered_links.py::test_embedded_snippets_bare_digit_still_follows_locally
FAILED tests/ace/tui/test_config_hub_pane.py::test_opening_config_constructs_only_the_active_child
FAILED tests/ace/tui/test_config_hub_pane.py::test_resize_switches_caption_variant_without_reloading_children
FAILED tests/ace/tui/test_config_hub_pane_navigation.py::test_filter_brackets_cycle_config_subtabs
FAILED tests/ace/tui/test_config_hub_pane_navigation.py::test_config_filter_keeps_prefix_digits_as_text
FAILED tests/ace/tui/test_config_pane_widget.py::test_config_pane_loads_and_populates_tree
FAILED tests/ace/tui/test_config_pane_widget.py::test_config_pane_restores_session_bookmark_by_path
FAILED tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_narrows_tree
FAILED tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_updates_title_match_count
FAILED tests/ace/tui/test_config_pane_widget.py::test_config_filter_brackets_cycle_subtabs_and_tab_switches_main_tab
FAILED tests/ace/tui/test_config_pane_widget.py::test_config_pane_modified_only_toggle
FAILED tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_j_k_wrap_visible_tree_and_arrows_clamp
FAILED tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_j_k_cycle_single_visible_row
FAILED tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_g_and_G_jump_tree_cursor
FAILED tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_h_l_collapse_expand_and_descend
FAILED tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_ctrl_d_and_ctrl_u_scroll_detail_only
FAILED tests/ace/tui/test_plugins_browser_pane_loading.py::test_config_center_cycles_all_tabs
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_plugin_mark_survives_filter_hide_and_is_consumed_by_install
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_cli_mark_consumed_by_update_when_cli_rows_hidden
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_plugin_marks_do_not_constrain_unmarked_cli_update
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_escape_clears_plugin_and_cli_marks_in_one_press
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_mark_all_respects_filter_and_section_capabilities
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_mark_all_keeps_builtin_and_community_plugins_apart
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_mark_all_unmarkable_row_warns_like_space
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_pane_bindings_have_no_duplicate_keys
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_asterisk_press_marks_all_without_saved_query_picker
FAILED tests/ace/tui/test_statistics_pane_loading.py::test_overview_revalidation_tick_never_paints_loading
FAILED tests/ace/tui/test_artifacts_post_paint_publication.py::test_retry_after_failed_discovery_retains_generation
FAILED tests/ace/tui/test_artifacts_post_paint_publication.py::test_shutdown_before_completion_discards_late_result
FAILED tests/ace/tui/test_artifacts_post_paint_publication.py::test_healthy_provider_is_replaced_when_it_degrades
FAILED tests/ace/tui/test_artifacts_post_paint_publication.py::test_open_palette_selects_newly_published_command
FAILED tests/ace/tui/test_artifacts_post_paint_publication.py::test_scope_change_during_staging_is_applied_before_commit
FAILED tests/ace/tui/test_artifacts_post_paint_publication.py::test_stale_epoch_is_rejected_then_coalesced
FAILED tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_hint_gated_on_installed
FAILED tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_not_installed_toasts
FAILED tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_disabled_when_not_uv_tool
FAILED tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_reload_clears_freshness_while_in_progress
FAILED tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_offline_reload_does_not_retain_freshness
FAILED tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_confirm_submits_actual_written_source
FAILED tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_cancelled_failed_clean_and_non_git_skip_prompt
FAILED tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_paints_hints_over_visible_rows_in_order
FAILED tests/ace/tui/test_projects_pane_init_flow_single.py::test_i_on_drifted_project_submits_check_and_sets_status
FAILED tests/ace/tui/test_projects_pane_init_flow_single.py::test_current_payload_opens_no_modal_and_toasts
FAILED tests/ace/tui/test_artifacts_plans_filtering.py::test_deep_archive_coverage_label_is_visible_in_idle_status_lane
FAILED tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_successful_write_toast_text
FAILED tests/ace/tui/test_plugins_browser_pane_marks.py::test_mark_all_updatable_clis_share_one_verb
=== 173 failed, 63807 passed, 17 skipped, 164 warnings in 839.18s (0:13:59) ====
error: recipe `test-scoped` failed on line 723 with exit code 1
error: recipe `check` failed on line 1004 with exit code 1
failed  exit=1  duration=1156595ms
unattrib  34.6s
triage test (scoped): 1 FLAKY 169 NEW stopped
NEW test (scoped): FAILED tests/test_detach_scope_bootstrap.py::test_monitor_supervisor_bootstrap_uses_detach_scope — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/test_config_center_resume.py::test_persisted_tab_seeds_home_and_repeated_opener_resume — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_chop_sdk.py::test_all_builtin_chop_modules_use_the_registry — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_core_health.py::test_cli_health_json_ok - ModuleNotFoundErr... — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_config_merge.py::test_config_show_projects_public_axe_contract — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_commit_workflow_checkpointing.py::test_no_staged_changes_conflict_checkpoint_marks_no_commit_dispatched — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_meta_changespec_strips_whitespace — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/test_config_edit_modal_vim_widget.py::test_two_stage_escape_backs_out_of_modal — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/test_config_edit_modal_validation_widget.py::test_schema_validation_blocks_write — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/test_config_center_tabs.py::test_home_tab_directions_and_digits_mount_only_requested_panes — recorded evidence; no owner
FLAKY test (scoped): FAILED tests/test_commit_workflow_resume_recovery.py::test_resume_failed_finalize_returns_failed — recorded evidence; no owner
verdict: new_failures — 169 NEW, 1 FLAKY; exit 1

