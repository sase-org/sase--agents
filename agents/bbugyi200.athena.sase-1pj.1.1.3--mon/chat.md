# Chat History - ace-run (sase-1pj.1.1.3--mon)

- **TIMESTAMP:** 2026-10-29 01:20:27 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1pj.1.1.3--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'finish check (joined run)'

## Response

sase tool run 4637bbba3802ceb5cd504a581dae5aa1
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.42.7 is missing 39 capability(s), and at least one has no containing sase-core release tag yet.
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
[core-floor-probe] publication_protection_ledger_empty: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_ledger_validate: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_lookup: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_rejection: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_scan: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_resolve_verified_clean: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_retry_allowed: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_upsert: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_scan_disposition: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] staged_handoff_receipt_authorizes: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); no release tag contains it yet.
[core-floor-probe] staged_handoff_wire_schema_version: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); no release tag contains it yet.
[core-floor-probe] validate_staged_handoff: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); no release tag contains it yet.
[core-floor-probe] validate_staged_handoff_receipt: first appears in sase-core cd62c83 (feat(staged_handoff): add staged-handoff wire contract and admission guards); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "416db28", "name": "agent_publication_protection_wire_schema_version", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "31deb0d", "name": "agent_stats_query_macro_usage", "release": null, "subject": "feat(stats): add query_macro_usage and accept config via"}, {"commit": "6613c9b", "name": "artifact_link_collision_partition", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_collision_wire_schema_version", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_canonical_json", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_path", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_validate", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_wire_schema_version", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "800caef", "name": "assess_repository_landing_proof", "release": "v0.43.0", "subject": "fix(beads): recover every eligible failed-run close in one mutation"}, {"commit": "4f17b72", "name": "bead_recover_failed_closes", "release": "v0.43.0", "subject": "feat(beads): recover failed-run closes atomically"}, {"commit": "416db28", "name": "classify_sidecar_publication_push_result", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "cd62c83", "name": "evaluate_stage_admission", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "83b010d", "name": "footprint_card", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_catalog_status", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_clear", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_decide", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "65546fd", "name": "footprint_export", "release": null, "subject": "feat(footprint): add identity-free weekly export and replace-all import"}, {"commit": "2d0b62e", "name": "footprint_fold", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "65546fd", "name": "footprint_import", "release": null, "subject": "feat(footprint): add identity-free weekly export and replace-all import"}, {"commit": "2d0b62e", "name": "footprint_ingest_catalog", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_prune", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_report", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_status", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_upsert_derived", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_validate_overlay", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_wire_schema_version", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "416db28", "name": "publication_protection_ledger_empty", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_ledger_validate", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_lookup", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_rejection", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_scan", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_resolve_verified_clean", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_retry_allowed", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_upsert", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_scan_disposition", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "cd62c83", "name": "staged_handoff_receipt_authorizes", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "cd62c83", "name": "staged_handoff_wire_schema_version", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "cd62c83", "name": "validate_staged_handoff", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}, {"commit": "cd62c83", "name": "validate_staged_handoff_receipt", "release": null, "subject": "feat(staged_handoff): add staged-handoff wire contract and admission guards"}], "declared_floor": "0.42.7", "exit_code": 4, "message": "sase-core-rs==0.42.7 is missing 39 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 5459 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 4795 commits behind HEAD) matched 5 changed file(s) and contributed 21 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
plugins: cov-7.1.0, mock-3.16.0, inline-snapshot-0.36.0, asyncio-1.4.0, hypothesis-6.168.5, xdist-3.8.0, platformdirs-4.13.5
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [9187 items]

........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
..................................................F......F..FFF...FFF... [ 12%]
.F...................................................................... [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 16%]
...s.................................................................... [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 49%]
..................................................................F..... [ 50%]
........................................................................ [ 50%]
.....................................F.................................. [ 51%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 70%]
............................................................F.F..FFF.F.. [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 99%]
...........................................                              [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______________ test_stranded_bead_waiters_share_one_notification _______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw1/test_stranded_bead_waiters_sha0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5dea18edd0>

    def test_stranded_bead_waiters_share_one_notification(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        point_wait_bead_status(monkeypatch)
        now = time.time()
        artifact = tmp_path / "stranded-turn"
        artifact.mkdir()
        issues = [
            phase(STRANDED_BEAD_ID, assignee=STRANDED_BEAD_ID, parent_id=STRANDED_PARENT_ID)
        ]
        records = [
            record(
                artifact,
                name=STRANDED_BEAD_ID,
                session=STRANDED_BEAD_ID,
                done=DoneMarkerWire(outcome="completed", finished_at=now - 3600),
            )
        ]
        wire_targeted_collector(monkeypatch, tmp_path, issues, records)
        first_waiter = make_waiters(tmp_path, "phase-two")[0]
    
        run_wait_checks(tmp_path, monkeypatch)
    
        assert not (first_waiter / "ready.json").exists()
        notifications = load_notifications()
>       assert len(notifications) == 1
E       assert 0 == 1
E        +  where 0 = len([])

tests/test_axe_chop_wait_checks_stranded_beads_notify.py:75: AssertionError
----------------------------- Captured stdout call -----------------------------
[wait_checks] waiter walk progress: projects=1 artifacts=1 waiting=1 live=0 dead=0 unknown_liveness=1 elapsed_ms=0
[wait_checks] resolving view progress: rows=0 scoped_waiters=1 full_view_waiters=0 elapsed_ms=0
[wait_checks] Stranded-bead collection failed for proj; leaving notifications unchanged: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
wait_checks: projects=1 artifacts=1 waiting=1 live_waiting=0 dead_waiting=0 unknown_liveness=1 ready_written=0 already_ready=0 invalid=0 unresolved=1 unknown_outcome=0 deferred_unconfirmed=0 waiter_errors=0 walk_ms=0 view_ms=0 resolve_ms=1 view_rows=0 scoped_waiters=1 full_view_waiters=0 reason=dependencies_not_ready
____________ test_stranded_bead_notification_dismisses_after_close _____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw1/test_stranded_bead_notificatio0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5dea18f070>

    def test_stranded_bead_notification_dismisses_after_close(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        closed_ids: set[str] = set()
        point_wait_bead_status(monkeypatch, closed_ids)
        now = time.time()
        artifact = tmp_path / "stranded-turn"
        artifact.mkdir()
        issues = [
            phase(STRANDED_BEAD_ID, assignee=STRANDED_BEAD_ID, parent_id=STRANDED_PARENT_ID)
        ]
        records = [
            record(
                artifact,
                name=STRANDED_BEAD_ID,
                session=STRANDED_BEAD_ID,
                done=DoneMarkerWire(outcome="completed", finished_at=now - 3600),
            )
        ]
        wire_targeted_collector(monkeypatch, tmp_path, issues, records)
        waiter = make_waiters(tmp_path, "waiter")[0]
    
        run_wait_checks(tmp_path, monkeypatch)
>       assert len(load_notifications()) == 1
E       assert 0 == 1
E        +  where 0 = len([])
E        +    where [] = load_notifications()

tests/test_axe_chop_wait_checks_stranded_beads_notify.py:265: AssertionError
----------------------------- Captured stdout call -----------------------------
[wait_checks] waiter walk progress: projects=1 artifacts=1 waiting=1 live=0 dead=0 unknown_liveness=1 elapsed_ms=0
[wait_checks] resolving view progress: rows=0 scoped_waiters=1 full_view_waiters=0 elapsed_ms=0
[wait_checks] Stranded-bead collection failed for proj; leaving notifications unchanged: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
wait_checks: projects=1 artifacts=1 waiting=1 live_waiting=0 dead_waiting=0 unknown_liveness=1 ready_written=0 already_ready=0 invalid=0 unresolved=1 unknown_outcome=0 deferred_unconfirmed=0 waiter_errors=0 walk_ms=0 view_ms=0 resolve_ms=0 view_rows=0 scoped_waiters=1 full_view_waiters=0 reason=dependencies_not_ready
__________ test_stranded_alert_dismisses_when_waiter_is_already_ready __________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw1/test_stranded_alert_dismisses_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5dea18d7f0>

    def test_stranded_alert_dismisses_when_waiter_is_already_ready(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        closed_ids: set[str] = set()
        point_wait_bead_status(monkeypatch, closed_ids)
        now = time.time()
        artifact = tmp_path / "stranded-turn"
        artifact.mkdir()
        issues = [
            phase(STRANDED_BEAD_ID, assignee=STRANDED_BEAD_ID, parent_id=STRANDED_PARENT_ID)
        ]
        records = [
            record(
                artifact,
                name=STRANDED_BEAD_ID,
                session=STRANDED_BEAD_ID,
                done=DoneMarkerWire(outcome="completed", finished_at=now - 3600),
            )
        ]
        wire_targeted_collector(monkeypatch, tmp_path, issues, records)
        waiter = make_waiters(tmp_path, "waiter")[0]
    
        run_wait_checks(tmp_path, monkeypatch)
>       assert len(load_notifications()) == 1
E       assert 0 == 1
E        +  where 0 = len([])
E        +    where [] = load_notifications()

tests/test_axe_chop_wait_checks_stranded_beads_notify.py:351: AssertionError
----------------------------- Captured stdout call -----------------------------
[wait_checks] waiter walk progress: projects=1 artifacts=1 waiting=1 live=0 dead=0 unknown_liveness=1 elapsed_ms=0
[wait_checks] resolving view progress: rows=0 scoped_waiters=1 full_view_waiters=0 elapsed_ms=0
[wait_checks] Stranded-bead collection failed for proj; leaving notifications unchanged: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
wait_checks: projects=1 artifacts=1 waiting=1 live_waiting=0 dead_waiting=0 unknown_liveness=1 ready_written=0 already_ready=0 invalid=0 unresolved=1 unknown_outcome=0 deferred_unconfirmed=0 waiter_errors=0 walk_ms=0 view_ms=0 resolve_ms=0 view_rows=0 scoped_waiters=1 full_view_waiters=0 reason=dependencies_not_ready
_________ test_stranded_alert_dismisses_when_waiting_marker_is_removed _________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw1/test_stranded_alert_dismisses_1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5de95ead60>

    def test_stranded_alert_dismisses_when_waiting_marker_is_removed(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        closed_ids: set[str] = set()
        point_wait_bead_status(monkeypatch, closed_ids)
        now = time.time()
        artifact = tmp_path / "stranded-turn"
        artifact.mkdir()
        issues = [
            phase(STRANDED_BEAD_ID, assignee=STRANDED_BEAD_ID, parent_id=STRANDED_PARENT_ID)
        ]
        records = [
            record(
                artifact,
                name=STRANDED_BEAD_ID,
                session=STRANDED_BEAD_ID,
                done=DoneMarkerWire(outcome="completed", finished_at=now - 3600),
            )
        ]
        wire_targeted_collector(monkeypatch, tmp_path, issues, records)
        waiter = make_waiters(tmp_path, "waiter")[0]
    
        run_wait_checks(tmp_path, monkeypatch)
>       assert len(load_notifications()) == 1
E       assert 0 == 1
E        +  where 0 = len([])
E        +    where [] = load_notifications()

tests/test_axe_chop_wait_checks_stranded_beads_notify.py:390: AssertionError
----------------------------- Captured stdout call -----------------------------
[wait_checks] waiter walk progress: projects=1 artifacts=1 waiting=1 live=0 dead=0 unknown_liveness=1 elapsed_ms=0
[wait_checks] resolving view progress: rows=0 scoped_waiters=1 full_view_waiters=0 elapsed_ms=0
[wait_checks] Stranded-bead collection failed for proj; leaving notifications unchanged: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
wait_checks: projects=1 artifacts=1 waiting=1 live_waiting=0 dead_waiting=0 unknown_liveness=1 ready_written=0 already_ready=0 invalid=0 unresolved=1 unknown_outcome=0 deferred_unconfirmed=0 waiter_errors=0 walk_ms=0 view_ms=0 resolve_ms=0 view_rows=0 scoped_waiters=1 full_view_waiters=0 reason=dependencies_not_ready
________________ test_stranded_alert_dismisses_when_waiter_died ________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw1/test_stranded_alert_dismisses_2')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5de95ea350>

    def test_stranded_alert_dismisses_when_waiter_died(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        closed_ids: set[str] = set()
        point_wait_bead_status(monkeypatch, closed_ids)
        now = time.time()
        artifact = tmp_path / "stranded-turn"
        artifact.mkdir()
        issues = [
            phase(STRANDED_BEAD_ID, assignee=STRANDED_BEAD_ID, parent_id=STRANDED_PARENT_ID)
        ]
        records = [
            record(
                artifact,
                name=STRANDED_BEAD_ID,
                session=STRANDED_BEAD_ID,
                done=DoneMarkerWire(outcome="completed", finished_at=now - 3600),
            )
        ]
        wire_targeted_collector(monkeypatch, tmp_path, issues, records)
        waiter = make_waiters(tmp_path, "waiter")[0]
    
        run_wait_checks(tmp_path, monkeypatch)
>       assert len(load_notifications()) == 1
E       assert 0 == 1
E        +  where 0 = len([])
E        +    where [] = load_notifications()

tests/test_axe_chop_wait_checks_stranded_beads_notify.py:425: AssertionError
----------------------------- Captured stdout call -----------------------------
[wait_checks] waiter walk progress: projects=1 artifacts=1 waiting=1 live=0 dead=0 unknown_liveness=1 elapsed_ms=0
[wait_checks] resolving view progress: rows=0 scoped_waiters=1 full_view_waiters=0 elapsed_ms=0
[wait_checks] Stranded-bead collection failed for proj; leaving notifications unchanged: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
wait_checks: projects=1 artifacts=1 waiting=1 live_waiting=0 dead_waiting=0 unknown_liveness=1 ready_written=0 already_ready=0 invalid=0 unresolved=1 unknown_outcome=0 deferred_unconfirmed=0 waiter_errors=0 walk_ms=0 view_ms=0 resolve_ms=0 view_rows=0 scoped_waiters=1 full_view_waiters=0 reason=dependencies_not_ready
__ test_notification_only_reconciliation_dismisses_resolved_states[settling] ___
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw1/test_notification_only_reconci0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5de95e9630>
state = 'settling'

    @pytest.mark.parametrize("state", ["settling", "owned", "delegated"])
    def test_notification_only_reconciliation_dismisses_resolved_states(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        state: str,
    ) -> None:
        point_wait_bead_status(monkeypatch)
        now = time.time()
        artifact = tmp_path / "active-turn"
        artifact.mkdir()
        issues = [
            phase(STRANDED_BEAD_ID, assignee=STRANDED_BEAD_ID, parent_id=STRANDED_PARENT_ID)
        ]
        if state == "settling":
            records = [
                record(
                    artifact,
                    name=STRANDED_BEAD_ID,
                    session=STRANDED_BEAD_ID,
                    done=DoneMarkerWire(outcome="completed", finished_at=now - 30),
                )
            ]
        elif state == "owned":
            records = [
                record(
                    artifact,
                    name=STRANDED_BEAD_ID,
                    session=STRANDED_BEAD_ID,
                    pid=os.getpid(),
                )
            ]
        else:
            from sase.agent.pending_handoff import PLAN_PENDING_MARKER
    
            (artifact / PLAN_PENDING_MARKER).write_text("", encoding="utf-8")
            records = [
                record(
                    artifact,
                    name=STRANDED_BEAD_ID,
                    session=STRANDED_BEAD_ID,
                    done=DoneMarkerWire(outcome="completed", finished_at=now - 3600),
                )
            ]
        wire_targeted_collector(monkeypatch, tmp_path, issues, records)
        monkeypatch.setattr(Path, "home", lambda: tmp_path)
        ensure_projects_dir(tmp_path)
        seed_stranded_notification("proj", STRANDED_BEAD_ID)
    
        run_wait_checks(tmp_path, monkeypatch)
    
>       assert load_notifications() == []
E       AssertionError: assert [Notification...oj:sase-1.2')] == []
E         
E         Left contains one more item: Notification(id='9b9393b0-8710-4590-9a9c-34591869d13b', timestamp='2026-10-26T00:00:00+00:00', sender='wait_checks', i...until=None, resurfaced_at=None, plus_ones=[], plus_ones_dropped=0, dedup_key='wait_checks:stranded-bead:proj:sase-1.2')
E         Use -v to get more diff

tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py:211: AssertionError
----------------------------- Captured stdout call -----------------------------
[wait_checks] waiter walk progress: projects=1 artifacts=0 waiting=0 live=0 dead=0 unknown_liveness=0 elapsed_ms=0
[wait_checks] resolving view progress: rows=0 scoped_waiters=0 full_view_waiters=0 elapsed_ms=0
[wait_checks] Stranded-bead collection failed for proj; leaving notifications unchanged: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
wait_checks: projects=1 artifacts=0 waiting=0 live_waiting=0 dead_waiting=0 unknown_liveness=0 ready_written=0 already_ready=0 invalid=0 unresolved=0 unknown_outcome=0 deferred_unconfirmed=0 waiter_errors=0 walk_ms=0 view_ms=0 resolve_ms=1 view_rows=0 scoped_waiters=0 full_view_waiters=0 reason=no_waiting_markers
____ test_notification_only_reconciliation_dismisses_resolved_states[owned] ____
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw1/test_notification_only_reconci1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5deb1a0ad0>
state = 'owned'

    @pytest.mark.parametrize("state", ["settling", "owned", "delegated"])
    def test_notification_only_reconciliation_dismisses_resolved_states(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        state: str,
    ) -> None:
        point_wait_bead_status(monkeypatch)
        now = time.time()
        artifact = tmp_path / "active-turn"
        artifact.mkdir()
        issues = [
            phase(STRANDED_BEAD_ID, assignee=STRANDED_BEAD_ID, parent_id=STRANDED_PARENT_ID)
        ]
        if state == "settling":
            records = [
                record(
                    artifact,
                    name=STRANDED_BEAD_ID,
                    session=STRANDED_BEAD_ID,
                    done=DoneMarkerWire(outcome="completed", finished_at=now - 30),
                )
            ]
        elif state == "owned":
            records = [
                record(
                    artifact,
                    name=STRANDED_BEAD_ID,
                    session=STRANDED_BEAD_ID,
                    pid=os.getpid(),
                )
            ]
        else:
            from sase.agent.pending_handoff import PLAN_PENDING_MARKER
    
            (artifact / PLAN_PENDING_MARKER).write_text("", encoding="utf-8")
            records = [
                record(
                    artifact,
                    name=STRANDED_BEAD_ID,
                    session=STRANDED_BEAD_ID,
                    done=DoneMarkerWire(outcome="completed", finished_at=now - 3600),
                )
            ]
        wire_targeted_collector(monkeypatch, tmp_path, issues, records)
        monkeypatch.setattr(Path, "home", lambda: tmp_path)
        ensure_projects_dir(tmp_path)
        seed_stranded_notification("proj", STRANDED_BEAD_ID)
    
        run_wait_checks(tmp_path, monkeypatch)
    
>       assert load_notifications() == []
E       AssertionError: assert [Notification...oj:sase-1.2')] == []
E         
E         Left contains one more item: Notification(id='4de0b9a4-c767-44f6-8c6a-127320755b3b', timestamp='2026-10-26T00:00:00+00:00', sender='wait_checks', i...until=None, resurfaced_at=None, plus_ones=[], plus_ones_dropped=0, dedup_key='wait_checks:stranded-bead:proj:sase-1.2')
E         Use -v to get more diff

tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py:211: AssertionError
----------------------------- Captured stdout call -----------------------------
[wait_checks] waiter walk progress: projects=1 artifacts=0 waiting=0 live=0 dead=0 unknown_liveness=0 elapsed_ms=0
[wait_checks] resolving view progress: rows=0 scoped_waiters=0 full_view_waiters=0 elapsed_ms=0
[wait_checks] Stranded-bead collection failed for proj; leaving notifications unchanged: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
wait_checks: projects=1 artifacts=0 waiting=0 live_waiting=0 dead_waiting=0 unknown_liveness=0 ready_written=0 already_ready=0 invalid=0 unresolved=0 unknown_outcome=0 deferred_unconfirmed=0 waiter_errors=0 walk_ms=0 view_ms=0 resolve_ms=1 view_rows=0 scoped_waiters=0 full_view_waiters=0 reason=no_waiting_markers
__ test_notification_only_reconciliation_dismisses_resolved_states[delegated] __
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw1/test_notification_only_reconci2')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5deb1a02f0>
state = 'delegated'

    @pytest.mark.parametrize("state", ["settling", "owned", "delegated"])
    def test_notification_only_reconciliation_dismisses_resolved_states(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        state: str,
    ) -> None:
        point_wait_bead_status(monkeypatch)
        now = time.time()
        artifact = tmp_path / "active-turn"
        artifact.mkdir()
        issues = [
            phase(STRANDED_BEAD_ID, assignee=STRANDED_BEAD_ID, parent_id=STRANDED_PARENT_ID)
        ]
        if state == "settling":
            records = [
                record(
                    artifact,
                    name=STRANDED_BEAD_ID,
                    session=STRANDED_BEAD_ID,
                    done=DoneMarkerWire(outcome="completed", finished_at=now - 30),
                )
            ]
        elif state == "owned":
            records = [
                record(
                    artifact,
                    name=STRANDED_BEAD_ID,
                    session=STRANDED_BEAD_ID,
                    pid=os.getpid(),
                )
            ]
        else:
            from sase.agent.pending_handoff import PLAN_PENDING_MARKER
    
            (artifact / PLAN_PENDING_MARKER).write_text("", encoding="utf-8")
            records = [
                record(
                    artifact,
                    name=STRANDED_BEAD_ID,
                    session=STRANDED_BEAD_ID,
                    done=DoneMarkerWire(outcome="completed", finished_at=now - 3600),
                )
            ]
        wire_targeted_collector(monkeypatch, tmp_path, issues, records)
        monkeypatch.setattr(Path, "home", lambda: tmp_path)
        ensure_projects_dir(tmp_path)
        seed_stranded_notification("proj", STRANDED_BEAD_ID)
    
        run_wait_checks(tmp_path, monkeypatch)
    
>       assert load_notifications() == []
E       AssertionError: assert [Notification...oj:sase-1.2')] == []
E         
E         Left contains one more item: Notification(id='8e170ced-8399-4e9f-a57a-01019029daf4', timestamp='2026-10-26T00:00:00+00:00', sender='wait_checks', i...until=None, resurfaced_at=None, plus_ones=[], plus_ones_dropped=0, dedup_key='wait_checks:stranded-bead:proj:sase-1.2')
E         Use -v to get more diff

tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py:211: AssertionError
----------------------------- Captured stdout call -----------------------------
[wait_checks] waiter walk progress: projects=1 artifacts=0 waiting=0 live=0 dead=0 unknown_liveness=0 elapsed_ms=0
[wait_checks] resolving view progress: rows=0 scoped_waiters=0 full_view_waiters=0 elapsed_ms=0
[wait_checks] Stranded-bead collection failed for proj; leaving notifications unchanged: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
wait_checks: projects=1 artifacts=0 waiting=0 live_waiting=0 dead_waiting=0 unknown_liveness=0 ready_written=0 already_ready=0 invalid=0 unresolved=0 unknown_outcome=0 deferred_unconfirmed=0 waiter_errors=0 walk_ms=0 view_ms=0 resolve_ms=1 view_rows=0 scoped_waiters=0 full_view_waiters=0 reason=no_waiting_markers
________ test_reconciliation_collects_only_pending_and_outstanding_ids _________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw1/test_reconciliation_collects_o0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5deb355780>

    def test_reconciliation_collects_only_pending_and_outstanding_ids(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        point_wait_bead_status(monkeypatch)
        now = time.time()
        artifact = tmp_path / "stranded-turn"
        artifact.mkdir()
        other_id = "sase-9"
        issues = [
            phase(
                STRANDED_BEAD_ID, assignee=STRANDED_BEAD_ID, parent_id=STRANDED_PARENT_ID
            ),
            phase(other_id, assignee=other_id, parent_id="sase-8"),
            phase("sase-1.3", assignee="sase-1.3", parent_id=STRANDED_PARENT_ID),
        ]
        records = [
            record(
                artifact,
                name=STRANDED_BEAD_ID,
                session=STRANDED_BEAD_ID,
                done=DoneMarkerWire(outcome="completed", finished_at=now - 3600),
            )
        ]
        wire_targeted_collector(monkeypatch, tmp_path, issues, records)
        make_waiters(tmp_path, "waiter")
        monkeypatch.setattr(Path, "home", lambda: tmp_path)
        seed_stranded_notification("other-proj", other_id)
        append_notification(
            Notification(
                id=str(uuid4()),
                timestamp="2026-10-26T00:00:00+00:00",
                sender="wait_checks",
                notes=["malformed"],
                tags=["wait", "blocked", "stranded"],
                dedup_key="wait_checks:stranded-bead:proj",
            )
        )
        append_notification(
            Notification(
                id=str(uuid4()),
                timestamp="2026-10-26T00:00:00+00:00",
                sender="wait_checks",
                notes=["unrelated"],
                tags=["wait", "blocked"],
                dedup_key="wait_checks:terminal-blocked:/tmp/waiter",
            )
        )
        append_notification(
            Notification(
                id=str(uuid4()),
                timestamp="2026-10-26T00:00:00+00:00",
                sender="other",
                notes=["wrong sender"],
                tags=["stranded"],
                dedup_key=f"wait_checks:stranded-bead:proj:{STRANDED_BEAD_ID}",
            )
        )
        calls = capture_collection_targets(monkeypatch)
    
        run_wait_checks(tmp_path, monkeypatch)
    
        assert sorted(calls) == [
            ("other-proj", (other_id,)),
            ("proj", (STRANDED_BEAD_ID,)),
        ]
>       assert any(
            row.dedup_key == f"wait_checks:stranded-bead:proj:{STRANDED_BEAD_ID}"
            for row in load_notifications()
            if row.sender == "wait_checks"
        )
E       assert False
E        +  where False = any(<generator object test_reconciliation_collects_only_pending_and_outstanding_ids.<locals>.<genexpr> at 0x7f5de7269620>)

tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py:403: AssertionError
----------------------------- Captured stdout call -----------------------------
[wait_checks] waiter walk progress: projects=1 artifacts=1 waiting=1 live=0 dead=0 unknown_liveness=1 elapsed_ms=0
[wait_checks] resolving view progress: rows=0 scoped_waiters=1 full_view_waiters=0 elapsed_ms=0
[wait_checks] Stranded-bead collection failed for proj; leaving notifications unchanged: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
wait_checks: projects=1 artifacts=1 waiting=1 live_waiting=0 dead_waiting=0 unknown_liveness=1 ready_written=0 already_ready=0 invalid=0 unresolved=1 unknown_outcome=0 deferred_unconfirmed=0 waiter_errors=0 walk_ms=0 view_ms=0 resolve_ms=1 view_rows=0 scoped_waiters=1 full_view_waiters=0 reason=dependencies_not_ready
____ test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker ____
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw2/test_start_monitor_kills_a_sup0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5ec5ccda20>

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
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw2/test_start_monitor_scrubs_agen0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5ec5d31860>

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
E       AssertionError: assert 'SASE_AGENT' not in {'SASE_GH_WORKSPACE_DIR': '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/', 'USER': 'bryan', 'CARGO_T...ryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws0-261028_204920', 'SASE_SERVICE_PROC': 'telegram_receiver', ...}

tests/monitor/test_monitor_start_supervisor.py:155: AssertionError
___________________ test_live_successor_owns_recovered_work ____________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6925621080>
tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw3/test_live_successor_owns_recov0')

    def test_live_successor_owns_recovered_work(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        with _seed_git_store(tmp_path / "store") as project:
            task_id = _recover_unassigned_task(project, tmp_path)
            claimed = project.claim_for_agent_launch(task_id, "successor")
            assert claimed.status == Status.IN_PROGRESS
            assert claimed.assignee == "successor"
            assert claimed.completion_failure is None
            beads_dir = project.beads_dir
        artifact = tmp_path / "artifacts" / "successor"
        artifact.mkdir(parents=True)
        live = record(
            artifact,
            name="successor",
            session="successor",
            pid=_PID,
            run_started_at="2026-10-26T19:00:00-04:00",
        )
        _point_collector_at_store(monkeypatch, tmp_path, beads_dir)
        index = tmp_path / "agent_artifact_index.sqlite"
        index.write_bytes(b"")
        monkeypatch.setattr(
            "sase.bead.stranded_facts.default_agent_artifact_index_path", lambda: index
        )
        from sase.core.agent_scan_wire import (
            AgentArtifactScanOptionsWire,
            AgentArtifactScanStatsWire,
            AgentArtifactScanWire,
        )
    
        def query(_index_path, projects_root, _query, options):
            return AgentArtifactScanWire(
                schema_version=12,
                projects_root=str(projects_root),
                options=options or AgentArtifactScanOptionsWire(),
                stats=AgentArtifactScanStatsWire(),
                records=[live],
            )
    
        monkeypatch.setattr("sase.bead.stranded_facts.query_agent_artifact_index", query)
>       report = reduce_stranded_work(collect_stranded_work_input(PROJECT, now=_NOW))
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_stranded_recovery_surfaces.py:183: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

facts = {'schema_version': 1, 'now': 1793041200.0, 'settle_grace_seconds': 120.0, 'beads': [{'id': 'store-1', 'kind': 'task', 'status': 'in_progress', 'candidate': True, ...}]}

    def reduce_stranded_work(facts: Mapping[str, Any]) -> StrandedWorkReport:
        """Classify bead facts through ``stranded_work_reduce``.
    
        *facts* is the reducer input mapping (schema_version, now,
        settle_grace_seconds, beads). Missing keys use the wire defaults.
        """
>       raw = _reduce_binding()(dict(facts))
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       ValueError: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`

src/sase/core/stranded_work_facade.py:119: ValueError
____________ test_in_progress_parent_is_blocked_by_recovered_phase _____________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6925622970>
tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw3/test_in_progress_parent_is_blo0')

    def test_in_progress_parent_is_blocked_by_recovered_phase(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        with _seed_git_store(tmp_path / "store") as project:
            plan = project.create("Recovery plan", IssueType.PLAN, tier="epic")
            phase = project.create(
                "Recovery phase",
                IssueType.PHASE,
                parent_id=plan.id,
                size=PhaseSize.MEDIUM,
                created_by="probe",
            )
            project.update(plan.id, status="in_progress", assignee="sase-plan.land")
            project.close(
                [phase.id],
                resolution=Resolution.DONE,
                close_provenance={
                    "run_id": "origin-run",
                    "agent_name": "origin-agent",
                    "artifact_dir": str(tmp_path / "artifacts"),
                },
            )
            rust_beads.recover_failed_closes(
                project.beads_dir,
                {
                    "run_id": "origin-run",
                    "failed_at": "2026-10-26T18:00:00Z",
                    "failure_code": "hook_failed",
                    "evidence_locations": [str(tmp_path / "artifacts")],
                    "note": "STITCH FAILED: hook failed for run origin-run.",
                    "actor": "origin-agent",
                },
            )
            recovered = project.show(phase.id)
            parent = project.show(plan.id)
            assert recovered.status == Status.OPEN
            assert parent.status == Status.IN_PROGRESS
            beads_dir = project.beads_dir
            phase_id = phase.id
            plan_id = plan.id
        lander = tmp_path / "artifacts" / "lander"
        origin = tmp_path / "artifacts" / "origin"
        lander.mkdir(parents=True)
        origin.mkdir(parents=True)
        live_parent = record(
            lander,
            name="sase-plan.land",
            session="sase-plan.land",
            pid=_PID,
            run_started_at="2026-10-26T19:00:00-04:00",
        )
        dead_phase = record(
            origin,
            name="origin-agent",
            session="origin-session",
            done=DoneMarkerWire(outcome="failed", finished_at=_NOW - 3600),
        )
        _point_collector_at_store(monkeypatch, tmp_path, beads_dir)
        index = tmp_path / "agent_artifact_index.sqlite"
        index.write_bytes(b"")
        monkeypatch.setattr(
            "sase.bead.stranded_facts.default_agent_artifact_index_path", lambda: index
        )
        from sase.core.agent_scan_wire import (
            AgentArtifactScanOptionsWire,
            AgentArtifactScanStatsWire,
            AgentArtifactScanWire,
        )
    
        def query(_index_path, projects_root, _query, options):
            return AgentArtifactScanWire(
                schema_version=12,
                projects_root=str(projects_root),
                options=options or AgentArtifactScanOptionsWire(),
                stats=AgentArtifactScanStatsWire(),
                records=[live_parent, dead_phase],
            )
    
        monkeypatch.setattr("sase.bead.stranded_facts.query_agent_artifact_index", query)
>       report = reduce_stranded_work(collect_stranded_work_input(PROJECT, now=_NOW))
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_stranded_recovery_surfaces.py:286: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

facts = {'schema_version': 1, 'now': 1793041200.0, 'settle_grace_seconds': 120.0, 'beads': [{'id': 'store-1', 'kind': 'epic', ...in_progress', 'candidate': True, ...}, {'id': 'store-1.1', 'kind': 'phase', 'status': 'open', 'candidate': True, ...}]}

    def reduce_stranded_work(facts: Mapping[str, Any]) -> StrandedWorkReport:
        """Classify bead facts through ``stranded_work_reduce``.
    
        *facts* is the reducer input mapping (schema_version, now,
        settle_grace_seconds, beads). Missing keys use the wire defaults.
        """
>       raw = _reduce_binding()(dict(facts))
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       ValueError: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`

src/sase/core/stranded_work_facade.py:119: ValueError
_________________ test_single_turn_unclosed_phase_is_stranded __________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6925621160>
tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw3/test_single_turn_unclosed_phas0')

    def test_single_turn_unclosed_phase_is_stranded(monkeypatch, tmp_path: Path) -> None:
        wire_collector(
            monkeypatch,
            tmp_path,
            [phase("sase-1.2", assignee="sase-1.2")],
            _root_done_records(tmp_path),
        )
        report = load_stranded_report(PROJECT, now=_NOW)
>       assert report.report.stranded_ids == ("sase-1.2",)
E       AssertionError: assert () == ('sase-1.2',)
E         
E         Right contains one more item: 'sase-1.2'
E         Use -v to get more diff

tests/test_stranded_single_turn.py:110: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.bead.stranded:stranded.py:46 stranded-work collector failed for project demo; returning empty report
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/bead/stranded.py", line 44, in load_stranded_report
    report = reduce_stranded_work(facts)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/stranded_work_facade.py", line 119, in reduce_stranded_work
    raw = _reduce_binding()(dict(facts))
ValueError: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
______________ test_single_turn_stranded_phase_blocks_parent_epic ______________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f691d4faf90>
tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw3/test_single_turn_stranded_phas0')

    def test_single_turn_stranded_phase_blocks_parent_epic(
        monkeypatch, tmp_path: Path
    ) -> None:
        land_dir = _dir(tmp_path, "sase-1.land")
        wire_collector(
            monkeypatch,
            tmp_path,
            [
                epic("sase-1", assignee="sase-1.land"),
                phase("sase-1.2", assignee="sase-1.2", parent_id="sase-1"),
            ],
            [
                *_root_done_records(tmp_path),
                # The land agent is a live single-turn waiter: a root member
                # with no agent_session, owned until propagation marks it
                # blocked on the stranded leaf.
                record(
                    land_dir,
                    name="sase-1.land",
                    session=None,
                    run_started_at="2026-10-22T12:00:00-04:00",
                    waiting=WaitingMarkerWire(waiting_for=["sase-1.2"]),
                ),
            ],
        )
        report = load_stranded_report(PROJECT, now=_NOW)
>       assert report.report.stranded_ids == ("sase-1.2",)
E       AssertionError: assert () == ('sase-1.2',)
E         
E         Right contains one more item: 'sase-1.2'
E         Use -v to get more diff

tests/test_stranded_single_turn.py:144: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.bead.stranded:stranded.py:46 stranded-work collector failed for project demo; returning empty report
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/bead/stranded.py", line 44, in load_stranded_report
    report = reduce_stranded_work(facts)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/stranded_work_facade.py", line 119, in reduce_stranded_work
    raw = _reduce_binding()(dict(facts))
ValueError: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
________________ test_live_single_turn_waiting_member_is_owned _________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f691d3f8360>
tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw3/test_live_single_turn_waiting_0')

    def test_live_single_turn_waiting_member_is_owned(monkeypatch, tmp_path: Path) -> None:
        artifact = _dir(tmp_path, "sase-1.2")
        wire_collector(
            monkeypatch,
            tmp_path,
            [phase("sase-1.2", assignee="sase-1.2")],
            [
                record(
                    artifact,
                    name="sase-1.2",
                    session=None,
                    run_started_at="2026-10-22T12:00:00-04:00",
                    waiting=WaitingMarkerWire(waiting_for=["sase-9"]),
                )
            ],
        )
        report = load_stranded_report(PROJECT, now=_NOW)
>       verdict = next(
            item for item in report.report.verdicts if item.bead_id == "sase-1.2"
        )
E       StopIteration

tests/test_stranded_single_turn.py:168: StopIteration
------------------------------ Captured log call -------------------------------
WARNING  sase.bead.stranded:stranded.py:46 stranded-work collector failed for project demo; returning empty report
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/bead/stranded.py", line 44, in load_stranded_report
    report = reduce_stranded_work(facts)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/stranded_work_facade.py", line 119, in reduce_stranded_work
    raw = _reduce_binding()(dict(facts))
ValueError: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
________________ test_multi_member_session_classifies_as_before ________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f691d3f9c50>
tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-8/popen-gw3/test_multi_member_session_clas0')

    def test_multi_member_session_classifies_as_before(monkeypatch, tmp_path: Path) -> None:
        root_dir = _dir(tmp_path, "root")
        successor_dir = _dir(tmp_path, "successor")
        records = [
            record(
                root_dir,
                name="sase-1.2",
                session=None,
                done=DoneMarkerWire(outcome="completed", finished_at=_NOW - 3600),
            ),
            record(
                successor_dir,
                name="sase-1.2--plan",
                session="sase-1.2",
                done=DoneMarkerWire(outcome="completed", finished_at=_NOW - 3600),
            ),
        ]
        wire_collector(
            monkeypatch, tmp_path, [phase("sase-1.2", assignee="sase-1.2")], records
        )
        multi = load_stranded_report(PROJECT, now=_NOW)
>       multi_verdict = next(
            item for item in multi.report.verdicts if item.bead_id == "sase-1.2"
        )
E       StopIteration

tests/test_stranded_single_turn.py:220: StopIteration
------------------------------ Captured log call -------------------------------
WARNING  sase.bead.stranded:stranded.py:46 stranded-work collector failed for project demo; returning empty report
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/bead/stranded.py", line 44, in load_stranded_report
    report = reduce_stranded_work(facts)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/stranded_work_facade.py", line 119, in reduce_stranded_work
    raw = _reduce_binding()(dict(facts))
ValueError: request is not a valid StrandedWorkInputWire dict: unknown field `staged_handoff`, expected one of `name`, `artifact_dir`, `turn_kind`, `lifecycle`, `process_live`, `remote`, `finalizing`, `pending_handoff`, `handoff_inflight`, `recovery_in_flight`, `turn_state`, `followup_pending`, `followup_outcome`, `followup_agent`, `declared_bead_action`, `started_at`, `ended_at`
=============================== warnings summary ===============================
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

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_agent_archive_column_app.py::test_open_mounts_the_archive_column_without_a_flag
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:110: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    def deepcopy(x, memo=None, _nil=[]):
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

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
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
  <frozen os>:898: DeprecationWarning: This process (pid=2635698) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

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

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
35.79s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
31.24s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
29.46s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
19.31s call     tests/test_procs_service_settlement.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
17.03s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
15.10s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
13.34s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
12.88s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
11.84s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
11.58s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
10.42s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent
10.06s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
9.98s call     tests/test_procs_facade_retention.py::test_service_proc_retention_uses_per_service_buckets
9.91s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_raises_and_restores_the_claim_when_the_supervisor_never_acknowledges
9.61s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
9.55s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_releases_a_fresh_numbered_claim_when_the_supervisor_never_acknowledges
9.47s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
9.42s call     tests/ace/tui/test_agents_filter_bar_session.py::test_escape_restores_the_prior_committed_query
9.41s call     tests/test_finalizers_live_e2e_cycles.py::test_live_command_and_fixture_plugin_run_in_order
9.33s call     tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
=========================== short test summary info ============================
FAILED tests/test_axe_chop_wait_checks_stranded_beads_notify.py::test_stranded_bead_waiters_share_one_notification
FAILED tests/test_axe_chop_wait_checks_stranded_beads_notify.py::test_stranded_bead_notification_dismisses_after_close
FAILED tests/test_axe_chop_wait_checks_stranded_beads_notify.py::test_stranded_alert_dismisses_when_waiter_is_already_ready
FAILED tests/test_axe_chop_wait_checks_stranded_beads_notify.py::test_stranded_alert_dismisses_when_waiting_marker_is_removed
FAILED tests/test_axe_chop_wait_checks_stranded_beads_notify.py::test_stranded_alert_dismisses_when_waiter_died
FAILED tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py::test_notification_only_reconciliation_dismisses_resolved_states[settling]
FAILED tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py::test_notification_only_reconciliation_dismisses_resolved_states[owned]
FAILED tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py::test_notification_only_reconciliation_dismisses_resolved_states[delegated]
FAILED tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py::test_reconciliation_collects_only_pending_and_outstanding_ids
FAILED tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
FAILED tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_scrubs_agent_identity_from_the_supervisor_env
FAILED tests/test_stranded_recovery_surfaces.py::test_live_successor_owns_recovered_work
FAILED tests/test_stranded_recovery_surfaces.py::test_in_progress_parent_is_blocked_by_recovered_phase
FAILED tests/test_stranded_single_turn.py::test_single_turn_unclosed_phase_is_stranded
FAILED tests/test_stranded_single_turn.py::test_single_turn_stranded_phase_blocks_parent_epic
FAILED tests/test_stranded_single_turn.py::test_live_single_turn_waiting_member_is_owned
FAILED tests/test_stranded_single_turn.py::test_multi_member_session_classifies_as_before
===== 17 failed, 9169 passed, 1 skipped, 66 warnings in 941.69s (0:15:41) ======
error: recipe `test-scoped` failed on line 631 with exit code 1
error: recipe `check` failed on line 897 with exit code 1
failed/1  1357498ms
triage test (scoped): 2 KNOWN 13 NEW
NEW test (scoped): FAILED tests/test_axe_chop_wait_checks_stranded_beads_notify.py::test_stranded_alert_dismisses_when_waiting_marker_is_removed — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py::test_reconciliation_collects_only_pending_and_outstanding_ids — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_stranded_single_turn.py::test_single_turn_unclosed_phase_is_stranded — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_axe_chop_wait_checks_stranded_beads_notify.py::test_stranded_bead_notification_dismisses_after_close — recorded evidence; no owner
NEW test (scoped): FAILED tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_scrubs_agent_identity_from_the_supervisor_env — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_stranded_single_turn.py::test_single_turn_stranded_phase_blocks_parent_epic — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_stranded_recovery_surfaces.py::test_in_progress_parent_is_blocked_by_recovered_phase — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_axe_chop_wait_checks_stranded_beads_reconcile.py::test_notification_only_reconciliation_dismisses_resolved_states[settling] — recorded evidence; no owner
NEW test (scoped): FAILED tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_stranded_single_turn.py::test_multi_member_session_classifies_as_before — recorded evidence; no owner
KNOWN test (scoped): FAILED tests/test_axe_chop_wait_checks_stranded_beads_notify.py::test_stranded_alert_dismisses_when_waiter_died — witness 1c51d80c6d66b8ed60d2e0c8972a0a9a; no owner
KNOWN test (scoped): FAILED tests/test_stranded_recovery_surfaces.py::test_live_successor_owns_recovered_work — witness 1c51d80c6d66b8ed60d2e0c8972a0a9a; no owner
sase tool show 4637bbba3802ceb5cd504a581dae5aa1 -l
verdict: new_failures — 13 NEW, 2 KNOWN; exit 1

