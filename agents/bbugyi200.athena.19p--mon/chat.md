# Chat History - ace-run (19p--mon)

- **TIMESTAMP:** 2026-11-07 14:44:21 EST
- **MODEL:** claude/opus
- **AGENT:** 19p--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'Finish just check (joined run) for the connect-unlaunched-project-sidecars plan'

## Response

sase tool run 4d441ab8c25555d7b67af8dd266a2c4d
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.44.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
[core-floor-probe] stale_actionable: sase-core-rs==0.43.2 is missing 50 capability(s) that exist in a published sase-core release.
[core-floor-probe] advance_agent_hijack_record: first appears in sase-core 65925ca (feat(agent-hijack): add core ledger and eligibility); release v0.44.0 contains it.
[core-floor-probe] agent_artifact_run_trash_wire_schema_version: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); release v0.44.0 contains it.
[core-floor-probe] agent_hijack_continuation_prompt: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); release v0.44.0 contains it.
[core-floor-probe] agent_hijack_continuation_wire_schema_version: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); release v0.44.0 contains it.
[core-floor-probe] agent_hijack_eligibility: first appears in sase-core 65925ca (feat(agent-hijack): add core ledger and eligibility); release v0.44.0 contains it.
[core-floor-probe] agent_hijack_escalation_target: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); release v0.44.0 contains it.
[core-floor-probe] agent_hijack_escalation_wire_schema_version: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); release v0.44.0 contains it.
[core-floor-probe] agent_hijack_status_for_done_marker: first appears in sase-core 65925ca (feat(agent-hijack): add core ledger and eligibility); release v0.44.0 contains it.
[core-floor-probe] agent_hijack_wire_schema_version: first appears in sase-core 65925ca (feat(agent-hijack): add core ledger and eligibility); release v0.44.0 contains it.
[core-floor-probe] agent_prompt_select: first appears in sase-core 45c6a26 (feat(agent-prompts): add Rust-owned agent prompt selection policy); release v0.44.0 contains it.
[core-floor-probe] bead_assess_epic_symbol_freshness: first appears in sase-core e60f3e1 (feat(bead): classify epic symbol freshness in Rust); release v0.44.0 contains it.
[core-floor-probe] bead_parse_epic_symbol_entries: first appears in sase-core e60f3e1 (feat(bead): classify epic symbol freshness in Rust); release v0.44.0 contains it.
[core-floor-probe] classify_instruction_readout: first appears in sase-core 6cd64a9 (feat(core): add instruction handoff readout classifier); release v0.44.0 contains it.
[core-floor-probe] decide_publication_rebase_conflict: first appears in sase-core e9c0a99 (feat(publication): add core rebase-conflict policy for agent publication); release v0.44.0 contains it.
[core-floor-probe] decide_workspace_retention: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); release v0.44.0 contains it.
[core-floor-probe] decide_workspace_retention_dismissal: first appears in sase-core 154fe9e (feat(stranded-work): retain held workspace as stranded unless live successor owns); release v0.44.0 contains it.
[core-floor-probe] default_publication_cleanup_timeout: first appears in sase-core f061f5f (fix(git-lock): enforce effective budget in backoff and aged-lock decisions); release v0.44.0 contains it.
[core-floor-probe] effective_wait_target: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] evaluate_recovery_decision: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); release v0.44.0 contains it.
[core-floor-probe] hijack_recovery_confirm: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); release v0.44.0 contains it.
[core-floor-probe] hijack_recovery_effective_target: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); release v0.44.0 contains it.
[core-floor-probe] hijack_recovery_execution_wire_schema_version: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); release v0.44.0 contains it.
[core-floor-probe] hijack_recovery_preview: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); release v0.44.0 contains it.
[core-floor-probe] hijack_recovery_preview_wire_schema_version: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); release v0.44.0 contains it.
[core-floor-probe] hijack_recovery_reconcile: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); release v0.44.0 contains it.
[core-floor-probe] hijack_recovery_reconcile_wire_schema_version: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); release v0.44.0 contains it.
[core-floor-probe] hijack_recovery_rollback: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); release v0.44.0 contains it.
[core-floor-probe] hijack_recovery_validate_execution: first appears in sase-core 417d5c8 (feat(agent-hijack): add execution validation and confirmation contract); release v0.44.0 contains it.
[core-floor-probe] list_agent_artifact_run_trash: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); release v0.44.0 contains it.
[core-floor-probe] normalize_hijack_rung: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); release v0.44.0 contains it.
[core-floor-probe] parse_wait_target: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] plan_checked_release_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); release v0.44.0 contains it.
[core-floor-probe] plan_pin_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); release v0.44.0 contains it.
[core-floor-probe] publication_parked_recheck_due: first appears in sase-core 542448a (feat(sase-core): anchor scanner rules, version blocks, add parked recheck); release v0.44.0 contains it.
[core-floor-probe] publication_protection_lookup_enforced: first appears in sase-core 542448a (feat(sase-core): anchor scanner rules, version blocks, add parked recheck); release v0.44.0 contains it.
[core-floor-probe] publication_protection_record_enforced: first appears in sase-core 542448a (feat(sase-core): anchor scanner rules, version blocks, add parked recheck); release v0.44.0 contains it.
[core-floor-probe] purge_agent_artifact_run_trash: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); release v0.44.0 contains it.
[core-floor-probe] quarantine_agent_artifact_runs: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); release v0.44.0 contains it.
[core-floor-probe] recovery_adoption_lock_filename: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); release v0.44.0 contains it.
[core-floor-probe] recovery_context_wire_schema_version: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); release v0.44.0 contains it.
[core-floor-probe] resolve_agent_run_state_observations: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); release v0.44.0 contains it.
[core-floor-probe] restore_agent_artifact_run_trash: first appears in sase-core 3974441 (feat(agent-artifact-run-trash): add journaled run quarantine); release v0.44.0 contains it.
[core-floor-probe] select_agent_run_state_discovery_window: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); release v0.44.0 contains it.
[core-floor-probe] select_agent_run_state_hoods: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); release v0.44.0 contains it.
[core-floor-probe] select_current_wait_turn: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] staged_handoff_receipt_transition_allowed: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); release v0.44.0 contains it.
[core-floor-probe] staged_reconcile_page: first appears in sase-core 16a3ed0 (feat(staged-handoff): add bounded discovery and automatic recovery policy); release v0.44.0 contains it.
[core-floor-probe] strip_hijack_launch_directives: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); release v0.44.0 contains it.
[core-floor-probe] validate_recovery_context: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); release v0.44.0 contains it.
[core-floor-probe] workspace_retention_wire_schema_version: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); release v0.44.0 contains it.
{"cache_hit": true, "capabilities": [{"commit": "65925ca", "name": "advance_agent_hijack_record", "release": "v0.44.0", "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "3974441", "name": "agent_artifact_run_trash_wire_schema_version", "release": "v0.44.0", "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "f1bbb4f", "name": "agent_hijack_continuation_prompt", "release": "v0.44.0", "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "f1bbb4f", "name": "agent_hijack_continuation_wire_schema_version", "release": "v0.44.0", "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "65925ca", "name": "agent_hijack_eligibility", "release": "v0.44.0", "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "f1bbb4f", "name": "agent_hijack_escalation_target", "release": "v0.44.0", "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "f1bbb4f", "name": "agent_hijack_escalation_wire_schema_version", "release": "v0.44.0", "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "65925ca", "name": "agent_hijack_status_for_done_marker", "release": "v0.44.0", "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "65925ca", "name": "agent_hijack_wire_schema_version", "release": "v0.44.0", "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "45c6a26", "name": "agent_prompt_select", "release": "v0.44.0", "subject": "feat(agent-prompts): add Rust-owned agent prompt selection policy"}, {"commit": "e60f3e1", "name": "bead_assess_epic_symbol_freshness", "release": "v0.44.0", "subject": "feat(bead): classify epic symbol freshness in Rust"}, {"commit": "e60f3e1", "name": "bead_parse_epic_symbol_entries", "release": "v0.44.0", "subject": "feat(bead): classify epic symbol freshness in Rust"}, {"commit": "6cd64a9", "name": "classify_instruction_readout", "release": "v0.44.0", "subject": "feat(core): add instruction handoff readout classifier"}, {"commit": "e9c0a99", "name": "decide_publication_rebase_conflict", "release": "v0.44.0", "subject": "feat(publication): add core rebase-conflict policy for agent publication"}, {"commit": "80338d6", "name": "decide_workspace_retention", "release": "v0.44.0", "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "154fe9e", "name": "decide_workspace_retention_dismissal", "release": "v0.44.0", "subject": "feat(stranded-work): retain held workspace as stranded unless live successor owns"}, {"commit": "f061f5f", "name": "default_publication_cleanup_timeout", "release": "v0.44.0", "subject": "fix(git-lock): enforce effective budget in backoff and aged-lock decisions"}, {"commit": "d7b00dd", "name": "effective_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "evaluate_recovery_decision", "release": "v0.44.0", "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "417d5c8", "name": "hijack_recovery_confirm", "release": "v0.44.0", "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "417d5c8", "name": "hijack_recovery_effective_target", "release": "v0.44.0", "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "417d5c8", "name": "hijack_recovery_execution_wire_schema_version", "release": "v0.44.0", "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "bbef1df", "name": "hijack_recovery_preview", "release": "v0.44.0", "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "bbef1df", "name": "hijack_recovery_preview_wire_schema_version", "release": "v0.44.0", "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "bbef1df", "name": "hijack_recovery_reconcile", "release": "v0.44.0", "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "bbef1df", "name": "hijack_recovery_reconcile_wire_schema_version", "release": "v0.44.0", "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "417d5c8", "name": "hijack_recovery_rollback", "release": "v0.44.0", "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "417d5c8", "name": "hijack_recovery_validate_execution", "release": "v0.44.0", "subject": "feat(agent-hijack): add execution validation and confirmation contract"}, {"commit": "3974441", "name": "list_agent_artifact_run_trash", "release": "v0.44.0", "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "f1bbb4f", "name": "normalize_hijack_rung", "release": "v0.44.0", "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "d7b00dd", "name": "parse_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "80338d6", "name": "plan_checked_release_workspace_claim_from_content", "release": "v0.44.0", "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "80338d6", "name": "plan_pin_workspace_claim_from_content", "release": "v0.44.0", "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "542448a", "name": "publication_parked_recheck_due", "release": "v0.44.0", "subject": "feat(sase-core): anchor scanner rules, version blocks, add parked recheck"}, {"commit": "542448a", "name": "publication_protection_lookup_enforced", "release": "v0.44.0", "subject": "feat(sase-core): anchor scanner rules, version blocks, add parked recheck"}, {"commit": "542448a", "name": "publication_protection_record_enforced", "release": "v0.44.0", "subject": "feat(sase-core): anchor scanner rules, version blocks, add parked recheck"}, {"commit": "3974441", "name": "purge_agent_artifact_run_trash", "release": "v0.44.0", "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "3974441", "name": "quarantine_agent_artifact_runs", "release": "v0.44.0", "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "73ec04a", "name": "recovery_adoption_lock_filename", "release": "v0.44.0", "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "73ec04a", "name": "recovery_context_wire_schema_version", "release": "v0.44.0", "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "dc5383f", "name": "resolve_agent_run_state_observations", "release": "v0.44.0", "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "3974441", "name": "restore_agent_artifact_run_trash", "release": "v0.44.0", "subject": "feat(agent-artifact-run-trash): add journaled run quarantine"}, {"commit": "dc5383f", "name": "select_agent_run_state_discovery_window", "release": "v0.44.0", "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "dc5383f", "name": "select_agent_run_state_hoods", "release": "v0.44.0", "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "d7b00dd", "name": "select_current_wait_turn", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "staged_handoff_receipt_transition_allowed", "release": "v0.44.0", "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "16a3ed0", "name": "staged_reconcile_page", "release": "v0.44.0", "subject": "feat(staged-handoff): add bounded discovery and automatic recovery policy"}, {"commit": "f1bbb4f", "name": "strip_hijack_launch_directives", "release": "v0.44.0", "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "73ec04a", "name": "validate_recovery_context", "release": "v0.44.0", "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "80338d6", "name": "workspace_retention_wire_schema_version", "release": "v0.44.0", "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}], "declared_floor": "0.43.2", "exit_code": 3, "message": "sase-core-rs==0.43.2 is missing 50 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
✓ docs (build + links)
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.44.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: src-data-asset); 5671 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: src-data-asset)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, platformdirs-4.12.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 2/2 workers
2 workers [60539 items]

.....................s.................................................. [  0%]
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
............................s........................................... [ 33%]
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
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
......................s................................................. [ 42%]
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
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
.....s.................................................................. [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
.........................................s.............................. [ 49%]
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
.....s.................................................................. [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
...............ssss..................................................... [ 65%]
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
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
.............................................................F.......... [ 70%]
....................................s................................... [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
.............................................s....ss.................... [ 71%]
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
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........s............................................................... [ 74%]
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
........................................................................ [ 77%]
........................................................................ [ 78%]
.....................s.................................................. [ 78%]
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
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
.....................................................F.................. [ 84%]
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
...........................................................              [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f961023ec40>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 497, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_ test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace _
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

self = <sase.macro.workflow_executor.WorkflowExecutor object at 0x7f9633812cf0>

    def execute(self) -> bool | WorkflowSuspended:
        """Execute all workflow steps sequentially.
    
        Steps marked with ``finally_=True`` run even when a prior step has
        failed.  Non-finally steps are skipped after a failure.  If no
        ``finally`` steps exist the behavior is identical to before.
    
        Returns:
            True/False for completed workflows, or a suspension signal for
            a staged review that is waiting for host adoption.
        """
        self._save_state()
    
        # Inject workflow environment variables before any steps run
        if self.workflow.environment:
            self._inject_environment()
    
        total_steps = len(self.workflow.steps)
        has_finally_steps = any(s.finally_ for s in self.workflow.steps)
    
        # Notify workflow start
        if self.output_handler:
            self.output_handler.on_workflow_start(
                self.workflow.name,
                dict(self.context),
                total_steps,
            )
    
        # Track failure info so finally steps can still run
        failure_exception: WorkflowExecutionError | None = None
        failure_returned_false: bool = False
        suspension: WorkflowSuspended | None = None
    
        for i, step in enumerate(self.workflow.steps):
            self.state.current_step_index = i
            step_state = self.state.steps[i]
            step_start_time = time.time()
    
            # Determine step type for display
            step_type = self._get_step_type(step)
    
            # After a failure, skip non-finally steps
            hit_failure = (
                failure_exception is not None
                or failure_returned_false
                or suspension is not None
            )
            if suspension is not None and not step.finally_:
                # Keep subsequent ordinary steps pending so the durable
                # workflow checkpoint resumes at the staged review.
                continue
            if hit_failure and not step.finally_:
                step_state.status = StepStatus.SKIPPED
                self.context[step.name] = {}
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_step_start(
                        step.name, step_type, i, total_steps
                    )
                    self.output_handler.on_step_skip(
                        step.name, reason="prior step failed"
                    )
                continue
    
            # Check if step should be skipped due to provided step input
            if step.name in self._step_inputs:
                step_state.status = StepStatus.SKIPPED
                step_state.output = self._step_inputs[step.name]
                self.context[step.name] = self._step_inputs[step.name]
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_step_start(
                        step.name,
                        step_type,
                        i,
                        total_steps,
                    )
                    self.output_handler.on_step_skip(
                        step.name, reason="step input provided"
                    )
                continue
    
            # Evaluate if: condition
            condition_result: bool | None = None
            if step.condition:
                condition_result = self._evaluate_condition(step.condition)
                if not condition_result:
                    step_state.status = StepStatus.SKIPPED
                    self.context[step.name] = {}
                    self._save_state()
                    # Notify step skipped
                    if self.output_handler:
                        self.output_handler.on_step_start(
                            step.name,
                            step_type,
                            i,
                            total_steps,
                            condition=step.condition,
                            condition_result=condition_result,
                        )
                        self.output_handler.on_step_skip(
                            step.name, reason="condition false"
                        )
                    continue
    
            step_state.status = StepStatus.IN_PROGRESS
            self._save_state()
    
            # Save initial "running" marker with step index for TUI display
            self._save_prompt_step_marker(
                step.name,
                step_state,
                step_type,
                step_index=i,
                hidden=step.hidden,
                output_types=self._get_output_types(i),
            )
    
            # Notify step start
            if self.output_handler:
                loop_info = self._get_loop_info(step)
                self.output_handler.on_step_start(
                    step.name,
                    step_type,
                    i,
                    total_steps,
                    condition=step.condition,
                    condition_result=condition_result,
                    loop_info=loop_info,
                )
    
            self._last_for_zero_iterations = False
    
            try:
                # Handle control flow constructs
                if step.for_loop and step.parallel_config:
                    success = self._execute_for_parallel_step(step, step_state)
                elif step.for_loop:
                    success = self._execute_for_step(step, step_state)
                elif step.repeat_config:
                    success = self._execute_repeat_step(step, step_state)
                elif step.while_config:
                    success = self._execute_while_step(step, step_state)
                elif step.parallel_config:
                    success = self._execute_parallel_step(step, step_state)
                elif step.is_agent_step():
>                   success = self._execute_prompt_step(step, step_state)
                              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_executor.py:348: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_executor_steps_prompt.py:102: in _execute_prompt_step
    prepared = self._prepare_prompt_step(step)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_executor_steps_prompt_prepare.py:121: in _prepare_prompt_step
    self._expand_embedded_workflows_in_prompt(early.prompt)
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_executor_steps_embedded_expand.py:234: in _expand_embedded_workflows_in_prompt
    success = self._execute_embedded_workflow_steps(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_executor_steps_embedded.py:177: in _execute_embedded_workflow_steps
    success = self._execute_python_step(step, temp_state)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <sase.macro.workflow_executor.WorkflowExecutor object at 0x7f9633812cf0>
step = WorkflowStep(name='resolve', agent=None, bash=None, python='from sase.scripts.agent_chat_from_name import main\nnames ..., repeat_config=None, while_config=None, parallel_config=None, join=None, finally_=False, artifact=None, on_error=None)
step_state = StepState(name='resolve', status=<StepStatus.IN_PROGRESS: 'in_progress'>, output=None, error=None, traceback=None, iteration_errors=None)

    def _execute_python_step(
        self,
        step: "WorkflowStep",
        step_state: StepState,
    ) -> bool:
        """Execute a python step.
    
        Args:
            step: The workflow step definition.
            step_state: The runtime state for this step.
    
        Returns:
            True if step succeeded, False if rejected by user.
        """
        if not step.python:
            raise WorkflowExecutionError(f"Python step '{step.name}' has no code")
    
        # Render code with Jinja2 context
        rendered_code = render_template(step.python, self.context)
    
        # Execute python code using the same interpreter.
        # stderr is streamed in real-time so long-running subprocesses
        # (e.g. a provider sync command) surface progress output as it happens,
        # while also being collected for error reporting on failure.
        try:
            proc = subprocess.Popen(
                [sys.executable, "-c", rendered_code],
                stdout=subprocess.PIPE,
                stderr=subprocess.PIPE,
                text=True,
                cwd=os.getcwd(),
            )
        except Exception as e:
            raise WorkflowExecutionError(
                f"Failed to execute python step '{step.name}': {e}"
            ) from e
    
        # Stream stderr to the terminal in real-time while collecting it.
        stderr_lines: list[str] = []
    
        def _stream_stderr() -> None:
            assert proc.stderr is not None
            for line in proc.stderr:
                sys.stderr.write(line)
                sys.stderr.flush()
                stderr_lines.append(line)
    
        stderr_thread = threading.Thread(target=_stream_stderr)
        stderr_thread.start()
    
        assert proc.stdout is not None
        stdout = proc.stdout.read()
        proc.wait()
        stderr_thread.join()
        captured_stderr = "".join(stderr_lines)
    
        if proc.returncode != 0:
            # Prefer stderr (contains tracebacks), fall back to stdout,
            # then to a bare exit-code message.
            error_msg = (
                captured_stderr.strip()
                or stdout.strip()
                or f"Exit code {proc.returncode}"
            )
>           raise WorkflowExecutionError(
                f"Python step '{step.name}' failed: {error_msg}"
            )
E           sase.macro.workflow_models.WorkflowExecutionError: Python step 'resolve' failed: Traceback (most recent call last):
E             File "<string>", line 4, in <module>
E               main(names or [], target=target)
E               ~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/scripts/_agent_chat_from_name_cli.py", line 21, in main
E               sources = resolve_agent_chat_sources(args.name, target=target)
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/scripts/_agent_chat_from_name_sources.py", line 100, in resolve_agent_chat_sources
E               raise RuntimeError("Invalid fork parents:\n- " + "\n- ".join(errors))
E           RuntimeError: Invalid fork parents:
E           - parent 1 (fakey-e2e): No agent with chat history found for: fakey-e2e

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_executor_steps_script.py:347: WorkflowExecutionError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-af46385f/pytest-of-bryan/pytest-0/popen-gw1/test_default_pipe_creates_agen0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f961620af20>

    def test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        harness = FakeyRetryHarness(
            tmp_path,
            monkeypatch,
            expose_to_agent_loader=True,
        )
        parent_hang = harness.barrier("parent")
        handle = _run_until_hang(
            harness,
            parent_hang,
            monkeypatch,
            [
                _hanging_success("parent waiting to pipe", parent_hang),
                successful_attempt("successor finished"),
            ],
        )
        try:
            assert _pipe(monkeypatch, harness.artifacts, "continue the work") == 0
            parent_hang.open()
>           result = handle.finish()
                     ^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/fakey/test_pipe_e2e.py:177: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/fakey/harness.py:96: in finish
    raise self._errors[0]
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/fakey/harness.py:483: in target
    results.append(self.run(prompt))
                   ^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/fakey/harness.py:473: in run
    return run_execution_loop(self.context(), f"%model:fakey-large\n{prompt}")
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/axe/run_agent_exec.py:267: in run_execution_loop
    return _run_execution_loop_bound(ctx, prompt)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/axe/run_agent_exec.py:361: in _run_execution_loop_bound
    result = execute_workflow(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_runner.py:563: in execute_workflow
    execution = executor.execute()
                ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <sase.macro.workflow_executor.WorkflowExecutor object at 0x7f9633812cf0>

    def execute(self) -> bool | WorkflowSuspended:
        """Execute all workflow steps sequentially.
    
        Steps marked with ``finally_=True`` run even when a prior step has
        failed.  Non-finally steps are skipped after a failure.  If no
        ``finally`` steps exist the behavior is identical to before.
    
        Returns:
            True/False for completed workflows, or a suspension signal for
            a staged review that is waiting for host adoption.
        """
        self._save_state()
    
        # Inject workflow environment variables before any steps run
        if self.workflow.environment:
            self._inject_environment()
    
        total_steps = len(self.workflow.steps)
        has_finally_steps = any(s.finally_ for s in self.workflow.steps)
    
        # Notify workflow start
        if self.output_handler:
            self.output_handler.on_workflow_start(
                self.workflow.name,
                dict(self.context),
                total_steps,
            )
    
        # Track failure info so finally steps can still run
        failure_exception: WorkflowExecutionError | None = None
        failure_returned_false: bool = False
        suspension: WorkflowSuspended | None = None
    
        for i, step in enumerate(self.workflow.steps):
            self.state.current_step_index = i
            step_state = self.state.steps[i]
            step_start_time = time.time()
    
            # Determine step type for display
            step_type = self._get_step_type(step)
    
            # After a failure, skip non-finally steps
            hit_failure = (
                failure_exception is not None
                or failure_returned_false
                or suspension is not None
            )
            if suspension is not None and not step.finally_:
                # Keep subsequent ordinary steps pending so the durable
                # workflow checkpoint resumes at the staged review.
                continue
            if hit_failure and not step.finally_:
                step_state.status = StepStatus.SKIPPED
                self.context[step.name] = {}
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_step_start(
                        step.name, step_type, i, total_steps
                    )
                    self.output_handler.on_step_skip(
                        step.name, reason="prior step failed"
                    )
                continue
    
            # Check if step should be skipped due to provided step input
            if step.name in self._step_inputs:
                step_state.status = StepStatus.SKIPPED
                step_state.output = self._step_inputs[step.name]
                self.context[step.name] = self._step_inputs[step.name]
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_step_start(
                        step.name,
                        step_type,
                        i,
                        total_steps,
                    )
                    self.output_handler.on_step_skip(
                        step.name, reason="step input provided"
                    )
                continue
    
            # Evaluate if: condition
            condition_result: bool | None = None
            if step.condition:
                condition_result = self._evaluate_condition(step.condition)
                if not condition_result:
                    step_state.status = StepStatus.SKIPPED
                    self.context[step.name] = {}
                    self._save_state()
                    # Notify step skipped
                    if self.output_handler:
                        self.output_handler.on_step_start(
                            step.name,
                            step_type,
                            i,
                            total_steps,
                            condition=step.condition,
                            condition_result=condition_result,
                        )
                        self.output_handler.on_step_skip(
                            step.name, reason="condition false"
                        )
                    continue
    
            step_state.status = StepStatus.IN_PROGRESS
            self._save_state()
    
            # Save initial "running" marker with step index for TUI display
            self._save_prompt_step_marker(
                step.name,
                step_state,
                step_type,
                step_index=i,
                hidden=step.hidden,
                output_types=self._get_output_types(i),
            )
    
            # Notify step start
            if self.output_handler:
                loop_info = self._get_loop_info(step)
                self.output_handler.on_step_start(
                    step.name,
                    step_type,
                    i,
                    total_steps,
                    condition=step.condition,
                    condition_result=condition_result,
                    loop_info=loop_info,
                )
    
            self._last_for_zero_iterations = False
    
            try:
                # Handle control flow constructs
                if step.for_loop and step.parallel_config:
                    success = self._execute_for_parallel_step(step, step_state)
                elif step.for_loop:
                    success = self._execute_for_step(step, step_state)
                elif step.repeat_config:
                    success = self._execute_repeat_step(step, step_state)
                elif step.while_config:
                    success = self._execute_while_step(step, step_state)
                elif step.parallel_config:
                    success = self._execute_parallel_step(step, step_state)
                elif step.is_agent_step():
                    success = self._execute_prompt_step(step, step_state)
                elif step.is_python_step():
                    success = self._execute_python_step(step, step_state)
                else:
                    success = self._execute_bash_step(step, step_state)
    
                if not success:
                    step_state.status = StepStatus.FAILED
                    self.state.status = "failed"
                    self._save_state()
                    if self.output_handler:
                        self.output_handler.on_workflow_failed(
                            f"Step '{step.name}' failed"
                        )
                    if not has_finally_steps:
                        return False
                    failure_returned_false = True
                    continue
    
                step_state.status = StepStatus.COMPLETED
                self._save_state()
                step_type = self._get_step_type(step)
                step_source = (
                    step.bash
                    if step_type == "bash"
                    else (step.python if step_type == "python" else None)
                )
                effective_hidden = step.hidden or (
                    step.for_loop is not None and self._last_for_zero_iterations
                )
                self._save_prompt_step_marker(
                    step.name,
                    step_state,
                    step_type,
                    step_source,
                    i,
                    hidden=effective_hidden,
                    output_types=self._get_output_types(i),
                )
    
                # Notify step complete
                if self.output_handler:
                    duration = time.time() - step_start_time
                    self.output_handler.on_step_complete(
                        step.name,
                        step_state.output,
                        duration=duration,
                    )
    
            except WorkflowSuspended as suspended:
                if suspension is not None:
                    failure_exception = WorkflowExecutionError(
                        "workflow attempted more than one staged HITL suspension"
                    )
                    continue
                suspension = suspended
                if suspended.step_index is None:
                    suspended.step_index = i
                step_state.status = StepStatus.WAITING_HITL
                self.state.status = "waiting_hitl"
                self._save_state()
                continue
            except Exception as e:
                import traceback
    
                step_state.status = StepStatus.FAILED
                step_state.error = f"{type(e).__qualname__}: {e}"
                step_state.traceback = traceback.format_exc()
                self.state.status = "failed"
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_workflow_failed(str(e))
                if not has_finally_steps:
>                   raise WorkflowExecutionError(
                        f"Step '{step.name}' failed: {e}"
                    ) from e
E                   sase.macro.workflow_models.WorkflowExecutionError: Step 'main' failed: Python step 'resolve' failed: Traceback (most recent call last):
E                     File "<string>", line 4, in <module>
E                       main(names or [], target=target)
E                       ~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E                     File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/scripts/_agent_chat_from_name_cli.py", line 21, in main
E                       sources = resolve_agent_chat_sources(args.name, target=target)
E                     File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/scripts/_agent_chat_from_name_sources.py", line 100, in resolve_agent_chat_sources
E                       raise RuntimeError("Invalid fork parents:\n- " + "\n- ".join(errors))
E                   RuntimeError: Invalid fork parents:
E                   - parent 1 (fakey-e2e): No agent with chat history found for: fakey-e2e

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_executor.py:421: WorkflowExecutionError
----------------------------- Captured stdout call -----------------------------
╭────── 🤖 Workflow-Tmp_261107_141526-Main [Fakey-Large] Agent - Prompt ───────╮
│                                                                              │
│  Exercise the pipe hand-off.                                                 │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭───────────────────────────────── sase pipe ──────────────────────────────────╮
│ This stages the handoff.                                                     │
│ The next agent session member starts after this turn completes with the      │
│ prompt below.                                                                │
│                                                                              │
│ from  fakey-e2e                                                              │
│ to    next numbered agent session member                                     │
│ model inherit                                                                │
│ fresh no (inherits this chat)                                                │
│ depth 1 / 8  (config: max_agent_pipe_chain)                                  │
│                                                                              │
│ prompt                                                                       │
│ continue the work                                                            │
╰──────────────────────────────────────────────────────────────────────────────╯
Staged pipe handoff. Nothing starts until this turn ends; finish with 
`/sase_final`.
parent waiting to pipe

✅ Waiting for Fakey completed in 00:00
----------------------------- Captured stderr call -----------------------------
/home/bryan/bin/bam: line 3: /var/tmp/sase-af46385f/pytest-of-bryan/pytest-0/popen-gw1/home-dn6gwebg/lib/bugyi.sh: No such file or directory
Traceback (most recent call last):
  File "<string>", line 4, in <module>
    main(names or [], target=target)
    ~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/scripts/_agent_chat_from_name_cli.py", line 21, in main
    sources = resolve_agent_chat_sources(args.name, target=target)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/scripts/_agent_chat_from_name_sources.py", line 100, in resolve_agent_chat_sources
    raise RuntimeError("Invalid fork parents:\n- " + "\n- ".join(errors))
RuntimeError: Invalid fork parents:
- parent 1 (fakey-e2e): No agent with chat history found for: fakey-e2e
------------------------------ Captured log call -------------------------------
WARNING  sase.macro.workflow_runner:workflow_runner.py:273 _flatten_anonymous_workflow: fast-path has_prompt_part branch returning None (workflow NOT flattened). prompt='#fork:fakey-e2e\ncontinue the work', first_ref='fork' (has_prompt_part=True), standalone_scan=no match, sase_prefix_keys=[], all_keys_count=62
___________________________ test_outputs_stay_valid ____________________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    @given(grids)
>   def test_outputs_stay_valid(g: PaneGrid) -> None:
                   ^^^
E   hypothesis.errors.FailedHealthCheck: Input generation is slow: Hypothesis only generated 6 valid inputs after 1.02 seconds.
E   
E         count | fraction |    slowest draws (seconds)
E     g |    6  |    100%  |      --      --      --      --   1.021
E   
E   This could be for a few reasons:
E   1. This strategy could be generating too much data per input. Try decreasing the amount of data generated, for example by decreasing the minimum size of collection strategies like st.lists().
E   2. Some other expensive computation could be running during input generation. For example, if @st.composite or st.data() is interspersed with an expensive computation, HealthCheck.too_slow is likely to trigger. If this computation is unrelated to input generation, move it elsewhere. Otherwise, try making it more efficient, or disable this health check if that is not possible.
E   
E   If you expect input generation to take this long, you can disable this health check with @settings(suppress_health_check=[HealthCheck.too_slow]). See https://hypothesis.readthedocs.io/en/latest/reference/api.html#hypothesis.HealthCheck for details.

tests/ace/tui/util/test_pane_grid_properties.py:121: FailedHealthCheck
---------------------------------- Hypothesis ----------------------------------
You can reproduce this failure by adding @seed(329690644762878107825480796621819465816) to this test, or by running pytest with --hypothesis-seed=329690644762878107825480796621819465816.
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=700930) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:200: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    memo[id(x)] = y
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:189: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    for k, j in zip(x, y):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:110: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def deepcopy(x, memo=None, _nil=[]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/collections/__init__.py:464: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    result = self._make(_map(kwds.pop, field_names, self))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
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

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_runner.py:477: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=700930) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=700930) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=700930) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=700930) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
63.29s call     tests/test_launch_request_staging.py::test_typed_plan_and_continuation_survive_adoption
61.62s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
57.86s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
56.88s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
33.73s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
31.27s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
29.91s call     tests/pager/test_app_goto.py::test_goto_backspace_on_empty_cancels
27.81s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
27.31s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
23.80s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
20.29s call     tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly
19.90s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
19.61s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
18.99s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
18.80s call     tests/test_global_state_leak_detector.py::test_report_only_mode_keeps_pytest_green_on_poison
18.55s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
17.56s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
15.72s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
15.48s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
15.38s call     tests/test_sdd_commit.py::test_commit_sdd_files_removes_persistent_index_lock_after_retry_exhausted
=========================== short test summary info ============================
FAILED tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace
FAILED tests/ace/tui/util/test_pane_grid_properties.py::test_outputs_stay_valid
==== 2 failed, 60521 passed, 17 skipped, 111 warnings in 5563.39s (1:32:43) ====
error: recipe `test-scoped` failed on line 672 with exit code 1
error: recipe `check` failed on line 946 with exit code 1
failed/1  6025467ms
triage test (scoped): 1 FLAKY 1 NEW
NEW test (scoped): FAILED tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace — recorded evidence; no owner
FLAKY test (scoped): FAILED tests/ace/tui/util/test_pane_grid_properties.py::test_outputs_stay_valid — recorded evidence; no owner
sase tool show 4d441ab8c25555d7b67af8dd266a2c4d -l
verdict: new_failures — 1 NEW, 1 FLAKY; exit 1

