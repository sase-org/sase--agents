# Chat History - ace-run (1e6--mon)

- **TIMESTAMP:** 2026-11-18 19:53:26 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** 1e6--mon

## Prompt

sase monitor start --command 'just check' --reason 'Verify before host completion'

## Response

sase tool run 9e7a2c93c629eec853e9c60905aa96af
[validate_sase_core_rs] installed sase-core-rs distribution version 0.43.3 is behind sase's sase-core-rs==0.44.2 floor in /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/pyproject.toml. Rebuild the extension: run `just install-venv`.
[core-source] linked sase-core source changed since the extension was built; flagging an extension rebuild.
[setup] Rebuilding sase_core_rs: linked sase-core source changed since the extension was built.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
# Capture the source identity after the checkout refresh above and before
# the build below. It is written to the venv only after a successful
# install (wheel-cache hit or `maturin develop` alike), so an edit made
# during the build still reads as stale on the next check.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/41dc308f48e382705724ca73b6f8f73062b0ed912db10fb9bad5db6f532411ef/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 2ms
Prepared 1 package in 0.77ms
Uninstalled 1 package in 1ms
Installed 1 package in 9ms
 - sase-core-rs==0.43.3 (from file:///home/bryan/.sase/cache/sase-core-artifacts/3c87dd78f30940f71b8cd3102f765466330633e04256f4366a52543cdca9327b/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.44.2 (from file:///home/bryan/.sase/cache/sase-core-artifacts/41dc308f48e382705724ca73b6f8f73062b0ed912db10fb9bad5db6f532411ef/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/319d6245cb57a42a3387a59e5c9f557ca00840e87586f05115e4aa3fea586f2d/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/sase-macro-lsp
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
✗ lint (mypy)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
.venv/bin/mypy
src/sase/axe/_chop_batch_recovery_observations.py:85: error: Argument 2 to "_name_in_blocked_roots" has incompatible type "Mapping[str, Any] | set[str]"; expected "Mapping[str, Any]"  [arg-type]
Found 1 error in 1 file (checked 6624 source files)
error: recipe `_lint-mypy` failed on line 348 with exit code 1
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (eager annotations)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (docs contract)
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.44.2 is missing 42 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] agent_artifact_list_wire_schema_version: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_decide: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] agent_hijack_eligibility_wire_schema_version: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] agent_hijack_latch_observe: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_latch_wire_schema_version: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_select_occupant: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] apply_chop_batch_transition: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] artifact_file_association_query: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); no release tag contains it yet.
[core-floor-probe] artifact_file_association_query_wire_schema_version: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); no release tag contains it yet.
[core-floor-probe] artifact_read_audit_query: first appears in sase-core 3992fce (feat(audit-query): query artifact-read audit logs); no release tag contains it yet.
[core-floor-probe] artifact_read_audit_query_wire_schema_version: first appears in sase-core 3992fce (feat(audit-query): query artifact-read audit logs); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query_wire_schema_version: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_view_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] chop_batch_generation_matches: first appears in sase-core b1a0363 (feat(axe-chop): add clan-scoped generation match and cancelled settlement); no release tag contains it yet.
[core-floor-probe] decide_local_command_trust: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] digest_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] filter_trusted_local_layer: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] hijack_latch_force_eligibility: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] hijack_latch_reconcile: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] local_command_trust_store_allow: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); no release tag contains it yet.
[core-floor-probe] local_command_trust_store_get: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); no release tag contains it yet.
[core-floor-probe] local_command_trust_store_revoke: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); no release tag contains it yet.
[core-floor-probe] local_command_trust_wire_schema_version: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] lookup_agent_artifacts: first appears in sase-core a4b1c84 (feat(agent-scan): add read-only indexed artifact identity lookups); no release tag contains it yet.
[core-floor-probe] lookup_named_dismissed_bundle: first appears in sase-core d201086 (feat(agent-scan): add bounded named lookup selection); no release tag contains it yet.
[core-floor-probe] memory_audit_query: first appears in sase-core c5e60d7 (feat(audit-query): add targeted memory audit query over JSONL); no release tag contains it yet.
[core-floor-probe] memory_audit_query_wire_schema_version: first appears in sase-core c5e60d7 (feat(audit-query): add targeted memory audit query over JSONL); no release tag contains it yet.
[core-floor-probe] plan_prompt_command_substitution: first appears in sase-core 1191f9a (feat: add prompt command-substitution source policy); no release tag contains it yet.
[core-floor-probe] project_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] prompt_command_substitution_wire_schema_version: first appears in sase-core 1191f9a (feat: add prompt command-substitution source policy); no release tag contains it yet.
[core-floor-probe] query_agent_artifact_index_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] reconcile_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] scan_agent_artifact_dirs_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] scan_agent_artifacts_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] select_agent_artifact_group: first appears in sase-core b9f33b0 (feat(agent-scan): select indexed session and clan generations); no release tag contains it yet.
[core-floor-probe] select_named_agent: first appears in sase-core d201086 (feat(agent-scan): add bounded named lookup selection); no release tag contains it yet.
[core-floor-probe] select_unscanned_coverage: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); no release tag contains it yet.
[core-floor-probe] suggest_unscanned_repair: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); no release tag contains it yet.
[core-floor-probe] summarize_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] unscanned_wire_schema_version: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); no release tag contains it yet.
[core-floor-probe] validate_chop_batch_manifest: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "8cedd45", "name": "agent_artifact_list_wire_schema_version", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "9940715", "name": "agent_hijack_decide", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "9940715", "name": "agent_hijack_eligibility_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_observe", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "9940715", "name": "agent_hijack_select_occupant", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "6cd9a0c", "name": "apply_chop_batch_transition", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "19b89ac", "name": "artifact_file_association_query", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "19b89ac", "name": "artifact_file_association_query_wire_schema_version", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "3992fce", "name": "artifact_read_audit_query", "release": null, "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "3992fce", "name": "artifact_read_audit_query_wire_schema_version", "release": null, "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "9f9341e", "name": "bead_touch_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "9f9341e", "name": "bead_touch_member_query_wire_schema_version", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "9f9341e", "name": "bead_view_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "b1a0363", "name": "chop_batch_generation_matches", "release": null, "subject": "feat(axe-chop): add clan-scoped generation match and cancelled settlement"}, {"commit": "e7647bf", "name": "decide_local_command_trust", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "digest_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "filter_trusted_local_layer", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e9b1cf0", "name": "hijack_latch_force_eligibility", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "hijack_latch_reconcile", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "233cb41", "name": "local_command_trust_store_allow", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_get", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_revoke", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "e7647bf", "name": "local_command_trust_wire_schema_version", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "a4b1c84", "name": "lookup_agent_artifacts", "release": null, "subject": "feat(agent-scan): add read-only indexed artifact identity lookups"}, {"commit": "d201086", "name": "lookup_named_dismissed_bundle", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "c5e60d7", "name": "memory_audit_query", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "c5e60d7", "name": "memory_audit_query_wire_schema_version", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "1191f9a", "name": "plan_prompt_command_substitution", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "e7647bf", "name": "project_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "1191f9a", "name": "prompt_command_substitution_wire_schema_version", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "8cedd45", "name": "query_agent_artifact_index_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "6cd9a0c", "name": "reconcile_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "8cedd45", "name": "scan_agent_artifact_dirs_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "8cedd45", "name": "scan_agent_artifacts_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "b9f33b0", "name": "select_agent_artifact_group", "release": null, "subject": "feat(agent-scan): select indexed session and clan generations"}, {"commit": "d201086", "name": "select_named_agent", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "7ac2081", "name": "select_unscanned_coverage", "release": null, "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "7ac2081", "name": "suggest_unscanned_repair", "release": null, "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "6cd9a0c", "name": "summarize_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "7ac2081", "name": "unscanned_wire_schema_version", "release": null, "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "6cd9a0c", "name": "validate_chop_batch_manifest", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}], "declared_floor": "0.44.2", "exit_code": 4, "message": "sase-core-rs==0.44.2 is missing 42 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 5810 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, hypothesis-6.167.1, platformdirs-4.12.2, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [62067 items]

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
........................................................................ [  4%]
........................................................................ [  4%]
.............................................s.......................... [  4%]
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
...............................s........................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
...........................s............................................ [ 11%]
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
............s........................................................... [ 22%]
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
....................................................................F... [ 34%]
........................................................................ [ 35%]
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
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
......................................s................................. [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
.......................................................s................ [ 50%]
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
........................................F............................... [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
.............................ss.ss...................................... [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
....................................s................................... [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
.....................................ss................................. [ 61%]
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
........................................................................ [ 62%]
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
........................................................................ [ 69%]
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
.................................................................s...... [ 77%]
........................................................................ [ 78%]
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
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
.....................................s.................................. [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
......F................................................................. [ 88%]
........................................................................ [ 89%]
.....................s.................................................. [ 89%]
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
...                                                                      [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_ test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent _
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-0/popen-gw5/test_synchronous_gate_answer_c0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe09a1475b0>

    def test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The default (non-detached) answer route claims real runner-slot
        capacity before its command executes, and releases it like any agent --
        without disturbing an unrelated owner's already-live claim.
        """
        harness = _RunnerSlotFakeyHarness(tmp_path, monkeypatch, cap=2)
        unrelated = harness.create_agent(0, name="unrelated", queue_weight=1.0)
        harness.start(unrelated)
        harness.wait_started(unrelated)
        unrelated_owner_key = harness.agent_meta(unrelated)["runner_claim_owner_key"]
    
        gate_started = harness.root / "signals" / "answer.started"
        gate_release = harness.root / "signals" / "answer.release"
        bundle_path, gate_dir = make_blocking_gate(
            request_id="answer-1",
            member_name="answer--gate",
            lane="answer",
            started=gate_started,
            release=gate_release,
            queue_weight=1.0,
            queue_weight_explicit=True,
        )
    
        errors: list[BaseException] = []
    
        def run_gate() -> None:
            try:
                callbacks = bind_gate_turn_execution_callbacks(gate_dir)
                execute_gate_selection(
                    bundle_path, ["run"], {}, source="test", **callbacks.as_kwargs()
                )
            except BaseException as exc:  # noqa: BLE001 - surfaced via `errors`
                errors.append(exc)
    
        thread = threading.Thread(target=run_gate, daemon=True)
        thread.start()
        _wait_for_condition(gate_started.exists, "gate command to start")
    
        gate_meta = json.loads((Path(gate_dir) / "agent_meta.json").read_text())
        assert gate_meta["gate_state"] == "settling"
        gate_owner_key = gate_meta.get("runner_claim_owner_key")
        assert isinstance(gate_owner_key, str) and gate_owner_key
        assert gate_owner_key != unrelated_owner_key
        assert gate_meta["queue_weight"] == 1.0
    
        competitor = harness.create_agent(1, name="competitor", queue_weight=1.0)
        harness.start(competitor)
        harness.wait_parked(competitor)
    
        assert (
            harness.agent_meta(unrelated)["runner_claim_owner_key"] == unrelated_owner_key
        )
    
        gate_release.parent.mkdir(parents=True, exist_ok=True)
        gate_release.touch()
        thread.join(_WAIT_TIMEOUT)
>       assert not thread.is_alive()
E       assert not True
E        +  where True = is_alive()
E        +    where is_alive = <Thread(Thread-43 (run_gate), started daemon 140602782947008)>.is_alive

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/fakey/test_gate_capacity_custom_e2e.py:265: AssertionError
----------------------------- Captured stdout call -----------------------------
Waiting for a runner slot
______________ test_refresh_prior_pos_lands_on_visually_below_row ______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

    def test_refresh_prior_pos_lands_on_visually_below_row() -> None:
        """Step 3: a removed middle row falls back to the visible neighbor."""
        zeta = _visible_order_agent(project="zeta", cl="z1", name="z1")
        alpha = _visible_order_agent(project="alpha", cl="a1", name="a1")
        beta = _visible_order_agent(project="beta", cl="b1", name="b1")
        agents = [zeta, alpha, beta]
        # Visible order is [alpha, beta, zeta]; select beta (middle).
        app = _RefreshFallbackApp(agents, current_idx=2)
        prior_pos = app._capture_focused_visible_pos()
        assert prior_pos == 1
    
        removed_identity = beta.identity
        app._agents = [zeta, alpha]
        app._agents_with_children = [zeta, alpha]
        app._invalidate_agent_panel_cache()
    
        app._finalize_agent_list(
            True,
            removed_identity,
            save_unfiltered=False,
            fold_filter_already_applied=True,
            prior_pos=prior_pos,
            previous_agents=agents,
            refresh_display=False,
        )
    
        # Visually below beta was zeta; the global-index clamp would land on alpha.
>       assert app._agents[app.current_idx].agent_name == "z1"
E       AssertionError: assert 'a1' == 'z1'
E         
E         - z1
E         + a1

tests/ace/tui/test_agents_panel_focus_follows_selection.py:451: AssertionError
__ test_older_generation_does_not_cancel_a_batch_without_recorded_generation ___
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

isolated_home = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-0/popen-gw4/test_older_generation_does_not0/.sase')

    def test_older_generation_does_not_cancel_a_batch_without_recorded_generation(
        isolated_home: Path,
    ) -> None:
        manifest = _manifest("run-new-clan", None)
        manifest["created_at"] = "2026-11-18T12:00:00+00:00"
        manifest["members"][0]["clan"] = "reused-clan"
        chop_batch_store.create_chop_batch("docs", "refresh", manifest)
    
        cancelled = recovery.cancel_chop_batches_for_clan(
            "reused-clan",
            generation="20261117_120000",
            reason="explicit TUI clan kill of the old generation",
        )
    
>       assert cancelled == []
E       AssertionError: assert [{'routine': ...un-new-clan'}] == []
E         
E         Left contains one more item: {'routine': 'docs', 'job': 'refresh', 'batch_id': 'run-new-clan'}
E         Use -v to get more diff

tests/axe/test_axe_chop_batch_recovery.py:181: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/macro/workflow_runner_execute.py:254: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/macro/workflow_runner_flatten.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/macro/workflow_runner_flatten.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = flatten_anonymous_workflow(workflow)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_lookup.py::test_queued_explicit_open_drains_on_idle_tick
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/asyncio/events.py:41: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    def __init__(self, callback, args, loop, context=None):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/config/loading.py:92: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=167244) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=167440) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/config/loading.py:92: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object _record_history_async.<locals>._record at 0x7fdb62b6a9d0>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorHostFinalizer::test_genuine_provider_500_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorHostFinalizer::test_genuine_provider_500_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_run_policies.py::test_proc_submit_captures_confirm_flags
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=167149) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=167131) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=167440) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/_agent_archive_column_helpers.py:55: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    row.update(extra)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/axe/test_axe_chop_batch_store.py::test_stale_and_live_ownership
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/axe/test_axe_chop_batch_store.py:220: DeprecationWarning: This process (pid=167131) is multi-threaded, use of fork() may lead to deadlocks in the child.
    pid = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=167131) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
131.11s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
87.66s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
66.05s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
65.08s call     tests/test_launch_request_staging.py::test_typed_plan_and_continuation_survive_adoption
63.36s call     tests/continuation/test_launch_local_capture_chain.py::test_twenty_launch_agent_monitor_cycles_keep_only_local_authored_text
62.68s call     tests/test_ace_testing.py::test_ace_page_screen
58.64s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
54.77s call     tests/llm_provider/test_usage_refresh_runner.py::test_runner_reports_providers_that_miss_the_batch_deadline
49.35s call     tests/fakey/test_agent_hijack_canary.py::test_monitor_hijack_continue_same_workspace
46.04s call     tests/test_bead/test_attachment_lifecycle.py::test_prune_cli_dry_run_then_evicts
46.02s call     tests/test_format_with_prettier.py::test_agent_prompt_formatter_preserves_literals_against_rewriting_prettier[Snake_case_name and _leading and trailing_\n]
39.68s call     tests/test_capacity_snapshot_parity.py::test_project_filter_preserves_shared_global_queue_numbers
37.95s call     tests/fakey/test_agent_hijack_canary.py::test_finalizing_latch_suppresses_staged_pipe_then_continues_same_workspace
35.34s call     tests/test_procs_service_settlement.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
35.03s call     tests/fakey/test_agent_hijack_canary.py::test_session_hijack_chooses_running_member_one
33.82s call     tests/monitor/test_monitor_start_ack.py::test_startup_sigterm_settles_stopped_without_running_command
33.68s call     tests/fakey/test_gate_capacity_custom_e2e.py::test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent
32.30s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
31.18s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
30.79s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
=========================== short test summary info ============================
FAILED tests/fakey/test_gate_capacity_custom_e2e.py::test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent
FAILED tests/ace/tui/test_agents_panel_focus_follows_selection.py::test_refresh_prior_pos_lands_on_visually_below_row
FAILED tests/axe/test_axe_chop_batch_recovery.py::test_older_generation_does_not_cancel_a_batch_without_recorded_generation
==== 3 failed, 62048 passed, 17 skipped, 161 warnings in 1119.49s (0:18:39) ====
error: recipe `test-scoped` failed on line 696 with exit code 1
error: recipe `check` failed on line 977 with exit code 1
failed  exit=1  duration=1466188ms
unattrib  29.6s
triage lint (mypy): 1 KNOWN continued
triage test (scoped): 1 KNOWN 2 NEW stopped
NEW test (scoped): FAILED tests/axe/test_axe_chop_batch_recovery.py::test_older_generation_does_not_cancel_a_batch_without_recorded_generation — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/test_agents_panel_focus_follows_selection.py::test_refresh_prior_pos_lands_on_visually_below_row — recorded evidence; no owner
KNOWN lint (mypy): src/sase/axe/_chop_batch_recovery_observations.py:85: error: Argument 2 to "_name_in_blocked_roots" has incompatible type "Mapping[str, Any] | set[str]"; expected "Mapping[str, Any]" [arg-type] — witness 03877e5f68acf5cd3ed2ff1147d15343; no owner
KNOWN test (scoped): FAILED tests/fakey/test_gate_capacity_custom_e2e.py::test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent — witness 5e0a93f77c4e2b8dc8d6c2d347b0980f; no owner
verdict: new_failures — 2 NEW, 2 KNOWN; exit 1

