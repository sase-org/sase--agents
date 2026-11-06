# Chat History - ace-run (sase-1rg.7--mon)

- **TIMESTAMP:** 2026-11-06 07:38:55 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1rg.7--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'Finish just check for staged-response phase sase-1rg.7'

## Response

sase tool run 081aa415628a9ddcaa242a9a2214b2da
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (docs contract)
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.43.2 is missing 49 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] advance_agent_hijack_record: first appears in sase-core 65925ca (feat(agent-hijack): add core ledger and eligibility); no release tag contains it yet.
[core-floor-probe] agent_artifact_run_trash_wire_schema_version: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); no release tag contains it yet.
[core-floor-probe] agent_hijack_continuation_prompt: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_continuation_wire_schema_version: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_eligibility: first appears in sase-core 65925ca (feat(agent-hijack): add core ledger and eligibility); no release tag contains it yet.
[core-floor-probe] agent_hijack_escalation_target: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_escalation_wire_schema_version: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_status_for_done_marker: first appears in sase-core 65925ca (feat(agent-hijack): add core ledger and eligibility); no release tag contains it yet.
[core-floor-probe] agent_hijack_wire_schema_version: first appears in sase-core 65925ca (feat(agent-hijack): add core ledger and eligibility); no release tag contains it yet.
[core-floor-probe] agent_prompt_select: first appears in sase-core 45c6a26 (feat(agent-prompts): add Rust-owned agent prompt selection policy); no release tag contains it yet.
[core-floor-probe] bead_assess_epic_symbol_freshness: first appears in sase-core e60f3e1 (feat(bead): classify epic symbol freshness in Rust); no release tag contains it yet.
[core-floor-probe] bead_parse_epic_symbol_entries: first appears in sase-core e60f3e1 (feat(bead): classify epic symbol freshness in Rust); no release tag contains it yet.
[core-floor-probe] classify_instruction_readout: first appears in sase-core 6cd64a9 (feat(core): add instruction handoff readout classifier); no release tag contains it yet.
[core-floor-probe] decide_workspace_retention: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] decide_workspace_retention_dismissal: first appears in sase-core 154fe9e (feat(stranded-work): retain held workspace as stranded unless live successor owns); no release tag contains it yet.
[core-floor-probe] default_publication_cleanup_timeout: first appears in sase-core f061f5f (fix(git-lock): enforce effective budget in backoff and aged-lock decisions); no release tag contains it yet.
[core-floor-probe] effective_wait_target: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] evaluate_recovery_decision: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] hijack_recovery_confirm: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); no release tag contains it yet.
[core-floor-probe] hijack_recovery_effective_target: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); no release tag contains it yet.
[core-floor-probe] hijack_recovery_execution_wire_schema_version: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); no release tag contains it yet.
[core-floor-probe] hijack_recovery_preview: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); no release tag contains it yet.
[core-floor-probe] hijack_recovery_preview_wire_schema_version: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); no release tag contains it yet.
[core-floor-probe] hijack_recovery_reconcile: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); no release tag contains it yet.
[core-floor-probe] hijack_recovery_reconcile_wire_schema_version: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); no release tag contains it yet.
[core-floor-probe] hijack_recovery_rollback: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); no release tag contains it yet.
[core-floor-probe] hijack_recovery_validate_execution: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); no release tag contains it yet.
[core-floor-probe] list_agent_artifact_run_trash: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); no release tag contains it yet.
[core-floor-probe] normalize_hijack_rung: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); no release tag contains it yet.
[core-floor-probe] parse_wait_target: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] plan_checked_release_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] plan_pin_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] publication_parked_recheck_due: first appears in sase-core 542448a (feat(sase-core): anchor scanner rules, version blocks, add parked recheck); no release tag contains it yet.
[core-floor-probe] publication_protection_lookup_enforced: first appears in sase-core 542448a (feat(sase-core): anchor scanner rules, version blocks, add parked recheck); no release tag contains it yet.
[core-floor-probe] publication_protection_record_enforced: first appears in sase-core 542448a (feat(sase-core): anchor scanner rules, version blocks, add parked recheck); no release tag contains it yet.
[core-floor-probe] purge_agent_artifact_run_trash: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); no release tag contains it yet.
[core-floor-probe] quarantine_agent_artifact_runs: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); no release tag contains it yet.
[core-floor-probe] recovery_adoption_lock_filename: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] recovery_context_wire_schema_version: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] resolve_agent_run_state_observations: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] restore_agent_artifact_run_trash: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); no release tag contains it yet.
[core-floor-probe] select_agent_run_state_discovery_window: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_agent_run_state_hoods: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_current_wait_turn: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] staged_handoff_receipt_transition_allowed: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] staged_reconcile_page: first appears in sase-core 16a3ed0 (feat(staged-handoff): add bounded discovery and automatic recovery policy); no release tag contains it yet.
[core-floor-probe] strip_hijack_launch_directives: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); no release tag contains it yet.
[core-floor-probe] validate_recovery_context: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] workspace_retention_wire_schema_version: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "65925ca", "name": "advance_agent_hijack_record", "release": null, "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "3974441", "name": "agent_artifact_run_trash_wire_schema_version", "release": null, "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "f1bbb4f", "name": "agent_hijack_continuation_prompt", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "f1bbb4f", "name": "agent_hijack_continuation_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "65925ca", "name": "agent_hijack_eligibility", "release": null, "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "f1bbb4f", "name": "agent_hijack_escalation_target", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "f1bbb4f", "name": "agent_hijack_escalation_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "65925ca", "name": "agent_hijack_status_for_done_marker", "release": null, "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "65925ca", "name": "agent_hijack_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "45c6a26", "name": "agent_prompt_select", "release": null, "subject": "feat(agent-prompts): add Rust-owned agent prompt selection policy"}, {"commit": "e60f3e1", "name": "bead_assess_epic_symbol_freshness", "release": null, "subject": "feat(bead): classify epic symbol freshness in Rust"}, {"commit": "e60f3e1", "name": "bead_parse_epic_symbol_entries", "release": null, "subject": "feat(bead): classify epic symbol freshness in Rust"}, {"commit": "6cd64a9", "name": "classify_instruction_readout", "release": null, "subject": "feat(core): add instruction handoff readout classifier"}, {"commit": "80338d6", "name": "decide_workspace_retention", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "154fe9e", "name": "decide_workspace_retention_dismissal", "release": null, "subject": "feat(stranded-work): retain held workspace as stranded unless live successor owns"}, {"commit": "f061f5f", "name": "default_publication_cleanup_timeout", "release": null, "subject": "fix(git-lock): enforce effective budget in backoff and aged-lock decisions"}, {"commit": "d7b00dd", "name": "effective_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "evaluate_recovery_decision", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "417d5c8", "name": "hijack_recovery_confirm", "release": null, "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "417d5c8", "name": "hijack_recovery_effective_target", "release": null, "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "417d5c8", "name": "hijack_recovery_execution_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "bbef1df", "name": "hijack_recovery_preview", "release": null, "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "bbef1df", "name": "hijack_recovery_preview_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "bbef1df", "name": "hijack_recovery_reconcile", "release": null, "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "bbef1df", "name": "hijack_recovery_reconcile_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "417d5c8", "name": "hijack_recovery_rollback", "release": null, "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "417d5c8", "name": "hijack_recovery_validate_execution", "release": null, "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "3974441", "name": "list_agent_artifact_run_trash", "release": null, "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "f1bbb4f", "name": "normalize_hijack_rung", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "d7b00dd", "name": "parse_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "80338d6", "name": "plan_checked_release_workspace_claim_from_content", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "80338d6", "name": "plan_pin_workspace_claim_from_content", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "542448a", "name": "publication_parked_recheck_due", "release": null, "subject": "feat(sase-core): anchor scanner rules, version blocks, add parked recheck"}, {"commit": "542448a", "name": "publication_protection_lookup_enforced", "release": null, "subject": "feat(sase-core): anchor scanner rules, version blocks, add parked recheck"}, {"commit": "542448a", "name": "publication_protection_record_enforced", "release": null, "subject": "feat(sase-core): anchor scanner rules, version blocks, add parked recheck"}, {"commit": "3974441", "name": "purge_agent_artifact_run_trash", "release": null, "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "3974441", "name": "quarantine_agent_artifact_runs", "release": null, "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "73ec04a", "name": "recovery_adoption_lock_filename", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "73ec04a", "name": "recovery_context_wire_schema_version", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "dc5383f", "name": "resolve_agent_run_state_observations", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "3974441", "name": "restore_agent_artifact_run_trash", "release": null, "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "dc5383f", "name": "select_agent_run_state_discovery_window", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "dc5383f", "name": "select_agent_run_state_hoods", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "d7b00dd", "name": "select_current_wait_turn", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "staged_handoff_receipt_transition_allowed", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "16a3ed0", "name": "staged_reconcile_page", "release": null, "subject": "feat(staged-handoff): add bounded discovery and automatic recovery policy"}, {"commit": "f1bbb4f", "name": "strip_hijack_launch_directives", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "73ec04a", "name": "validate_recovery_context", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "80338d6", "name": "workspace_retention_wire_schema_version", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}], "declared_floor": "0.43.2", "exit_code": 4, "message": "sase-core-rs==0.43.2 is missing 49 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, contract-set-always, marker-audit, no-baseline-depth-boost, serial-budget-exceeded); 5627 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 5048 commits behind HEAD) matched 0 changed file(s) and contributed 0 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34
configfile: pyproject.toml
plugins: hypothesis-6.168.0, cov-7.1.0, platformdirs-4.14.5, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [8527 items]

........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 13%]
................................................................F....... [ 14%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
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
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
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
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 57%]
.......................F................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 73%]
...........................s.....................................ss..... [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
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
..............................s......................................... [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 99%]
...............................                                          [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_________________ test_adoption_waits_for_finalizer_settlement _________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-209af3f4/pytest-of-bryan/pytest-0/popen-gw1/test_adoption_waits_for_finali0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd484a66580>

    def test_adoption_waits_for_finalizer_settlement(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """The monitor check cannot launch before the commit finalizer settles."""
        from sase.axe.run_agent_exec_staged import dispatch_completed_staged_handoff
        from sase.axe.run_agent_exec_staged import StagedInlineContinuation
        from sase.agent.staged_handoff import write_staged_handoff
        from tests._axe_run_agent_exec_helpers import make_exec_ctx
        from sase.axe.run_agent_exec import LoopState
    
        staged_id = "aaaaaaaa-bbbb-4ccc-8ddd-eeeeeeeeeeee"
        monkeypatch.setenv("SASE_AGENT", "agent")
        monkeypatch.setenv("SASE_AGENT_NAME", "agent")
        ctx = make_exec_ctx(tmp_path, is_home_mode=False)
        artifacts = Path(ctx.artifacts_dir)
        monkeypatch.setenv("SASE_ARTIFACTS_DIR", str(artifacts))
        state = LoopState(
            current_prompt="p",
            current_role_suffix="",
            current_artifacts_dir=str(artifacts),
            loop_outcome="completed",
            sdd_spec_path=None,
            original_prompt="p",
        )
        record = {
            "schema_version": 1,
            "staged_id": staged_id,
            "kind": "monitor",
            "created_at": "2026-10-26T12:00:00Z",
            "payload": {"monitor_id": "monitor-1"},
            "successor_workspace": "inherit",
            "carry_allowed": True,
            "dirty_obligations_at_stage": [],
        }
        write_staged_handoff(record, artifacts_dir=str(artifacts))
        _write_agent_meta(artifacts)
        # Unsettled finalizer: adoption is held and no proc launches.
        (artifacts / "finalizer_result.json").write_text(
            json.dumps({"status": "running", "instances": []}), encoding="utf-8"
        )
        launches: list[str] = []
        monkeypatch.setattr(
            "sase.monitor.staged_owner.read_staged_owner_index",
            lambda monitor_id: {
                "staged_id": staged_id,
                "artifacts_dir": str(tmp_path / "m"),
            },
        )
    
        monkeypatch.setattr(
            "sase.axe.run_agent_exec_monitor.capture_monitor_handoff",
            lambda *_args, **_kwargs: SimpleNamespace(node_id="starter-node-1"),
        )
        monkeypatch.setattr(
            "sase.monitor.start_stage.launch_from_persisted_payload",
            lambda member_dir, **_kwargs: (
                launches.append(member_dir)
                or SimpleNamespace(monitor_id="m", artifacts_dir=member_dir)
            ),
        )
        dispatch = dispatch_completed_staged_handoff(
            str(artifacts), StagedInlineContinuation(ctx=ctx, state=state)
        )
        assert dispatch is not None and dispatch.adopted is False
        assert launches == []
    
        # Settled finalizer (commit hook included): one launch proceeds.
        (artifacts / "finalizer_result.json").write_text(
            json.dumps({"status": "success", "instances": []}), encoding="utf-8"
        )
        import sase.axe.run_agent_exec_staged_dispatch as dispatch_mod
    
        monkeypatch.setattr(
            dispatch_mod, "finalizer_settlement_refusal", lambda *a, **k: None
        )
>       monkeypatch.setattr(
            dispatch_mod, "read_staged_handoff_response", lambda *a, **k: "real response"
        )
E       AttributeError: <module 'sase.axe.run_agent_exec_staged_dispatch' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/axe/run_agent_exec_staged_dispatch.py'> has no attribute 'read_staged_handoff_response'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/monitor/test_monitor_start_activation.py:454: AttributeError
______________ test_unsupported_staged_kind_records_held_receipt _______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/bin/python

obj = <module 'sase.axe.run_agent_exec_staged_dispatch' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/axe/run_agent_exec_staged_dispatch.py'>
name = 'read_staged_handoff_response'
ann = 'sase.axe.run_agent_exec_staged_dispatch'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.axe.run_agent_exec_staged_dispatch' has no attribute 'read_staged_handoff_response'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-209af3f4/pytest-of-bryan/pytest-0/popen-gw1/test_unsupported_staged_kind_r0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd48534e2e0>

    def test_unsupported_staged_kind_records_held_receipt(
        tmp_path: Path,
        monkeypatch,
    ) -> None:
        ctx, state, artifacts = _continuation(tmp_path)
        # "monitor" is a supported staged kind since activation (sase-1pj.5.1.4);
        # exercise the unsupported path with a kind no adopter handles.
        record = {**_record(tmp_path), "kind": "bogus"}
        monkeypatch.setattr(
            "sase.axe.run_agent_exec_staged_dispatch.read_staged_handoff",
            lambda _root: record,
        )
>       monkeypatch.setattr(
            "sase.axe.run_agent_exec_staged_dispatch.read_staged_handoff_response",
            lambda *_args, **_kwargs: "planner response",
        )

tests/test_axe_run_agent_exec_staged.py:311: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.axe.run_agent_exec_staged_dispatch' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/axe/run_agent_exec_staged_dispatch.py'>
name = 'read_staged_handoff_response'
ann = 'sase.axe.run_agent_exec_staged_dispatch'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.axe.run_agent_exec_staged_dispatch has no attribute 'read_staged_handoff_response'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
=============================== warnings summary ===============================
tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=2800350) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/macro/workflow_runner.py:477: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
63.19s call     tests/test_launch_request_staging.py::test_typed_plan_and_continuation_survive_adoption
36.40s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
33.73s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
29.77s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
21.61s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
15.23s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
12.14s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
9.91s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent
9.87s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
9.10s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
8.61s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
8.24s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
8.18s call     tests/test_project_display_presentation_audit.py::test_project_labels_never_derive_from_paths
8.17s call     tests/test_project_display_presentation_audit.py::test_path_label_exemptions_name_existing_sites_and_rationales
7.94s call     tests/tool/test_settlement_retention.py::test_idle_timeout_settles_signaled_timeout
7.79s call     tests/tool/test_inline_escalation.py::test_sigterm_leaves_run_running
7.41s call     tests/fakey/test_pipe_e2e.py::test_two_link_chain_then_bound_leaves_the_agent_running
7.40s call     tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace
7.38s call     tests/tool/test_settlement_retention.py::test_total_timeout_settles_signaled_timeout
7.13s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
=========================== short test summary info ============================
FAILED tests/monitor/test_monitor_start_activation.py::test_adoption_waits_for_finalizer_settlement
FAILED tests/test_axe_run_agent_exec_staged.py::test_unsupported_staged_kind_records_held_receipt
====== 2 failed, 8521 passed, 4 skipped, 66 warnings in 564.82s (0:09:24) ======
error: recipe `test-scoped` failed on line 675 with exit code 1
error: recipe `check` failed on line 942 with exit code 1
failed  exit=1  duration=1047026ms
unattrib  31.3s
triage test (scoped): 2 NEW stopped
NEW test (scoped): FAILED tests/test_axe_run_agent_exec_staged.py::test_unsupported_staged_kind_records_held_receipt — recorded evidence; no owner
NEW test (scoped): FAILED tests/monitor/test_monitor_start_activation.py::test_adoption_waits_for_finalizer_settlement — recorded evidence; no owner
verdict: new_failures — 2 NEW; exit 1
failed/1  1047026ms
triage test (scoped): 2 NEW stopped
NEW test (scoped): FAILED tests/test_axe_run_agent_exec_staged.py::test_unsupported_staged_kind_records_held_receipt — recorded evidence; no owner
NEW test (scoped): FAILED tests/monitor/test_monitor_start_activation.py::test_adoption_waits_for_finalizer_settlement — recorded evidence; no owner
sase tool show 081aa415628a9ddcaa242a9a2214b2da -l
verdict: new_failures — 2 NEW; exit 1

