# Chat History - ace-run (toobig-8w.publication_snapshot.0--mon)

- **TIMESTAMP:** 2026-10-30 15:21:18 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-8w.publication_snapshot.0--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'finish check (joined run)'

## Response

sase tool run a401a53099a1f03e226de0fada4a5500
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
[core-floor-probe] stale_actionable: sase-core-rs==0.42.7 is missing 62 capability(s) that exist in a published sase-core release.
[core-floor-probe] advance_agent_run_state_schedule: first appears in sase-core 7de361c (feat(agent-run-state): add shared reconciliation policy and bindings); release v0.43.2 contains it.
[core-floor-probe] agent_publication_protection_wire_schema_version: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] agent_run_state_wire_schema_version: first appears in sase-core 7de361c (feat(agent-run-state): add shared reconciliation policy and bindings); release v0.43.2 contains it.
[core-floor-probe] agent_stats_query_macro_usage: first appears in sase-core 31deb0d (feat(stats): add query_macro_usage and accept config via); release v0.43.1 contains it.
[core-floor-probe] artifact_link_collision_partition: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); release v0.43.1 contains it.
[core-floor-probe] artifact_link_collision_wire_schema_version: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); release v0.43.1 contains it.
[core-floor-probe] artifact_link_quarantine_record_canonical_json: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); release v0.43.1 contains it.
[core-floor-probe] artifact_link_quarantine_record_path: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); release v0.43.1 contains it.
[core-floor-probe] artifact_link_quarantine_record_validate: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); release v0.43.1 contains it.
[core-floor-probe] artifact_link_quarantine_wire_schema_version: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); release v0.43.1 contains it.
[core-floor-probe] assess_repository_landing_proof: first appears in sase-core 800caef (fix(beads): recover every eligible failed-run close in one mutation); release v0.43.0 contains it.
[core-floor-probe] bead_recover_failed_closes: first appears in sase-core 4f17b72 (feat(beads): recover failed-run closes atomically); release v0.43.0 contains it.
[core-floor-probe] build_gate_staged_payload: first appears in sase-core f4aa8fb (feat(gate): Rust-owned staged gate payload and workspace disposition); release v0.43.2 contains it.
[core-floor-probe] build_rebase_gate_context: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); release v0.43.1 contains it.
[core-floor-probe] check_repository_action: first appears in sase-core 24e160d (feat(core-policy): add handoff disposition and prepared-coverage predicates with bindings); release v0.43.1 contains it.
[core-floor-probe] classify_rebase_gate_result: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); release v0.43.1 contains it.
[core-floor-probe] classify_sidecar_publication_push_result: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] continuation_evaluate_prepared_reservation_access: first appears in sase-core 2a62513 (feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts); release v0.43.2 contains it.
[core-floor-probe] continuation_evaluate_prepared_starter_coverage: first appears in sase-core 24e160d (feat(core-policy): add handoff disposition and prepared-coverage predicates with bindings); release v0.43.1 contains it.
[core-floor-probe] evaluate_host_stage_admission: first appears in sase-core 17e79c8 (feat(gate): Rust-owned host preparation admission for workflow reviews); release v0.43.2 contains it.
[core-floor-probe] evaluate_stage_admission: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); release v0.43.1 contains it.
[core-floor-probe] evaluate_staged_monitor_membership: first appears in sase-core 2a62513 (feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts); release v0.43.2 contains it.
[core-floor-probe] evaluate_staged_owner_liveness: first appears in sase-core 2a62513 (feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts); release v0.43.2 contains it.
[core-floor-probe] evaluate_staged_self_wait: first appears in sase-core 2a62513 (feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts); release v0.43.2 contains it.
[core-floor-probe] footprint_card: first appears in sase-core 83b010d (feat(footprint): add lens engine, evidence states, and review decisions); release v0.43.1 contains it.
[core-floor-probe] footprint_catalog_status: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); release v0.43.1 contains it.
[core-floor-probe] footprint_clear: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); release v0.43.1 contains it.
[core-floor-probe] footprint_decide: first appears in sase-core 83b010d (feat(footprint): add lens engine, evidence states, and review decisions); release v0.43.1 contains it.
[core-floor-probe] footprint_export: first appears in sase-core 65546fd (feat(footprint): add identity-free weekly export and replace-all import); release v0.43.1 contains it.
[core-floor-probe] footprint_fold: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); release v0.43.1 contains it.
[core-floor-probe] footprint_import: first appears in sase-core 65546fd (feat(footprint): add identity-free weekly export and replace-all import); release v0.43.1 contains it.
[core-floor-probe] footprint_ingest_catalog: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); release v0.43.1 contains it.
[core-floor-probe] footprint_prune: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); release v0.43.1 contains it.
[core-floor-probe] footprint_report: first appears in sase-core 83b010d (feat(footprint): add lens engine, evidence states, and review decisions); release v0.43.1 contains it.
[core-floor-probe] footprint_status: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); release v0.43.1 contains it.
[core-floor-probe] footprint_upsert_derived: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); release v0.43.1 contains it.
[core-floor-probe] footprint_validate_overlay: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); release v0.43.1 contains it.
[core-floor-probe] footprint_wire_schema_version: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); release v0.43.1 contains it.
[core-floor-probe] gate_staged_payload_schema_version: first appears in sase-core f4aa8fb (feat(gate): Rust-owned staged gate payload and workspace disposition); release v0.43.2 contains it.
[core-floor-probe] merge_rebase_gate_contexts: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); release v0.43.1 contains it.
[core-floor-probe] publication_protection_ledger_empty: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_ledger_validate: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_lookup: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_rejection: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_scan: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_resolve_verified_clean: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_retry_allowed: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_upsert: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_scan_disposition: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] rebase_gate_wire_schema_version: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); release v0.43.1 contains it.
[core-floor-probe] resolve_agent_run_state: first appears in sase-core 7de361c (feat(agent-run-state): add shared reconciliation policy and bindings); release v0.43.2 contains it.
[core-floor-probe] select_agent_run_state_window: first appears in sase-core 7de361c (feat(agent-run-state): add shared reconciliation policy and bindings); release v0.43.2 contains it.
[core-floor-probe] staged_handoff_receipt_authorizes: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); release v0.43.1 contains it.
[core-floor-probe] staged_handoff_wire_schema_version: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); release v0.43.1 contains it.
[core-floor-probe] staged_monitor_launch_payload_schema_version: first appears in sase-core 2a62513 (feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts); release v0.43.2 contains it.
[core-floor-probe] update_rebase_gate_context: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); release v0.43.1 contains it.
[core-floor-probe] validate_finalizer_handoff: first appears in sase-core 24e160d (feat(core-policy): add handoff disposition and prepared-coverage predicates with bindings); release v0.43.1 contains it.
[core-floor-probe] validate_gate_staged_payload: first appears in sase-core f4aa8fb (feat(gate): Rust-owned staged gate payload and workspace disposition); release v0.43.2 contains it.
[core-floor-probe] validate_rebase_gate_timeout_seconds: first appears in sase-core 4f0fe37 (feat(vcs): add rebase gate policy and bindings); release v0.43.1 contains it.
[core-floor-probe] validate_staged_handoff: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); release v0.43.1 contains it.
[core-floor-probe] validate_staged_handoff_receipt: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); release v0.43.1 contains it.
[core-floor-probe] validate_staged_monitor_launch_payload: first appears in sase-core 2a62513 (feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts); release v0.43.2 contains it.
{"cache_hit": true, "capabilities": [{"commit": "7de361c", "name": "advance_agent_run_state_schedule", "release": "v0.43.2", "subject": "feat(agent-run-state): add shared reconciliation policy and bindings"}, {"commit": "416db28", "name": "agent_publication_protection_wire_schema_version", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "7de361c", "name": "agent_run_state_wire_schema_version", "release": "v0.43.2", "subject": "feat(agent-run-state): add shared reconciliation policy and bindings"}, {"commit": "31deb0d", "name": "agent_stats_query_macro_usage", "release": "v0.43.1", "subject": "feat(stats): add query_macro_usage and accept config via"}, {"commit": "6613c9b", "name": "artifact_link_collision_partition", "release": "v0.43.1", "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_collision_wire_schema_version", "release": "v0.43.1", "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_canonical_json", "release": "v0.43.1", "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_path", "release": "v0.43.1", "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_validate", "release": "v0.43.1", "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_wire_schema_version", "release": "v0.43.1", "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "800caef", "name": "assess_repository_landing_proof", "release": "v0.43.0", "subject": "fix(beads): recover every eligible failed-run close in one mutation"}, {"commit": "4f17b72", "name": "bead_recover_failed_closes", "release": "v0.43.0", "subject": "feat(beads): recover failed-run closes atomically"}, {"commit": "f4aa8fb", "name": "build_gate_staged_payload", "release": "v0.43.2", "subject": "feat(gate): Rust-owned staged gate payload and workspace disposition"}, {"commit": "60fe51d", "name": "build_rebase_gate_context", "release": "v0.43.1", "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "24e160d", "name": "check_repository_action", "release": "v0.43.1", "subject": "feat(core-policy): add handoff disposition and prepared-coverage predicates with bindings"}, {"commit": "60fe51d", "name": "classify_rebase_gate_result", "release": "v0.43.1", "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "416db28", "name": "classify_sidecar_publication_push_result", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "2a62513", "name": "continuation_evaluate_prepared_reservation_access", "release": "v0.43.2", "subject": "feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts"}, {"commit": "24e160d", "name": "continuation_evaluate_prepared_starter_coverage", "release": "v0.43.1", "subject": "feat(core-policy): add handoff disposition and prepared-coverage predicates with bindings"}, {"commit": "17e79c8", "name": "evaluate_host_stage_admission", "release": "v0.43.2", "subject": "feat(gate): Rust-owned host preparation admission for workflow reviews"}, {"commit": "cd62c83", "name": "evaluate_stage_admission", "release": "v0.43.1", "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "2a62513", "name": "evaluate_staged_monitor_membership", "release": "v0.43.2", "subject": "feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts"}, {"commit": "2a62513", "name": "evaluate_staged_owner_liveness", "release": "v0.43.2", "subject": "feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts"}, {"commit": "2a62513", "name": "evaluate_staged_self_wait", "release": "v0.43.2", "subject": "feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts"}, {"commit": "83b010d", "name": "footprint_card", "release": "v0.43.1", "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_catalog_status", "release": "v0.43.1", "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_clear", "release": "v0.43.1", "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_decide", "release": "v0.43.1", "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "65546fd", "name": "footprint_export", "release": "v0.43.1", "subject": "feat(footprint): add identity-free weekly export and replace-all import"}, {"commit": "2d0b62e", "name": "footprint_fold", "release": "v0.43.1", "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "65546fd", "name": "footprint_import", "release": "v0.43.1", "subject": "feat(footprint): add identity-free weekly export and replace-all import"}, {"commit": "2d0b62e", "name": "footprint_ingest_catalog", "release": "v0.43.1", "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_prune", "release": "v0.43.1", "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_report", "release": "v0.43.1", "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_status", "release": "v0.43.1", "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_upsert_derived", "release": "v0.43.1", "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_validate_overlay", "release": "v0.43.1", "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_wire_schema_version", "release": "v0.43.1", "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "f4aa8fb", "name": "gate_staged_payload_schema_version", "release": "v0.43.2", "subject": "feat(gate): Rust-owned staged gate payload and workspace disposition"}, {"commit": "60fe51d", "name": "merge_rebase_gate_contexts", "release": "v0.43.1", "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "416db28", "name": "publication_protection_ledger_empty", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_ledger_validate", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_lookup", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_rejection", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_scan", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_resolve_verified_clean", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_retry_allowed", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_upsert", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_scan_disposition", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "60fe51d", "name": "rebase_gate_wire_schema_version", "release": "v0.43.1", "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "7de361c", "name": "resolve_agent_run_state", "release": "v0.43.2", "subject": "feat(agent-run-state): add shared reconciliation policy and bindings"}, {"commit": "7de361c", "name": "select_agent_run_state_window", "release": "v0.43.2", "subject": "feat(agent-run-state): add shared reconciliation policy and bindings"}, {"commit": "cd62c83", "name": "staged_handoff_receipt_authorizes", "release": "v0.43.1", "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "cd62c83", "name": "staged_handoff_wire_schema_version", "release": "v0.43.1", "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "2a62513", "name": "staged_monitor_launch_payload_schema_version", "release": "v0.43.2", "subject": "feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts"}, {"commit": "60fe51d", "name": "update_rebase_gate_context", "release": "v0.43.1", "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "24e160d", "name": "validate_finalizer_handoff", "release": "v0.43.1", "subject": "feat(core-policy): add handoff disposition and prepared-coverage predicates with bindings"}, {"commit": "f4aa8fb", "name": "validate_gate_staged_payload", "release": "v0.43.2", "subject": "feat(gate): Rust-owned staged gate payload and workspace disposition"}, {"commit": "4f0fe37", "name": "validate_rebase_gate_timeout_seconds", "release": "v0.43.1", "subject": "feat(vcs): add rebase gate policy and bindings"}, {"commit": "cd62c83", "name": "validate_staged_handoff", "release": "v0.43.1", "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "cd62c83", "name": "validate_staged_handoff_receipt", "release": "v0.43.1", "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "2a62513", "name": "validate_staged_monitor_launch_payload", "release": "v0.43.2", "subject": "feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts"}], "declared_floor": "0.42.7", "exit_code": 3, "message": "sase-core-rs==0.42.7 is missing 62 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 5508 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1253s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 46s, heartbeat 45s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1283s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 76s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1313s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 106s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1343s, heartbeat 0s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 136s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1373s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 166s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1403s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 196s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1433s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 226s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1463s, heartbeat 1s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 256s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1493s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 286s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1523s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 316s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1553s, heartbeat 0s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 346s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1583s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 376s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1613s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 406s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1643s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 436s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1674s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 466s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1704s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 496s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1734s, heartbeat 5s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 526s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1764s, heartbeat 5s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 556s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1794s, heartbeat 5s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 586s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1824s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 616s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1854s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 646s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1884s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 676s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1914s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 706s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1944s, heartbeat 0s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 736s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 1974s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 766s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2004s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 796s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2034s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 826s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2064s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 856s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 3263961, grant 1, age 5s, heartbeat 2s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/4c99d281707740048772e84b1c8751ac/capture --sase-visual-capture-run-id 4c99d281707740048772e84b1c8751ac --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2094s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 886s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 3275030, grant 1, age 1s, heartbeat 1s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/4c99d281707740048772e84b1c8751ac/recover-1 --sase-visual-capture-run-id 4c99d281707740048772e84b1c8751ac-recover-1 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2124s, heartbeat 5s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 917s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 3275030, grant 1, age 31s, heartbeat 3s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/4c99d281707740048772e84b1c8751ac/recover-1 --sase-visual-capture-run-id 4c99d281707740048772e84b1c8751ac-recover-1 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2154s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 947s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 3296510, grant 1, age 28s, heartbeat 25s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/4c99d281707740048772e84b1c8751ac/recover-2 --sase-visual-capture-run-id 4c99d281707740048772e84b1c8751ac-recover-2 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2184s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 977s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2214s, heartbeat 1s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1007s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 3332992, grant 1, age 21s, heartbeat 18s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/b5fd7850e69f471dafa497547275fe89/capture --sase-visual-capture-run-id b5fd7850e69f471dafa497547275fe89 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2244s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1037s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 3344865, grant 1, age 18s, heartbeat 15s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/b5fd7850e69f471dafa497547275fe89/recover-1 --sase-visual-capture-run-id b5fd7850e69f471dafa497547275fe89-recover-1 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2274s, heartbeat 6s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1067s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 3356520, grant 1, age 13s, heartbeat 10s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/b5fd7850e69f471dafa497547275fe89/recover-2 --sase-visual-capture-run-id b5fd7850e69f471dafa497547275fe89-recover-2 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2304s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1097s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2334s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1127s, heartbeat 0s, argv 'tools/run_pytest scoped'; 1 token: pid 3364236, grant 1, age 28s, heartbeat 24s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/8fd3b9ef8d7743ab8c157325a168592f/capture --sase-visual-capture-run-id 8fd3b9ef8d7743ab8c157325a168592f --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2364s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1157s, heartbeat 0s, argv 'tools/run_pytest scoped'; 1 token: pid 3372388, grant 1, age 24s, heartbeat 21s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/8fd3b9ef8d7743ab8c157325a168592f/recover-1 --sase-visual-capture-run-id 8fd3b9ef8d7743ab8c157325a168592f-recover-1 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2394s, heartbeat 1s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1187s, heartbeat 5s, argv 'tools/run_pytest scoped'; 1 token: pid 3380297, grant 1, age 21s, heartbeat 18s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/8fd3b9ef8d7743ab8c157325a168592f/recover-2 --sase-visual-capture-run-id 8fd3b9ef8d7743ab8c157325a168592f-recover-2 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2424s, heartbeat 5s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1217s, heartbeat 3s, argv 'tools/run_pytest scoped'; 1 token: pid 3394785, grant 1, age 0s, heartbeat 0s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/c46b2d5e39504be9bfe12973d4e41fe9/capture --sase-visual-capture-run-id c46b2d5e39504be9bfe12973d4e41fe9 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2454s, heartbeat 5s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1247s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2484s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1277s, heartbeat 3s, argv 'tools/run_pytest scoped'; 1 token: pid 3404898, grant 1, age 21s, heartbeat 18s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/6f18913cc1904b4d91ea0a0cf99022cf/capture --sase-visual-capture-run-id 6f18913cc1904b4d91ea0a0cf99022cf --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2514s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1307s, heartbeat 3s, argv 'tools/run_pytest scoped'; 1 token: pid 3410016, grant 1, age 18s, heartbeat 16s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/6f18913cc1904b4d91ea0a0cf99022cf/recover-1 --sase-visual-capture-run-id 6f18913cc1904b4d91ea0a0cf99022cf-recover-1 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2544s, heartbeat 2s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1337s, heartbeat 3s, argv 'tools/run_pytest scoped'; 1 token: pid 3421699, grant 1, age 15s, heartbeat 12s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/6f18913cc1904b4d91ea0a0cf99022cf/recover-2 --sase-visual-capture-run-id 6f18913cc1904b4d91ea0a0cf99022cf-recover-2 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2574s, heartbeat 5s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1367s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2604s, heartbeat 0s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1397s, heartbeat 1s, argv 'tools/run_pytest scoped'; 1 token: pid 3438197, grant 1, age 3s, heartbeat 0s, argv 'tools/run_pytest fast tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_resize_block_refresh_keeps_preferred_main_card tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_spread_to_paged_resize_keeps_preferred_main_card'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2634s, heartbeat 4s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1427s, heartbeat 0s, argv 'tools/run_pytest scoped'; 1 token: pid 3441477, grant 1, age 9s, heartbeat 6s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/8152101ed7004a2aab52338fb0c5d2be/capture --sase-visual-capture-run-id 8152101ed7004a2aab52338fb0c5d2be --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2664s, heartbeat 0s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1457s, heartbeat 5s, argv 'tools/run_pytest scoped'; 1 token: pid 3446183, grant 1, age 18s, heartbeat 2s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/8152101ed7004a2aab52338fb0c5d2be/verify --sase-visual-capture-run-id 8152101ed7004a2aab52338fb0c5d2be-verify --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2694s, heartbeat 0s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1487s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2724s, heartbeat 3s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1517s, heartbeat 1s, argv 'tools/run_pytest scoped'; 1 token: pid 3453651, grant 1, age 15s, heartbeat 12s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/7bc6e8eb2402462d9b8301daff4ee450/capture --sase-visual-capture-run-id 7bc6e8eb2402462d9b8301daff4ee450 --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 1 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2754s, heartbeat 5s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1547s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2785s, heartbeat 1s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1577s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 3466450, grant 1, age 10s, heartbeat 7s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/64068ac1d7b04295af729c3b4f4cb4df/capture --sase-visual-capture-run-id 64068ac1d7b04295af729c3b4f4cb4df --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_session_panel_monitor.py::test_agent_session_panel_turns_monitor_metadata_png_snapshot tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots'
Waiting for a SASE pytest worker-token grant of 4-9 worker tokens; 0 tokens were available below the floor. Current holders: 4 tokens: pid 2025495, grant 4, age 2815s, heartbeat 0s, argv 'tools/run_pytest scoped'; 7 tokens: pid 2942523, grant 7, age 1607s, heartbeat 15s, argv 'tools/run_pytest scoped'; 1 token: pid 3466450, grant 1, age 40s, heartbeat 20s, argv '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/run_pytest visual --sase-visual-capture-dir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.pytest_cache/sase-visual/runs/64068ac1d7b04295af729c3b4f4cb4df/capture --sase-visual-capture-run-id 64068ac1d7b04295af729c3b4f4cb4df --sase-visual-capture-scope targeted --sase-visual-capture-ace-root tests/ace/tui/visual/snapshots/png --sase-visual-capture-pager-root tests/pager/visual/snapshots/png tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_session_panel_monitor.py::test_agent_session_panel_turns_monitor_metadata_png_snapshot tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_live_reply_partial_and_growth_png_snapshots tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots'
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, platformdirs-4.12.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 7/7 workers
7 workers [59199 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
...........................................................s............ [  1%]
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
.s...................................................................... [  2%]
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
........................................................................ [  4%]
..................................................................s..... [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
...s.................................................................... [  6%]
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
........................................................................ [ 24%]
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
........................................................................ [ 35%]
........................................................................ [ 36%]
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
................................................s....................... [ 39%]
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
........................................................................ [ 42%]
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
........................................................................ [ 51%]
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
....................s................................................... [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
......................................................s................. [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
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
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
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
........................................................................ [ 61%]
........................................................................ [ 61%]
................................................................sss.s... [ 61%]
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
...........s............................................................ [ 70%]
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
..........................................F............................. [ 72%]
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
.....................................................s.................. [ 76%]
........................................................................ [ 76%]
..................................................s..s.................. [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
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
...................................s.................................... [ 91%]
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
........................................................................ [ 96%]
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
........................................................................ [ 99%]
........................................................................ [ 99%]
...............                                                          [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
________________ test_tui_app_import_stays_under_startup_budget ________________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

    def test_tui_app_import_stays_under_startup_budget() -> None:
        """Importing the app should not pull known heavy deferred profile edges."""
    
        last_elapsed = 0.0
        last_sase_count = 0
        last_count = 0
        for _ in range(2):
>           payload = _measure_tui_app_import()
                      ^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_app_import_budget.py:179: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/test_app_import_budget.py:129: in _measure_tui_app_import
    _assert_sase_module_budget(sase_module_count)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

sase_module_count = 2861, cap = 2861

    def _assert_sase_module_budget(
        sase_module_count: int, *, cap: int = _MAX_SASE_MODULE_COUNT
    ) -> None:
>       assert sase_module_count < cap, (
            f"TUI app import loads {sase_module_count} sase.* modules "
            f"against the {cap} cap; attribute the growth with "
            f"`tools/tui_import_closure --diff "
            f"$(git merge-base HEAD origin/master)` and defer the new edges"
        )
E       AssertionError: TUI app import loads 2861 sase.* modules against the 2861 cap; attribute the growth with `tools/tui_import_closure --diff $(git merge-base HEAD origin/master)` and defer the new edges
E       assert 2861 < 2861

tests/ace/tui/test_app_import_budget.py:57: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=3472959) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:200: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    memo[id(x)] = y
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
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

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/macro/workflow_runner.py:477: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=3472939) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=3472939) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=3472947) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_lookup.py::test_coalesced_idle_does_not_publish_false_missing_for_queued_open
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:112: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    doc = getattr(func, "__doc__", None)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:1725: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return ((p, type(p)) for p in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
64.88s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
63.42s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
62.57s call     tests/test_launch_request_staging.py::test_typed_plan_and_continuation_survive_adoption
58.15s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
49.02s call     tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows
32.50s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
30.42s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
30.34s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
27.36s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
21.20s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
19.42s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
19.30s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
18.96s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
18.18s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
16.18s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
15.51s call     tests/test_sdd_commit.py::test_commit_sdd_files_removes_persistent_index_lock_after_retry_exhausted
15.31s call     tests/test_bare_git_init.py::TestInitBareGitProject::test_git_runner_removes_persistent_index_lock_after_retries
15.01s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
14.98s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
14.59s call     tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly
=========================== short test summary info ============================
FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget
==== 1 failed, 59182 passed, 17 skipped, 127 warnings in 1577.15s (0:26:17) ====
error: recipe `test-scoped` failed on line 649 with exit code 1
error: recipe `check` failed on line 915 with exit code 1
failed/1  3681294ms
triage test (scoped): 1 NEW
NEW test (scoped): FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget — recorded evidence; no owner
sase tool show a401a53099a1f03e226de0fada4a5500 -l
verdict: new_failures — 1 NEW; exit 1

