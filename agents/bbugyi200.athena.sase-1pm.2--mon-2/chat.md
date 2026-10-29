# Chat History - ace-run (sase-1pm.2--mon-2)

- **TIMESTAMP:** 2026-10-29 05:55:36 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1pm.2--mon-2

## Prompt

sase monitor start --command 'just check' --reason 'Verify TERM pin before host completion of sase-1pm.2; workspace fast-forwarded onto origin/master so stale sase-1pj.1.1.4 epic-symbol lint is gone; root-conftest change still escalates just check to the full suite'

## Response

sase tool run fd2ea3beb0f5ce99226c3dac8917d32a
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.42.7 is missing 44 capability(s), and at least one has no containing sase-core release tag yet.
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
[core-floor-probe] build_rebase_gate_context: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); no release tag contains it yet.
[core-floor-probe] classify_rebase_gate_result: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); no release tag contains it yet.
[core-floor-probe] classify_sidecar_publication_push_result: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] evaluate_stage_admission: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); no release tag contains it yet.
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
[core-floor-probe] merge_rebase_gate_contexts: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); no release tag contains it yet.
[core-floor-probe] publication_protection_ledger_empty: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_ledger_validate: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_lookup: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_rejection: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_scan: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_resolve_verified_clean: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_retry_allowed: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_upsert: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_scan_disposition: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] rebase_gate_wire_schema_version: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); no release tag contains it yet.
[core-floor-probe] staged_handoff_receipt_authorizes: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); no release tag contains it yet.
[core-floor-probe] staged_handoff_wire_schema_version: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); no release tag contains it yet.
[core-floor-probe] update_rebase_gate_context: first appears in sase-core 60fe51d (feat(vcs): add rebase gate policy bindings); no release tag contains it yet.
[core-floor-probe] validate_staged_handoff: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); no release tag contains it yet.
[core-floor-probe] validate_staged_handoff_receipt: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "416db28", "name": "agent_publication_protection_wire_schema_version", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "31deb0d", "name": "agent_stats_query_macro_usage", "release": null, "subject": "feat(stats): add query_macro_usage and accept config via"}, {"commit": "6613c9b", "name": "artifact_link_collision_partition", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_collision_wire_schema_version", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_canonical_json", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_path", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_validate", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_wire_schema_version", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "800caef", "name": "assess_repository_landing_proof", "release": "v0.43.0", "subject": "fix(beads): recover every eligible failed-run close in one mutation"}, {"commit": "4f17b72", "name": "bead_recover_failed_closes", "release": "v0.43.0", "subject": "feat(beads): recover failed-run closes atomically"}, {"commit": "60fe51d", "name": "build_rebase_gate_context", "release": null, "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "60fe51d", "name": "classify_rebase_gate_result", "release": null, "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "416db28", "name": "classify_sidecar_publication_push_result", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "cd62c83", "name": "evaluate_stage_admission", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "83b010d", "name": "footprint_card", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_catalog_status", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_clear", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_decide", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "65546fd", "name": "footprint_export", "release": null, "subject": "feat(footprint): add identity-free weekly export and replace-all import"}, {"commit": "2d0b62e", "name": "footprint_fold", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "65546fd", "name": "footprint_import", "release": null, "subject": "feat(footprint): add identity-free weekly export and replace-all import"}, {"commit": "2d0b62e", "name": "footprint_ingest_catalog", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_prune", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_report", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_status", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_upsert_derived", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_validate_overlay", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_wire_schema_version", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "60fe51d", "name": "merge_rebase_gate_contexts", "release": null, "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "416db28", "name": "publication_protection_ledger_empty", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_ledger_validate", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_lookup", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_rejection", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_scan", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_resolve_verified_clean", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_retry_allowed", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_upsert", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_scan_disposition", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "60fe51d", "name": "rebase_gate_wire_schema_version", "release": null, "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "cd62c83", "name": "staged_handoff_receipt_authorizes", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "cd62c83", "name": "staged_handoff_wire_schema_version", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "60fe51d", "name": "update_rebase_gate_context", "release": null, "subject": "feat(vcs): add rebase gate policy bindings"}, {"commit": "cd62c83", "name": "validate_staged_handoff", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "cd62c83", "name": "validate_staged_handoff_receipt", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}], "declared_floor": "0.42.7", "exit_code": 4, "message": "sase-core-rs==0.42.7 is missing 44 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed, root-conftest); 5465 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed, root-conftest)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.12.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [58734 items]

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
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
......................................................................s. [  2%]
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
............s........................................................... [  4%]
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
.............................................................s.......... [  7%]
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
.............................s.......................................... [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
..........s............................................................. [  9%]
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
.......................................................................s [ 12%]
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
........................................................................ [ 14%]
........................................................................ [ 14%]
...............................................................s........ [ 14%]
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
.............s.......................................................... [ 31%]
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
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
.............................s.......................................... [ 45%]
........................................................................ [ 45%]
...............................................................s.s...... [ 45%]
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
...........................s............................................ [ 51%]
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
........................................................................ [ 57%]
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
....................................................ssss................ [ 61%]
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
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
..........................................................F............. [ 63%]
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
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
...........................s............................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
.......................................................F................ [ 69%]
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
........................F............................................... [ 72%]
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
........................................................................ [ 82%]
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
.....................F.................................................. [ 88%]
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
......................................................                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
_____________ test_artifact_directory_operation_sites_are_reviewed _____________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/bin/python

    def test_artifact_directory_operation_sites_are_reviewed() -> None:
>       assert set(_artifact_directory_operation_contexts()) == set(
            _REVIEWED_DIR_OPERATION_CONTEXTS
        )
E       AssertionError: assert {'src/sase/_l...migrate', ...} == {'src/sase/_l...migrate', ...}
E         
E         Extra items in the left set:
E         'src/sase/workflows/commit/rebase_gate_runner.py:_cleanup_workdir'
E         
E         Full diff:
E           {
E               'src/sase/_linked_repo_workspaces.py:_remove_path',
E               'src/sase/_linked_repo_workspaces.py:clear_workspace_repos',
E               'src/sase/_linked_repo_workspaces.py:move_aside_for_background_delete',
E               'src/sase/ace/tui/bgcmd.py:dismiss_background_command',
E               'src/sase/agent/names/_wipe_execute.py:_remove_artifact_dirs',
E               'src/sase/agents/cli_artifacts_layout.py:_handle_migrate',
E               'src/sase/agents/cli_artifacts_layout.py:_handle_rollback',
E               'src/sase/agents_sync/_git_sync_ops_git.py:ensure_agents_clone',
E               'src/sase/agents_sync/purge_local_state.py:_apply_closure',
E               'src/sase/agents_sync/v2_io.py:_cleanup_transaction_dirs',
E               'src/sase/axe/run_agent_exec_attempts.py:_move_into_tmp',
E               'src/sase/axe/run_agent_exec_attempts.py:snapshot_attempt',
E               'src/sase/bead/attachments/lifecycle.py:quarantine_local_object',
E               'src/sase/bead/attachments/store.py:remove',
E               'src/sase/dev_update/prebuild_producer.py:_prune_completed_sets',
E               'src/sase/dev_update/prebuild_producer.py:produce_prebuild',
E               'src/sase/llm_provider/_codex_home.py:_try_delete_shadow_home',
E               'src/sase/llm_provider/_plan_utils.py:move_plan_to_sase',
E               'src/sase/main/project_handler_lifecycle.py:delete_project_locked',
E               'src/sase/main/repo_open_external.py:_remove_clone_staging_path',
E               'src/sase/main/workspace_handler_maintenance.py:remove_checkout',
E               'src/sase/main/workspace_handler_migration.py:handle_migrate',
E               'src/sase/migration_kit/atomic.py:_remove_path',
E               'src/sase/migration_kit/atomic.py:remove_path',
E               'src/sase/migration_kit/restore.py:_swap_into_place',
E               'src/sase/mode_switch/execute.py:_cleanup_failed_clone',
E               'src/sase/notification_gates/command_runner.py:_remove_untrusted_terminal',
E               'src/sase/notification_gates/service_creation.py:_start_gate_creation',
E               'src/sase/notification_gates/service_creation.py:create_gate',
E               'src/sase/procs/_migration.py:_perform_migration',
E               'src/sase/procs/_migration.py:_relocate_legacy_logs',
E               'src/sase/sdd/_bead_adoption.py:_copy_bead_state',
E               'src/sase/sdd/_bead_adoption.py:cleanup_plans_bead_state',
E               'src/sase/sdd/_store_adoption.py:cleanup_staging',
E               'src/sase/sdd/_store_clone_common.py:remove_partial_sdd_clone',
E               'src/sase/sdd/_store_clone_transaction.py:_remove_clone_stage_path',
E               'src/sase/sdd/_store_link.py:_replace_workspace_sdd_clone',
E               'src/sase/sudo/execution_handoff.py:cleanup_handoff',
E         +     'src/sase/workflows/commit/rebase_gate_runner.py:_cleanup_workdir',
E               'src/sase/workspace_provider/_rescue_git.py:_rescue_git_repo_body',
E               'src/sase/workspace_provider/_rescue_store.py:_quarantine_directory',
E               'src/sase/workspace_provider/_rescue_store.py:_reap_rescue_entries',
E               'src/sase/workspace_provider/_snapshot_capture_payload.py:_cleanup_capture_temps',
E               'src/sase/workspace_provider/_snapshot_capture_payload_objects.py:verify_pack',
E               'src/sase/workspace_provider/_snapshot_capture_source.py:_discard_incomplete',
E               'src/sase/workspace_provider/_snapshot_restore.py:_clear_worktree',
E               'src/sase/workspace_provider/_snapshot_restore.py:_restore_operation_markers',
E               'src/sase/workspace_provider/_utils_checkout.py:_remove_corrupt_checkout',
E               'src/sase/workspace_provider/_utils_git.py:abort_in_progress_git_operations',
E               'src/sase/workspace_provider/reset_replay.py:_clear_owned_paths',
E           }

tests/test_agent_artifact_directory_operation_audit.py:356: AssertionError
____ test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker ____
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-63c021a1/pytest-of-bryan/pytest-2/popen-gw6/test_start_monitor_kills_a_sup0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f2e4bd81320>

    def test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        write_project_file("proj")
        starter_dir = make_starter_agent(
            "proj",
            "20260812120000",
            "acme--0",
            agent_session="acme",
            model="claude-sonnet-5",
            workspace_dir=str(tmp_path),
            workspace_num=0,
            pid=os.getpid(),
            cl_name="acme",
        )
        patch_project_records(monkeypatch, [starter_dir])
    
        import sase.procs.spawn as spawn_module
    
        monkeypatch.setenv("SASE_PROC_START_ACK_TIMEOUT_SECONDS", "0.3")
    
        real_popen = spawn_module.subprocess.Popen
        spawned: list[subprocess.Popen[bytes]] = []
    
        def fake_popen(*args: object, **kwargs: object) -> object:
            del args
            # Alive, but wedged before it could write `.monitor_started`.
            stalled = real_popen(["sleep", "30"])
            spawned.append(stalled)
            pass_fds = kwargs["pass_fds"]
            assert isinstance(pass_fds, tuple)
            pid_fd = pass_fds[0]
            assert isinstance(pid_fd, int)
            os.write(pid_fd, json.dumps({"pid": stalled.pid}).encode() + b"\n")
            return SimpleNamespace(
                pid=stalled.pid, poll=lambda: 0, wait=lambda timeout=None: 0
            )
    
        monkeypatch.setattr(spawn_module.subprocess, "Popen", fake_popen)
    
        request = StartMonitorRequest(
            command="true",
            reason="verify",
            timeout_seconds=30.0,
            cwd=str(tmp_path),
            project_name="proj",
            start_status="MONITORING",
            stop_status="MONITORED",
            lane="acme",
            inherit_lane_workspace_claim=False,
        )
    
        with pytest.raises(MonitorError, match="did not acknowledge startup"):
            start_monitor(request)
    
>       assert len(spawned) == 1
E       AssertionError: assert 6 == 1
E        +  where 6 = len([<Popen: returncode: None args: ['sleep', '30']>, <Popen: returncode: None args: ['sleep', '30']>, <Popen: returncode:...gs: ['sleep', '30']>, <Popen: returncode: None args: ['sleep', '30']>, <Popen: returncode: None args: ['sleep', '30']>])

tests/monitor/test_monitor_start_ack.py:472: AssertionError
----------------------------- Captured stdout call -----------------------------
{"context": "monitor-settlement", "event": "launch_scratch_cleanup", "reason": "no-scratch-key", "removed": 0, "removed_bytes": 0, "scratch_key": null, "skipped": 0, "status": "skipped"}
_______ test_start_monitor_scrubs_agent_identity_from_the_supervisor_env _______
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-63c021a1/pytest-of-bryan/pytest-2/popen-gw6/test_start_monitor_scrubs_agen0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f2e4bd80590>

    def test_start_monitor_scrubs_agent_identity_from_the_supervisor_env(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        monkeypatch.setenv("SASE_AGENT", "1")
        monkeypatch.setenv("SASE_AGENT_NAME", "starter--0")
        monkeypatch.setenv("SASE_ARTIFACTS_DIR", "/dead/starter")
        monkeypatch.setenv("SASE_PROVIDER_SYNC_CEILING_SECONDS", "600")
        monkeypatch.setenv("SASE_PROVIDER_SYNC_SOFT_CEILING_SECONDS", "1200")
        write_project_file(
            "proj",
            running_claims=[WorkspaceClaim(3, "ace-run", "acme", pid=os.getpid())],
        )
        starter_dir = make_starter_agent(
            "proj",
            "20260812120000",
            "acme",
            model="claude-sonnet-5",
            workspace_dir=str(tmp_path),
            workspace_num=3,
            pid=os.getpid(),
            cl_name="acme",
        )
        patch_project_records(monkeypatch, [starter_dir])
    
        import sase.procs.spawn as spawn_module
    
        real_popen = spawn_module.subprocess.Popen
        captured_env: dict[str, str] = {}
    
        def fake_popen(*args: object, **kwargs: object) -> object:
            env = kwargs.get("env")
            if isinstance(env, dict):
                captured_env.update(env)
            return real_popen(*args, **kwargs)  # type: ignore[arg-type]
    
        monkeypatch.setattr(spawn_module.subprocess, "Popen", fake_popen)
    
        request = StartMonitorRequest(
            command="true",
            reason="verify",
            timeout_seconds=30.0,
            cwd=str(tmp_path),
            project_name="proj",
            start_status="MONITORING",
            stop_status="MONITORED",
            lane="acme",
        )
    
        record = start_monitor(request)
        wait_for_done(record.artifacts_dir)
    
>       assert "SASE_AGENT" not in captured_env
E       AssertionError: assert 'SASE_AGENT' not in {'PYENV_VIRTUALENV_INIT': '1', 'LIBRARY_PATH': '', 'MAVEN_OPTS': '-Dstyle.color=always', 'DBB': '/home/bryan/Sync/bin', ...}

tests/monitor/test_monitor_start_supervisor.py:155: AssertionError
_______________ test_contract_manifest_matches_marker_selection ________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/bin/python

    def test_contract_manifest_matches_marker_selection() -> None:
        tool = _load_refresh_tool()
    
        current = tool.collect_contract_files()
        committed = _read_manifest()
    
>       assert current == committed, (
            "tests/contract_manifest.txt is stale; run "
            "`just refresh-contract-manifest`.\n"
            f"marker currently selects: {current}\n"
            f"committed manifest:       {committed}"
        )
E       AssertionError: tests/contract_manifest.txt is stale; run `just refresh-contract-manifest`.
E         marker currently selects: ['tests/ace/tui/test_visual_fixture_host_paths.py', 'tests/test_agent_session_terminology.py', 'tests/test_agent_stop_hook_config.py', 'tests/test_agent_tribe_terminology.py', 'tests/test_check_sase_core_rs_bindings_tool.py', 'tests/test_ci_bootstrap_sidecars_tool.py', 'tests/test_commit_type_tag_contract.py', 'tests/test_config_schema.py', 'tests/test_config_schema_ace.py', 'tests/test_config_schema_beads.py', 'tests/test_config_schema_extensions.py', 'tests/test_config_schema_gate_turn.py', 'tests/test_config_schema_keymaps.py', 'tests/test_config_schema_runtime_limits.py', 'tests/test_core_finalizer_facade.py', 'tests/test_demo_media_postprocessor.py', 'tests/test_exercise_release.py', 'tests/test_gemini_active_surface_guard.py', 'tests/test_github_actions_build_core.py', 'tests/test_github_actions_ci_master_gate.py', 'tests/test_github_actions_ci_workflow.py', 'tests/test_github_actions_install_smoke.py', 'tests/test_github_actions_publish.py', 'tests/test_github_actions_release.py', 'tests/test_github_actions_release_steward.py', 'tests/test_github_actions_setup_sase.py', 'tests/test_github_actions_testpypi_drill.py', 'tests/test_justfile_lint_check.py', 'tests/test_justfile_lint_lint.py', 'tests/test_justfile_lint_setup.py', 'tests/test_justfile_sase_core_dir.py', 'tests/test_macro_terminology.py', 'tests/test_patch_stitch_terminology_audit.py', 'tests/test_probe_core_floor_tool.py', 'tests/test_project_display_presentation_audit.py', 'tests/test_prompt_prediction_replay_sources.py', 'tests/test_ratchet_core_revision_tool.py', 'tests/test_ratchet_core_window_source_normalization.py', 'tests/test_ratchet_core_window_tool_core.py', 'tests/test_ratchet_core_window_tool_guardrails.py', 'tests/test_ratchet_core_window_tool_modes.py', 'tests/test_ratchet_core_window_tool_reconciliation.py', 'tests/test_ratchet_core_window_tool_ref.py', 'tests/test_release_candidate_inventory.py', 'tests/test_release_candidate_publish.py', 'tests/test_release_candidate_published_core.py', 'tests/test_release_candidate_qualify_red.py', 'tests/test_release_candidate_rerun.py', 'tests/test_release_candidate_seal.py', 'tests/test_release_core.py', 'tests/test_require_tool_run.py', 'tests/test_ruff_config.py', 'tests/test_run_pytest_command.py', 'tests/test_run_pytest_contention.py', 'tests/test_run_pytest_health.py', 'tests/test_run_pytest_main.py', 'tests/test_run_pytest_scoped.py', 'tests/test_run_pytest_tmpdir.py', 'tests/test_run_pytest_workers.py', 'tests/test_rust_install_cleanup.py', 'tests/test_sase_bead_tool.py', 'tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py', 'tests/test_sase_core_rs_bead_resolution_smoke_tool.py', 'tests/test_sase_core_rs_feature_flag_state_smoke_tool.py', 'tests/test_sase_core_rs_glossary_line_break_smoke_tool.py', 'tests/test_sase_core_rs_plan_header_smoke_tool.py', 'tests/test_sase_core_rs_telemetry_smoke_tool.py', 'tests/test_sase_core_wheel_cache_tool.py', 'tests/test_sase_migrate_statuses.py', 'tests/test_sase_turn_terminology.py', 'tests/test_sdd_canonical_layout.py', 'tests/test_setup_required_plugins_tool.py', 'tests/test_suite_gate.py', 'tests/test_suite_gate_budget.py', 'tests/test_suite_gate_lease.py', 'tests/test_suite_gate_reclaim.py', 'tests/test_timezone_display_guard.py', 'tests/test_tool_adoption_report_tool.py', 'tests/test_validate_changelog_tool.py', 'tests/test_validate_dependency_group_tool.py', 'tests/test_validate_sase_core_rs_contracts_fleet_tool.py', 'tests/test_validate_sase_core_rs_contracts_provider_tool.py', 'tests/test_validate_sase_core_rs_contracts_tool.py', 'tests/test_validate_sase_core_rs_environment_tool.py', 'tests/test_validate_sase_core_rs_prompt_tool.py', 'tests/test_validate_sase_core_rs_runtime_tool.py', 'tests/test_validate_sase_core_rs_tool.py', 'tests/test_validate_sase_core_rs_version_tool.py', 'tests/test_validate_test_environment_tool.py']
E         committed manifest:       ['tests/ace/tui/test_visual_fixture_host_paths.py', 'tests/test_agent_session_terminology.py', 'tests/test_agent_stop_hook_config.py', 'tests/test_agent_tribe_terminology.py', 'tests/test_check_sase_core_rs_bindings_tool.py', 'tests/test_ci_bootstrap_sidecars_tool.py', 'tests/test_commit_type_tag_contract.py', 'tests/test_config_schema.py', 'tests/test_config_schema_ace.py', 'tests/test_config_schema_beads.py', 'tests/test_config_schema_extensions.py', 'tests/test_config_schema_gate_turn.py', 'tests/test_config_schema_keymaps.py', 'tests/test_config_schema_runtime_limits.py', 'tests/test_core_finalizer_facade.py', 'tests/test_demo_media_postprocessor.py', 'tests/test_exercise_release.py', 'tests/test_gemini_active_surface_guard.py', 'tests/test_github_actions_build_core.py', 'tests/test_github_actions_ci_master_gate.py', 'tests/test_github_actions_ci_workflow.py', 'tests/test_github_actions_install_smoke.py', 'tests/test_github_actions_publish.py', 'tests/test_github_actions_release.py', 'tests/test_github_actions_release_steward.py', 'tests/test_github_actions_setup_sase.py', 'tests/test_github_actions_testpypi_drill.py', 'tests/test_justfile_lint_check.py', 'tests/test_justfile_lint_lint.py', 'tests/test_justfile_lint_setup.py', 'tests/test_justfile_sase_core_dir.py', 'tests/test_macro_terminology.py', 'tests/test_patch_stitch_terminology_audit.py', 'tests/test_probe_core_floor_tool.py', 'tests/test_project_display_presentation_audit.py', 'tests/test_prompt_prediction_replay_sources.py', 'tests/test_ratchet_core_revision_tool.py', 'tests/test_ratchet_core_window_source_normalization.py', 'tests/test_ratchet_core_window_tool_core.py', 'tests/test_ratchet_core_window_tool_guardrails.py', 'tests/test_ratchet_core_window_tool_modes.py', 'tests/test_ratchet_core_window_tool_reconciliation.py', 'tests/test_release_candidate_inventory.py', 'tests/test_release_candidate_publish.py', 'tests/test_release_candidate_published_core.py', 'tests/test_release_candidate_qualify_red.py', 'tests/test_release_candidate_rerun.py', 'tests/test_release_candidate_seal.py', 'tests/test_release_core.py', 'tests/test_require_tool_run.py', 'tests/test_ruff_config.py', 'tests/test_run_pytest_command.py', 'tests/test_run_pytest_contention.py', 'tests/test_run_pytest_health.py', 'tests/test_run_pytest_main.py', 'tests/test_run_pytest_scoped.py', 'tests/test_run_pytest_tmpdir.py', 'tests/test_run_pytest_workers.py', 'tests/test_rust_install_cleanup.py', 'tests/test_sase_bead_tool.py', 'tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py', 'tests/test_sase_core_rs_bead_resolution_smoke_tool.py', 'tests/test_sase_core_rs_feature_flag_state_smoke_tool.py', 'tests/test_sase_core_rs_glossary_line_break_smoke_tool.py', 'tests/test_sase_core_rs_plan_header_smoke_tool.py', 'tests/test_sase_core_rs_telemetry_smoke_tool.py', 'tests/test_sase_core_wheel_cache_tool.py', 'tests/test_sase_migrate_statuses.py', 'tests/test_sase_turn_terminology.py', 'tests/test_sdd_canonical_layout.py', 'tests/test_setup_required_plugins_tool.py', 'tests/test_suite_gate.py', 'tests/test_suite_gate_budget.py', 'tests/test_suite_gate_lease.py', 'tests/test_suite_gate_reclaim.py', 'tests/test_timezone_display_guard.py', 'tests/test_tool_adoption_report_tool.py', 'tests/test_validate_changelog_tool.py', 'tests/test_validate_dependency_group_tool.py', 'tests/test_validate_sase_core_rs_contracts_fleet_tool.py', 'tests/test_validate_sase_core_rs_contracts_provider_tool.py', 'tests/test_validate_sase_core_rs_contracts_tool.py', 'tests/test_validate_sase_core_rs_environment_tool.py', 'tests/test_validate_sase_core_rs_prompt_tool.py', 'tests/test_validate_sase_core_rs_runtime_tool.py', 'tests/test_validate_sase_core_rs_tool.py', 'tests/test_validate_sase_core_rs_version_tool.py', 'tests/test_validate_test_environment_tool.py']
E       assert ['tests/ace/t...tool.py', ...] == ['tests/ace/t...tool.py', ...]
E         
E         At index 42 diff: 'tests/test_ratchet_core_window_tool_ref.py' != 'tests/test_release_candidate_inventory.py'
E         Left contains one more item: 'tests/test_validate_test_environment_tool.py'
E         
E         Full diff:
E           [
E               'tests/ace/tui/test_visual_fixture_host_paths.py',
E               'tests/test_agent_session_terminology.py',
E               'tests/test_agent_stop_hook_config.py',
E               'tests/test_agent_tribe_terminology.py',
E               'tests/test_check_sase_core_rs_bindings_tool.py',
E               'tests/test_ci_bootstrap_sidecars_tool.py',
E               'tests/test_commit_type_tag_contract.py',
E               'tests/test_config_schema.py',
E               'tests/test_config_schema_ace.py',
E               'tests/test_config_schema_beads.py',
E               'tests/test_config_schema_extensions.py',
E               'tests/test_config_schema_gate_turn.py',
E               'tests/test_config_schema_keymaps.py',
E               'tests/test_config_schema_runtime_limits.py',
E               'tests/test_core_finalizer_facade.py',
E               'tests/test_demo_media_postprocessor.py',
E               'tests/test_exercise_release.py',
E               'tests/test_gemini_active_surface_guard.py',
E               'tests/test_github_actions_build_core.py',
E               'tests/test_github_actions_ci_master_gate.py',
E               'tests/test_github_actions_ci_workflow.py',
E               'tests/test_github_actions_install_smoke.py',
E               'tests/test_github_actions_publish.py',
E               'tests/test_github_actions_release.py',
E               'tests/test_github_actions_release_steward.py',
E               'tests/test_github_actions_setup_sase.py',
E               'tests/test_github_actions_testpypi_drill.py',
E               'tests/test_justfile_lint_check.py',
E               'tests/test_justfile_lint_lint.py',
E               'tests/test_justfile_lint_setup.py',
E               'tests/test_justfile_sase_core_dir.py',
E               'tests/test_macro_terminology.py',
E               'tests/test_patch_stitch_terminology_audit.py',
E               'tests/test_probe_core_floor_tool.py',
E               'tests/test_project_display_presentation_audit.py',
E               'tests/test_prompt_prediction_replay_sources.py',
E               'tests/test_ratchet_core_revision_tool.py',
E               'tests/test_ratchet_core_window_source_normalization.py',
E               'tests/test_ratchet_core_window_tool_core.py',
E               'tests/test_ratchet_core_window_tool_guardrails.py',
E               'tests/test_ratchet_core_window_tool_modes.py',
E               'tests/test_ratchet_core_window_tool_reconciliation.py',
E         +     'tests/test_ratchet_core_window_tool_ref.py',
E               'tests/test_release_candidate_inventory.py',
E               'tests/test_release_candidate_publish.py',
E               'tests/test_release_candidate_published_core.py',
E               'tests/test_release_candidate_qualify_red.py',
E               'tests/test_release_candidate_rerun.py',
E               'tests/test_release_candidate_seal.py',
E               'tests/test_release_core.py',
E               'tests/test_require_tool_run.py',
E               'tests/test_ruff_config.py',
E               'tests/test_run_pytest_command.py',
E               'tests/test_run_pytest_contention.py',
E               'tests/test_run_pytest_health.py',
E               'tests/test_run_pytest_main.py',
E               'tests/test_run_pytest_scoped.py',
E               'tests/test_run_pytest_tmpdir.py',
E               'tests/test_run_pytest_workers.py',
E               'tests/test_rust_install_cleanup.py',
E               'tests/test_sase_bead_tool.py',
E               'tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py',
E               'tests/test_sase_core_rs_bead_resolution_smoke_tool.py',
E               'tests/test_sase_core_rs_feature_flag_state_smoke_tool.py',
E               'tests/test_sase_core_rs_glossary_line_break_smoke_tool.py',
E               'tests/test_sase_core_rs_plan_header_smoke_tool.py',
E               'tests/test_sase_core_rs_telemetry_smoke_tool.py',
E               'tests/test_sase_core_wheel_cache_tool.py',
E               'tests/test_sase_migrate_statuses.py',
E               'tests/test_sase_turn_terminology.py',
E               'tests/test_sdd_canonical_layout.py',
E               'tests/test_setup_required_plugins_tool.py',
E               'tests/test_suite_gate.py',
E               'tests/test_suite_gate_budget.py',
E               'tests/test_suite_gate_lease.py',
E               'tests/test_suite_gate_reclaim.py',
E               'tests/test_timezone_display_guard.py',
E               'tests/test_tool_adoption_report_tool.py',
E               'tests/test_validate_changelog_tool.py',
E               'tests/test_validate_dependency_group_tool.py',
E               'tests/test_validate_sase_core_rs_contracts_fleet_tool.py',
E               'tests/test_validate_sase_core_rs_contracts_provider_tool.py',
E               'tests/test_validate_sase_core_rs_contracts_tool.py',
E               'tests/test_validate_sase_core_rs_environment_tool.py',
E               'tests/test_validate_sase_core_rs_prompt_tool.py',
E               'tests/test_validate_sase_core_rs_runtime_tool.py',
E               'tests/test_validate_sase_core_rs_tool.py',
E               'tests/test_validate_sase_core_rs_version_tool.py',
E               'tests/test_validate_test_environment_tool.py',
E           ]

tests/test_contract_manifest.py:441: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/macro/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/ace/tui/test_agent_archive_controller_lookup.py::test_coalesced_idle_does_not_publish_false_missing_for_queued_open
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/functools.py:76: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return partial(update_wrapper, wrapped=wrapped,
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:1725: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return ((p, type(p)) for p in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=597455) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=597406) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:234: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    y = func(*args)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=597392) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
61.86s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
55.92s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
52.93s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
40.12s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
29.87s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
28.74s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
27.36s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
20.33s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
19.97s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
18.85s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
16.99s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
15.36s call     tests/test_sdd_commit.py::test_commit_sdd_files_removes_persistent_index_lock_after_retry_exhausted
15.35s call     tests/test_bare_git_init.py::TestInitBareGitProject::test_git_runner_removes_persistent_index_lock_after_retries
15.16s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
14.54s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
13.82s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
13.60s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
13.09s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
12.73s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
12.68s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
=========================== short test summary info ============================
FAILED tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed - AssertionError: assert {'src/sase/_l...migrate', ...} == {'src/sase/_l...migrate', ...}
  
  Extra items in the left set:
  'src/sase/workflows/commit/rebase_gate_runner.py:_cleanup_workdir'
  
  Full diff:
    {
        'src/sase/_linked_repo_workspaces.py:_remove_path',
        'src/sase/_linked_repo_workspaces.py:clear_workspace_repos',
        'src/sase/_linked_repo_workspaces.py:move_aside_for_background_delete',
        'src/sase/ace/tui/bgcmd.py:dismiss_background_command',
        'src/sase/agent/names/_wipe_execute.py:_remove_artifact_dirs',
        'src/sase/agents/cli_artifacts_layout.py:_handle_migrate',
        'src/sase/agents/cli_artifacts_layout.py:_handle_rollback',
        'src/sase/agents_sync/_git_sync_ops_git.py:ensure_agents_clone',
        'src/sase/agents_sync/purge_local_state.py:_apply_closure',
        'src/sase/agents_sync/v2_io.py:_cleanup_transaction_dirs',
        'src/sase/axe/run_agent_exec_attempts.py:_move_into_tmp',
        'src/sase/axe/run_agent_exec_attempts.py:snapshot_attempt',
        'src/sase/bead/attachments/lifecycle.py:quarantine_local_object',
        'src/sase/bead/attachments/store.py:remove',
        'src/sase/dev_update/prebuild_producer.py:_prune_completed_sets',
        'src/sase/dev_update/prebuild_producer.py:produce_prebuild',
        'src/sase/llm_provider/_codex_home.py:_try_delete_shadow_home',
        'src/sase/llm_provider/_plan_utils.py:move_plan_to_sase',
        'src/sase/main/project_handler_lifecycle.py:delete_project_locked',
        'src/sase/main/repo_open_external.py:_remove_clone_staging_path',
        'src/sase/main/workspace_handler_maintenance.py:remove_checkout',
        'src/sase/main/workspace_handler_migration.py:handle_migrate',
        'src/sase/migration_kit/atomic.py:_remove_path',
        'src/sase/migration_kit/atomic.py:remove_path',
        'src/sase/migration_kit/restore.py:_swap_into_place',
        'src/sase/mode_switch/execute.py:_cleanup_failed_clone',
        'src/sase/notification_gates/command_runner.py:_remove_untrusted_terminal',
        'src/sase/notification_gates/service_creation.py:_start_gate_creation',
        'src/sase/notification_gates/service_creation.py:create_gate',
        'src/sase/procs/_migration.py:_perform_migration',
        'src/sase/procs/_migration.py:_relocate_legacy_logs',
        'src/sase/sdd/_bead_adoption.py:_copy_bead_state',
        'src/sase/sdd/_bead_adoption.py:cleanup_plans_bead_state',
        'src/sase/sdd/_store_adoption.py:cleanup_staging',
        'src/sase/sdd/_store_clone_common.py:remove_partial_sdd_clone',
        'src/sase/sdd/_store_clone_transaction.py:_remove_clone_stage_path',
        'src/sase/sdd/_store_link.py:_replace_workspace_sdd_clone',
        'src/sase/sudo/execution_handoff.py:cleanup_handoff',
  +     'src/sase/workflows/commit/rebase_gate_runner.py:_cleanup_workdir',
        'src/sase/workspace_provider/_rescue_git.py:_rescue_git_repo_body',
        'src/sase/workspace_provider/_rescue_store.py:_quarantine_directory',
        'src/sase/workspace_provider/_rescue_store.py:_reap_rescue_entries',
        'src/sase/workspace_provider/_snapshot_capture_payload.py:_cleanup_capture_temps',
        'src/sase/workspace_provider/_snapshot_capture_payload_objects.py:verify_pack',
        'src/sase/workspace_provider/_snapshot_capture_source.py:_discard_incomplete',
        'src/sase/workspace_provider/_snapshot_restore.py:_clear_worktree',
        'src/sase/workspace_provider/_snapshot_restore.py:_restore_operation_markers',
        'src/sase/workspace_provider/_utils_checkout.py:_remove_corrupt_checkout',
        'src/sase/workspace_provider/_utils_git.py:abort_in_progress_git_operations',
        'src/sase/workspace_provider/reset_replay.py:_clear_owned_paths',
    }
FAILED tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker - AssertionError: assert 6 == 1
 +  where 6 = len([<Popen: returncode: None args: ['sleep', '30']>, <Popen: returncode: None args: ['sleep', '30']>, <Popen: returncode:...gs: ['sleep', '30']>, <Popen: returncode: None args: ['sleep', '30']>, <Popen: returncode: None args: ['sleep', '30']>])
FAILED tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_scrubs_agent_identity_from_the_supervisor_env - AssertionError: assert 'SASE_AGENT' not in {'PYENV_VIRTUALENV_INIT': '1', 'LIBRARY_PATH': '', 'MAVEN_OPTS': '-Dstyle.color=always', 'DBB': '/home/bryan/Sync/bin', ...}
FAILED tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection - AssertionError: tests/contract_manifest.txt is stale; run `just refresh-contract-manifest`.
  marker currently selects: ['tests/ace/tui/test_visual_fixture_host_paths.py', 'tests/test_agent_session_terminology.py', 'tests/test_agent_stop_hook_config.py', 'tests/test_agent_tribe_terminology.py', 'tests/test_check_sase_core_rs_bindings_tool.py', 'tests/test_ci_bootstrap_sidecars_tool.py', 'tests/test_commit_type_tag_contract.py', 'tests/test_config_schema.py', 'tests/test_config_schema_ace.py', 'tests/test_config_schema_beads.py', 'tests/test_config_schema_extensions.py', 'tests/test_config_schema_gate_turn.py', 'tests/test_config_schema_keymaps.py', 'tests/test_config_schema_runtime_limits.py', 'tests/test_core_finalizer_facade.py', 'tests/test_demo_media_postprocessor.py', 'tests/test_exercise_release.py', 'tests/test_gemini_active_surface_guard.py', 'tests/test_github_actions_build_core.py', 'tests/test_github_actions_ci_master_gate.py', 'tests/test_github_actions_ci_workflow.py', 'tests/test_github_actions_install_smoke.py', 'tests/test_github_actions_publish.py', 'tests/test_github_actions_release.py', 'tests/test_github_actions_release_steward.py', 'tests/test_github_actions_setup_sase.py', 'tests/test_github_actions_testpypi_drill.py', 'tests/test_justfile_lint_check.py', 'tests/test_justfile_lint_lint.py', 'tests/test_justfile_lint_setup.py', 'tests/test_justfile_sase_core_dir.py', 'tests/test_macro_terminology.py', 'tests/test_patch_stitch_terminology_audit.py', 'tests/test_probe_core_floor_tool.py', 'tests/test_project_display_presentation_audit.py', 'tests/test_prompt_prediction_replay_sources.py', 'tests/test_ratchet_core_revision_tool.py', 'tests/test_ratchet_core_window_source_normalization.py', 'tests/test_ratchet_core_window_tool_core.py', 'tests/test_ratchet_core_window_tool_guardrails.py', 'tests/test_ratchet_core_window_tool_modes.py', 'tests/test_ratchet_core_window_tool_reconciliation.py', 'tests/test_ratchet_core_window_tool_ref.py', 'tests/test_release_candidate_inventory.py', 'tests/test_release_candidate_publish.py', 'tests/test_release_candidate_published_core.py', 'tests/test_release_candidate_qualify_red.py', 'tests/test_release_candidate_rerun.py', 'tests/test_release_candidate_seal.py', 'tests/test_release_core.py', 'tests/test_require_tool_run.py', 'tests/test_ruff_config.py', 'tests/test_run_pytest_command.py', 'tests/test_run_pytest_contention.py', 'tests/test_run_pytest_health.py', 'tests/test_run_pytest_main.py', 'tests/test_run_pytest_scoped.py', 'tests/test_run_pytest_tmpdir.py', 'tests/test_run_pytest_workers.py', 'tests/test_rust_install_cleanup.py', 'tests/test_sase_bead_tool.py', 'tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py', 'tests/test_sase_core_rs_bead_resolution_smoke_tool.py', 'tests/test_sase_core_rs_feature_flag_state_smoke_tool.py', 'tests/test_sase_core_rs_glossary_line_break_smoke_tool.py', 'tests/test_sase_core_rs_plan_header_smoke_tool.py', 'tests/test_sase_core_rs_telemetry_smoke_tool.py', 'tests/test_sase_core_wheel_cache_tool.py', 'tests/test_sase_migrate_statuses.py', 'tests/test_sase_turn_terminology.py', 'tests/test_sdd_canonical_layout.py', 'tests/test_setup_required_plugins_tool.py', 'tests/test_suite_gate.py', 'tests/test_suite_gate_budget.py', 'tests/test_suite_gate_lease.py', 'tests/test_suite_gate_reclaim.py', 'tests/test_timezone_display_guard.py', 'tests/test_tool_adoption_report_tool.py', 'tests/test_validate_changelog_tool.py', 'tests/test_validate_dependency_group_tool.py', 'tests/test_validate_sase_core_rs_contracts_fleet_tool.py', 'tests/test_validate_sase_core_rs_contracts_provider_tool.py', 'tests/test_validate_sase_core_rs_contracts_tool.py', 'tests/test_validate_sase_core_rs_environment_tool.py', 'tests/test_validate_sase_core_rs_prompt_tool.py', 'tests/test_validate_sase_core_rs_runtime_tool.py', 'tests/test_validate_sase_core_rs_tool.py', 'tests/test_validate_sase_core_rs_version_tool.py', 'tests/test_validate_test_environment_tool.py']
  committed manifest:       ['tests/ace/tui/test_visual_fixture_host_paths.py', 'tests/test_agent_session_terminology.py', 'tests/test_agent_stop_hook_config.py', 'tests/test_agent_tribe_terminology.py', 'tests/test_check_sase_core_rs_bindings_tool.py', 'tests/test_ci_bootstrap_sidecars_tool.py', 'tests/test_commit_type_tag_contract.py', 'tests/test_config_schema.py', 'tests/test_config_schema_ace.py', 'tests/test_config_schema_beads.py', 'tests/test_config_schema_extensions.py', 'tests/test_config_schema_gate_turn.py', 'tests/test_config_schema_keymaps.py', 'tests/test_config_schema_runtime_limits.py', 'tests/test_core_finalizer_facade.py', 'tests/test_demo_media_postprocessor.py', 'tests/test_exercise_release.py', 'tests/test_gemini_active_surface_guard.py', 'tests/test_github_actions_build_core.py', 'tests/test_github_actions_ci_master_gate.py', 'tests/test_github_actions_ci_workflow.py', 'tests/test_github_actions_install_smoke.py', 'tests/test_github_actions_publish.py', 'tests/test_github_actions_release.py', 'tests/test_github_actions_release_steward.py', 'tests/test_github_actions_setup_sase.py', 'tests/test_github_actions_testpypi_drill.py', 'tests/test_justfile_lint_check.py', 'tests/test_justfile_lint_lint.py', 'tests/test_justfile_lint_setup.py', 'tests/test_justfile_sase_core_dir.py', 'tests/test_macro_terminology.py', 'tests/test_patch_stitch_terminology_audit.py', 'tests/test_probe_core_floor_tool.py', 'tests/test_project_display_presentation_audit.py', 'tests/test_prompt_prediction_replay_sources.py', 'tests/test_ratchet_core_revision_tool.py', 'tests/test_ratchet_core_window_source_normalization.py', 'tests/test_ratchet_core_window_tool_core.py', 'tests/test_ratchet_core_window_tool_guardrails.py', 'tests/test_ratchet_core_window_tool_modes.py', 'tests/test_ratchet_core_window_tool_reconciliation.py', 'tests/test_release_candidate_inventory.py', 'tests/test_release_candidate_publish.py', 'tests/test_release_candidate_published_core.py', 'tests/test_release_candidate_qualify_red.py', 'tests/test_release_candidate_rerun.py', 'tests/test_release_candidate_seal.py', 'tests/test_release_core.py', 'tests/test_require_tool_run.py', 'tests/test_ruff_config.py', 'tests/test_run_pytest_command.py', 'tests/test_run_pytest_contention.py', 'tests/test_run_pytest_health.py', 'tests/test_run_pytest_main.py', 'tests/test_run_pytest_scoped.py', 'tests/test_run_pytest_tmpdir.py', 'tests/test_run_pytest_workers.py', 'tests/test_rust_install_cleanup.py', 'tests/test_sase_bead_tool.py', 'tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py', 'tests/test_sase_core_rs_bead_resolution_smoke_tool.py', 'tests/test_sase_core_rs_feature_flag_state_smoke_tool.py', 'tests/test_sase_core_rs_glossary_line_break_smoke_tool.py', 'tests/test_sase_core_rs_plan_header_smoke_tool.py', 'tests/test_sase_core_rs_telemetry_smoke_tool.py', 'tests/test_sase_core_wheel_cache_tool.py', 'tests/test_sase_migrate_statuses.py', 'tests/test_sase_turn_terminology.py', 'tests/test_sdd_canonical_layout.py', 'tests/test_setup_required_plugins_tool.py', 'tests/test_suite_gate.py', 'tests/test_suite_gate_budget.py', 'tests/test_suite_gate_lease.py', 'tests/test_suite_gate_reclaim.py', 'tests/test_timezone_display_guard.py', 'tests/test_tool_adoption_report_tool.py', 'tests/test_validate_changelog_tool.py', 'tests/test_validate_dependency_group_tool.py', 'tests/test_validate_sase_core_rs_contracts_fleet_tool.py', 'tests/test_validate_sase_core_rs_contracts_provider_tool.py', 'tests/test_validate_sase_core_rs_contracts_tool.py', 'tests/test_validate_sase_core_rs_environment_tool.py', 'tests/test_validate_sase_core_rs_prompt_tool.py', 'tests/test_validate_sase_core_rs_runtime_tool.py', 'tests/test_validate_sase_core_rs_tool.py', 'tests/test_validate_sase_core_rs_version_tool.py', 'tests/test_validate_test_environment_tool.py']
assert ['tests/ace/t...tool.py', ...] == ['tests/ace/t...tool.py', ...]
  
  At index 42 diff: 'tests/test_ratchet_core_window_tool_ref.py' != 'tests/test_release_candidate_inventory.py'
  Left contains one more item: 'tests/test_validate_test_environment_tool.py'
  
  Full diff:
    [
        'tests/ace/tui/test_visual_fixture_host_paths.py',
        'tests/test_agent_session_terminology.py',
        'tests/test_agent_stop_hook_config.py',
        'tests/test_agent_tribe_terminology.py',
        'tests/test_check_sase_core_rs_bindings_tool.py',
        'tests/test_ci_bootstrap_sidecars_tool.py',
        'tests/test_commit_type_tag_contract.py',
        'tests/test_config_schema.py',
        'tests/test_config_schema_ace.py',
        'tests/test_config_schema_beads.py',
        'tests/test_config_schema_extensions.py',
        'tests/test_config_schema_gate_turn.py',
        'tests/test_config_schema_keymaps.py',
        'tests/test_config_schema_runtime_limits.py',
        'tests/test_core_finalizer_facade.py',
        'tests/test_demo_media_postprocessor.py',
        'tests/test_exercise_release.py',
        'tests/test_gemini_active_surface_guard.py',
        'tests/test_github_actions_build_core.py',
        'tests/test_github_actions_ci_master_gate.py',
        'tests/test_github_actions_ci_workflow.py',
        'tests/test_github_actions_install_smoke.py',
        'tests/test_github_actions_publish.py',
        'tests/test_github_actions_release.py',
        'tests/test_github_actions_release_steward.py',
        'tests/test_github_actions_setup_sase.py',
        'tests/test_github_actions_testpypi_drill.py',
        'tests/test_justfile_lint_check.py',
        'tests/test_justfile_lint_lint.py',
        'tests/test_justfile_lint_setup.py',
        'tests/test_justfile_sase_core_dir.py',
        'tests/test_macro_terminology.py',
        'tests/test_patch_stitch_terminology_audit.py',
        'tests/test_probe_core_floor_tool.py',
        'tests/test_project_display_presentation_audit.py',
        'tests/test_prompt_prediction_replay_sources.py',
        'tests/test_ratchet_core_revision_tool.py',
        'tests/test_ratchet_core_window_source_normalization.py',
        'tests/test_ratchet_core_window_tool_core.py',
        'tests/test_ratchet_core_window_tool_guardrails.py',
        'tests/test_ratchet_core_window_tool_modes.py',
        'tests/test_ratchet_core_window_tool_reconciliation.py',
  +     'tests/test_ratchet_core_window_tool_ref.py',
        'tests/test_release_candidate_inventory.py',
        'tests/test_release_candidate_publish.py',
        'tests/test_release_candidate_published_core.py',
        'tests/test_release_candidate_qualify_red.py',
        'tests/test_release_candidate_rerun.py',
        'tests/test_release_candidate_seal.py',
        'tests/test_release_core.py',
        'tests/test_require_tool_run.py',
        'tests/test_ruff_config.py',
        'tests/test_run_pytest_command.py',
        'tests/test_run_pytest_contention.py',
        'tests/test_run_pytest_health.py',
        'tests/test_run_pytest_main.py',
        'tests/test_run_pytest_scoped.py',
        'tests/test_run_pytest_tmpdir.py',
        'tests/test_run_pytest_workers.py',
        'tests/test_rust_install_cleanup.py',
        'tests/test_sase_bead_tool.py',
        'tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py',
        'tests/test_sase_core_rs_bead_resolution_smoke_tool.py',
        'tests/test_sase_core_rs_feature_flag_state_smoke_tool.py',
        'tests/test_sase_core_rs_glossary_line_break_smoke_tool.py',
        'tests/test_sase_core_rs_plan_header_smoke_tool.py',
        'tests/test_sase_core_rs_telemetry_smoke_tool.py',
        'tests/test_sase_core_wheel_cache_tool.py',
        'tests/test_sase_migrate_statuses.py',
        'tests/test_sase_turn_terminology.py',
        'tests/test_sdd_canonical_layout.py',
        'tests/test_setup_required_plugins_tool.py',
        'tests/test_suite_gate.py',
        'tests/test_suite_gate_budget.py',
        'tests/test_suite_gate_lease.py',
        'tests/test_suite_gate_reclaim.py',
        'tests/test_timezone_display_guard.py',
        'tests/test_tool_adoption_report_tool.py',
        'tests/test_validate_changelog_tool.py',
        'tests/test_validate_dependency_group_tool.py',
        'tests/test_validate_sase_core_rs_contracts_fleet_tool.py',
        'tests/test_validate_sase_core_rs_contracts_provider_tool.py',
        'tests/test_validate_sase_core_rs_contracts_tool.py',
        'tests/test_validate_sase_core_rs_environment_tool.py',
        'tests/test_validate_sase_core_rs_prompt_tool.py',
        'tests/test_validate_sase_core_rs_runtime_tool.py',
        'tests/test_validate_sase_core_rs_tool.py',
        'tests/test_validate_sase_core_rs_version_tool.py',
        'tests/test_validate_test_environment_tool.py',
    ]
==== 4 failed, 58713 passed, 18 skipped, 154 warnings in 792.53s (0:13:12) =====
error: recipe `test-scoped` failed on line 633 with exit code 1
error: recipe `check` failed on line 899 with exit code 1
failed  exit=1  duration=1185893ms
unattrib  26.1s
triage test (scoped): 1 FLAKY 2 KNOWN 1 NEW stopped
NEW test (scoped): FAILED tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_scrubs_agent_identity_from_the_supervisor_env - AssertionError: assert 'SASE_AGENT' not in {'PYENV_VIRTUALENV_INIT': '1', 'LIBRARY_PATH': '', 'MAVEN_OPTS': '-Dstyle.color=always', 'DBB': '/home/bryan/Sync/bin', ...} — recorded evidence; no owner
KNOWN test (scoped): FAILED tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker - AssertionError: assert 6 == 1 — witness 08a3ec703c011e1cfebd914eddaa5095; no owner
KNOWN test (scoped): FAILED tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed - AssertionError: assert {'src/sase/_l...migrate', ...} == {'src/sase/_l...migrate', ...} — witness 08a3ec703c011e1cfebd914eddaa5095; no owner
FLAKY test (scoped): FAILED tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection - AssertionError: tests/contract_manifest.txt is stale; run `just refresh-contract-manifest`. — recorded evidence; no owner
verdict: new_failures — 1 NEW, 2 KNOWN, 1 FLAKY; exit 1

