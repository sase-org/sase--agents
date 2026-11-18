# Chat History - ace-run (sase-1tc.3.1.2--mon-2)

- **TIMESTAMP:** 2026-11-18 00:06:07 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1tc.3.1.2--mon-2

## Prompt

sase monitor start --command 'just check' --reason 'Verify ordinary chop launch journal before host completion'

## Response

sase tool run e6954566eede706dd8b38809f84baf7e
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.44.2 is missing 37 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] agent_artifact_list_wire_schema_version: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_decide: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] agent_hijack_eligibility_wire_schema_version: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] agent_hijack_latch_observe: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_latch_wire_schema_version: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_select_occupant: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] apply_chop_batch_transition: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] artifact_file_association_query: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); no release tag contains it yet.
[core-floor-probe] artifact_file_association_query_wire_schema_version: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query_wire_schema_version: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_view_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
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
[core-floor-probe] scan_agent_artifact_dir_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] scan_agent_artifact_dirs_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] scan_agent_artifacts_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] select_agent_artifact_group: first appears in sase-core b9f33b0 (feat(agent-scan): select indexed session and clan generations); no release tag contains it yet.
[core-floor-probe] select_named_agent: first appears in sase-core d201086 (feat(agent-scan): add bounded named lookup selection); no release tag contains it yet.
[core-floor-probe] summarize_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] validate_chop_batch_manifest: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "8cedd45", "name": "agent_artifact_list_wire_schema_version", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "9940715", "name": "agent_hijack_decide", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "9940715", "name": "agent_hijack_eligibility_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_observe", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "9940715", "name": "agent_hijack_select_occupant", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "6cd9a0c", "name": "apply_chop_batch_transition", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "19b89ac", "name": "artifact_file_association_query", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "19b89ac", "name": "artifact_file_association_query_wire_schema_version", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "9f9341e", "name": "bead_touch_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "9f9341e", "name": "bead_touch_member_query_wire_schema_version", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "9f9341e", "name": "bead_view_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "e7647bf", "name": "decide_local_command_trust", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "digest_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "filter_trusted_local_layer", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e9b1cf0", "name": "hijack_latch_force_eligibility", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "hijack_latch_reconcile", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "233cb41", "name": "local_command_trust_store_allow", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_get", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_revoke", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "e7647bf", "name": "local_command_trust_wire_schema_version", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "a4b1c84", "name": "lookup_agent_artifacts", "release": null, "subject": "feat(agent-scan): add read-only indexed artifact identity lookups"}, {"commit": "d201086", "name": "lookup_named_dismissed_bundle", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "c5e60d7", "name": "memory_audit_query", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "c5e60d7", "name": "memory_audit_query_wire_schema_version", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "1191f9a", "name": "plan_prompt_command_substitution", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "e7647bf", "name": "project_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "1191f9a", "name": "prompt_command_substitution_wire_schema_version", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "8cedd45", "name": "query_agent_artifact_index_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "6cd9a0c", "name": "reconcile_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "8cedd45", "name": "scan_agent_artifact_dir_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "8cedd45", "name": "scan_agent_artifact_dirs_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "8cedd45", "name": "scan_agent_artifacts_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "b9f33b0", "name": "select_agent_artifact_group", "release": null, "subject": "feat(agent-scan): select indexed session and clan generations"}, {"commit": "d201086", "name": "select_named_agent", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "6cd9a0c", "name": "summarize_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "6cd9a0c", "name": "validate_chop_batch_manifest", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}], "declared_floor": "0.44.2", "exit_code": 4, "message": "sase-core-rs==0.44.2 is missing 37 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
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
test selection escalated to the full suite (rules: core-identity-changed, justfile); 5782 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed, justfile)
Waiting for a SASE pytest worker-token grant of 4-8 worker tokens; 0 tokens were available below the floor. Current holders: 9 tokens: pid 173672, grant 9, age 1417s, heartbeat 2s, argv 'tools/run_pytest scoped'; 8 tokens: pid 4065705, grant 8, age 1705s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-8 worker tokens; 0 tokens were available below the floor. Current holders: 9 tokens: pid 173672, grant 9, age 1447s, heartbeat 2s, argv 'tools/run_pytest scoped'; 8 tokens: pid 4065705, grant 8, age 1735s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-8 worker tokens; 0 tokens were available below the floor. Current holders: 9 tokens: pid 173672, grant 9, age 1478s, heartbeat 1s, argv 'tools/run_pytest scoped'; 8 tokens: pid 4065705, grant 8, age 1765s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-8 worker tokens; 0 tokens were available below the floor. Current holders: 9 tokens: pid 173672, grant 9, age 1508s, heartbeat 1s, argv 'tools/run_pytest scoped'; 8 tokens: pid 4065705, grant 8, age 1795s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-8 worker tokens; 0 tokens were available below the floor. Current holders: 9 tokens: pid 173672, grant 9, age 1538s, heartbeat 1s, argv 'tools/run_pytest scoped'; 8 tokens: pid 4065705, grant 8, age 1825s, heartbeat 21s, argv 'tools/run_pytest scoped'
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, platformdirs-4.14.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 8/8 workers
8 workers [61877 items]

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
...................................s.................................... [  4%]
......................ss................................................ [  4%]
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
..................................F..............F....F................. [ 14%]
......F................................................................. [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
...........................F...................F.....F.................. [ 15%]
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
........................................................................ [ 20%]
............................................................s........... [ 20%]
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
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
..............s......................................................... [ 23%]
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
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
.........................................s.............................. [ 31%]
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
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
......................................................................F. [ 34%]
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
..F..................................................................... [ 42%]
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
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
.............F.......................................................... [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
...................................................s.................... [ 52%]
...............F......................................F...F......F...... [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
...F....F.......F....................................................... [ 53%]
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
................................................s....................... [ 54%]
........................................................................ [ 55%]
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
....................................s................................... [ 57%]
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
........................................................................ [ 60%]
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
.....................................ssss............................... [ 64%]
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
..........................................................s............. [ 72%]
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
s....................................................................... [ 74%]
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
........................................................................ [ 89%]
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
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
..................................................................F..... [ 93%]
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
.................s...................................................... [ 94%]
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
............................................s........................... [ 96%]
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
........................................................................ [ 99%]
.............................                                            [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
__________________ test_single_slot_swarm_records_invocation ___________________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/test_single_slot_swarm_records0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa8e54bac80>

    def test_single_slot_swarm_records_invocation(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """A swarm that reduces to one slot records the trigger, not the member."""
        from tests._macro_swarm_helpers import patch_catalog, xp
    
        history_file = _history_file(tmp_path)
        monkeypatch.delenv("SASE_AGENT", raising=False)
        _isolated_successful_cwd_launch(monkeypatch)
        # A `---` body makes this a swarm; the empty segments drop out, so it
        # reduces to one slot whose member text must not be recorded.
        swarm = {
            "solo": xp(
                "solo",
                "---\nplease summarize these project notes for me now\n---\n",
            )
        }
        with (
            patch("sase.history.prompt_store._PROMPT_HISTORY_FILE", history_file),
            patch_catalog(swarm),
        ):
>           results = launch_agents_from_cwd("#solo", origin="typed")
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/history/test_prompt_canonical_text.py:131: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/agent/launch_cwd.py:44: in launch_agents_from_cwd
    return launch_agents_from_cwd_impl(
src/sase/agent/launch_cwd_agents.py:318: in launch_agents_from_cwd_impl
    return launch_single_agent(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = 'please summarize these project notes for me now'
project_file = '/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/home-t5tzul2u/.sase/projects/home/home.sase'
project_name = 'home', is_home_mode = True, workspace_num = 0
extra_env = {'SASE_LAUNCH_SUBMITTED_AT': '2026-11-18T04:43:10.759589Z', 'SASE_PROMPT_ORIGIN': 'typed', 'SASE_PROMPT_AUTHORSHIP': 'human', 'SASE_PROMPT_SOURCE_SURFACE': 'unknown', ...}
timestamp = 'ts-0'
recorder = LaunchHistoryRecorder(text='#solo', origin='typed', allow_short=True)
before_agent_spawn = None, on_agent_launch_recorded = None
pause_requested_fn = None, on_launch_paused = None

    def launch_single_agent(
        query: str,
        *,
        project_file: str,
        project_name: str,
        is_home_mode: bool,
        workspace_num: int | None,
        extra_env: dict[str, str] | None,
        timestamp: str | None,
        recorder: LaunchHistoryRecorder,
        before_agent_spawn: Callable[[int, int, object, object | None], None] | None = None,
        on_agent_launch_recorded: Callable[[int, int, object, object | None], None]
        | None = None,
        pause_requested_fn: Callable[[], bool] | None = None,
        on_launch_paused: Callable[[], None] | None = None,
    ) -> list[AgentLaunchResult]:
        """Resolve the VCS/workspace context for one prompt and spawn it.
    
        History records the recorder's submitted invocation text, which may
        differ from *query* when a swarm expanded to this single slot.
        """
        from sase.ace.tui.actions.agent_workflow._ref_resolution import (
            resolve_ref_from_prompt,
        )
        from sase.workspace_provider import get_workflow_names
        from sase.macro.directives import has_deferred_start_directive
    
        has_wait = has_deferred_start_directive(query)
        vcs_ref: tuple[str, str] | None = None
        workspace_dir: str | None = None
    
        # Resolve VCS metadata without reserving a numbered workspace for normal
        # VCS refs. The executor claims the final slot atomically just before
        # spawn; deferred %wait launches carry a workspace here.
        for wf_name in get_workflow_names():
            resolved = resolve_ref_from_prompt(
                query,
                wf_name,
                skip_workspace=True,
            )
            if resolved is not None:
                project_file, project_name, resolved_dir, ws_num, ref_value = resolved
                if has_wait:
                    workspace_dir = resolved_dir
                    workspace_num = ws_num
                else:
                    workspace_dir = None
                    workspace_num = None
                vcs_ref = (wf_name, ref_value)
                is_home_mode = False
                break
    
        if vcs_ref is None:
            known_ref = resolve_known_project_vcs_launch_ref(query)
            if known_ref is not None:
                project_file = known_ref.project_file
                project_name = known_ref.ref
                workspace_dir = known_ref.workspace_dir if has_wait else None
                workspace_num = 0
                vcs_ref = (known_ref.workflow_type, known_ref.ref)
                is_home_mode = False
    
        if vcs_ref is None and not is_home_mode:
            from sase.workspace_provider import get_ref_patterns
    
            for wf_name, pattern in get_ref_patterns().items():
                match = pattern.search(query)
                if match is not None:
                    ref_value = match.group(1) or match.group(2)
                    if ref_value:
                        vcs_ref = (wf_name, ref_value)
                        break
    
        # If no workspace ref is found and we're not already in home mode, fall
        # back to direct home mode. Bare prompts normally gain the default
        # workspace ref before this point; this branch covers disabled/missing
        # workspace providers and explicit non-workspace contexts.
        if vcs_ref is None and not is_home_mode:
            from sase.ace.patch.project_spec_path import preferred_project_spec_path
    
            is_home_mode = True
            project_name = "home"
            home_dir = str(sase_projects_dir() / "home")
            project_file = preferred_project_spec_path(home_dir, "home")
    
        # --- Resolve fixed workspace contexts ---
        if timestamp is None:
            from sase.core.agent_launch_facade import reserve_launch_timestamp_batch
    
            timestamp = reserve_launch_timestamp_batch(1)[0]
    
        if not workspace_dir:
            if is_home_mode:
                workspace_dir = os.path.expanduser("~")
                workspace_num = 0
            elif has_wait:
                # Deferred workspace: use main workspace dir as CWD during wait
                from sase.running_field import get_workspace_directory
    
                workspace_num = 0
                workspace_dir = get_workspace_directory(project_name, 1)
    
        # --- Determine display name / sort key ---
        if vcs_ref is not None:
            cl_name = vcs_ref[1]
            history_sort_key = vcs_ref[1]
            from sase.vcs_provider import VCS_DEFAULT_REVISION
    
            update_target = VCS_DEFAULT_REVISION
        else:
            cl_name = project_name
            history_sort_key = ""
            update_target = ""
    
        try:
            from sase.agent.launch_validation import validate_launch_name_requests
    
            validate_launch_name_requests(
                [query],
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
            )
        except RuntimeError:
            recorder.record_failed()
            raise
    
        # --- Save prompt to history ---
        # Records the submitted invocation, not the expanded single slot: a
        # swarm that reduces to one slot must not record that member's text.
        recorder.record_submitted()
    
        from sase.agent.launch_executor import LaunchExecutionContext, execute_launch_plan
        from sase.core.agent_launch_facade import plan_fake_fanout
    
        extra_env, name_allocator = plan_single_agent_name(
            query,
            extra_env,
            project_name=project_name,
            timestamp=timestamp,
        )
    
        fixed_workspace = is_home_mode or has_wait
        try:
            execution = execute_launch_plan(
                plan_fake_fanout("single", [query]),
                LaunchExecutionContext(
                    cl_name=cl_name,
                    project_file=project_file,
                    project_name=project_name,
                    update_target=update_target,
                    history_sort_key=history_sort_key,
                    is_home_mode=is_home_mode,
                    vcs_ref=vcs_ref,
                    deferred_workspace=has_wait,
                    workspace_num=workspace_num if fixed_workspace else None,
                    workspace_dir=workspace_dir if fixed_workspace else None,
                    use_preallocated_workspace=False,
                ),
                extra_env=extra_env,
                base_timestamp=timestamp,
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
                before_spawn=(
                    None
                    if before_agent_spawn is None
                    else lambda slot, request: before_agent_spawn(
                        0, int(slot.slot_index), request, None
                    )
                ),
                on_slot_executed=(
                    None
                    if on_agent_launch_recorded is None
                    else lambda record: on_agent_launch_recorded(
                        0, int(record.slot.slot_index), record, None
                    )
                ),
                stop_requested=pause_requested_fn,
            )
        except Exception:
            if name_allocator is not None:
                name_allocator.release_uncommitted_template_reservations()
            recorder.record_failed()
            raise
>       if execution.paused:
           ^^^^^^^^^^^^^^^^
E       AttributeError: 'types.SimpleNamespace' object has no attribute 'paused'

src/sase/agent/launch_cwd_single.py:203: AttributeError
_______________ test_repeat_records_parent_once_and_no_slot_rows _______________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/test_repeat_records_parent_onc0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa8e53192b0>

    def test_repeat_records_parent_once_and_no_slot_rows(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """``%r:3`` records the parent once; generated slots write nothing."""
        history_file = _history_file(tmp_path)
        monkeypatch.delenv("SASE_AGENT", raising=False)
        _isolated_successful_cwd_launch(monkeypatch)
        parent = "please review the project documentation thoroughly now %r:3"
        with patch("sase.history.prompt_store._PROMPT_HISTORY_FILE", history_file):
>           results = launch_agents_from_cwd(parent, origin="typed")
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/history/test_prompt_canonical_text.py:148: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/agent/launch_cwd.py:44: in launch_agents_from_cwd
    return launch_agents_from_cwd_impl(
src/sase/agent/launch_cwd_agents.py:294: in launch_agents_from_cwd_impl
    repeat_results = launch_repeat_branch_if_applicable(
src/sase/agent/launch_cwd_fanout.py:198: in launch_repeat_branch_if_applicable
    _spawn_repeat_slot(spec)
src/sase/agent/launch_cwd_fanout.py:189: in _spawn_repeat_slot
    recursive_launch(
src/sase/agent/launch_cwd.py:44: in launch_agents_from_cwd
    return launch_agents_from_cwd_impl(
src/sase/agent/launch_cwd_agents.py:318: in launch_agents_from_cwd_impl
    return launch_single_agent(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = '%i:0.1\nplease review the project documentation thoroughly now'
project_file = '/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/home-wknan2i4/.sase/projects/home/home.sase'
project_name = 'home', is_home_mode = True, workspace_num = 0
extra_env = {'SASE_REPEAT_NAME': '0.1', 'SASE_REPEAT_ITERATION': '1', 'SASE_REPEAT_TOTAL': '3', 'SASE_LAUNCH_SUBMITTED_AT': '2026-11-18T04:43:11.462308Z', ...}
timestamp = 'ts-0'
recorder = LaunchHistoryRecorder(text='%i:0.1\nplease review the project documentation thoroughly now ', origin='generated', allow_short=False)
before_agent_spawn = None, on_agent_launch_recorded = None
pause_requested_fn = None, on_launch_paused = None

    def launch_single_agent(
        query: str,
        *,
        project_file: str,
        project_name: str,
        is_home_mode: bool,
        workspace_num: int | None,
        extra_env: dict[str, str] | None,
        timestamp: str | None,
        recorder: LaunchHistoryRecorder,
        before_agent_spawn: Callable[[int, int, object, object | None], None] | None = None,
        on_agent_launch_recorded: Callable[[int, int, object, object | None], None]
        | None = None,
        pause_requested_fn: Callable[[], bool] | None = None,
        on_launch_paused: Callable[[], None] | None = None,
    ) -> list[AgentLaunchResult]:
        """Resolve the VCS/workspace context for one prompt and spawn it.
    
        History records the recorder's submitted invocation text, which may
        differ from *query* when a swarm expanded to this single slot.
        """
        from sase.ace.tui.actions.agent_workflow._ref_resolution import (
            resolve_ref_from_prompt,
        )
        from sase.workspace_provider import get_workflow_names
        from sase.macro.directives import has_deferred_start_directive
    
        has_wait = has_deferred_start_directive(query)
        vcs_ref: tuple[str, str] | None = None
        workspace_dir: str | None = None
    
        # Resolve VCS metadata without reserving a numbered workspace for normal
        # VCS refs. The executor claims the final slot atomically just before
        # spawn; deferred %wait launches carry a workspace here.
        for wf_name in get_workflow_names():
            resolved = resolve_ref_from_prompt(
                query,
                wf_name,
                skip_workspace=True,
            )
            if resolved is not None:
                project_file, project_name, resolved_dir, ws_num, ref_value = resolved
                if has_wait:
                    workspace_dir = resolved_dir
                    workspace_num = ws_num
                else:
                    workspace_dir = None
                    workspace_num = None
                vcs_ref = (wf_name, ref_value)
                is_home_mode = False
                break
    
        if vcs_ref is None:
            known_ref = resolve_known_project_vcs_launch_ref(query)
            if known_ref is not None:
                project_file = known_ref.project_file
                project_name = known_ref.ref
                workspace_dir = known_ref.workspace_dir if has_wait else None
                workspace_num = 0
                vcs_ref = (known_ref.workflow_type, known_ref.ref)
                is_home_mode = False
    
        if vcs_ref is None and not is_home_mode:
            from sase.workspace_provider import get_ref_patterns
    
            for wf_name, pattern in get_ref_patterns().items():
                match = pattern.search(query)
                if match is not None:
                    ref_value = match.group(1) or match.group(2)
                    if ref_value:
                        vcs_ref = (wf_name, ref_value)
                        break
    
        # If no workspace ref is found and we're not already in home mode, fall
        # back to direct home mode. Bare prompts normally gain the default
        # workspace ref before this point; this branch covers disabled/missing
        # workspace providers and explicit non-workspace contexts.
        if vcs_ref is None and not is_home_mode:
            from sase.ace.patch.project_spec_path import preferred_project_spec_path
    
            is_home_mode = True
            project_name = "home"
            home_dir = str(sase_projects_dir() / "home")
            project_file = preferred_project_spec_path(home_dir, "home")
    
        # --- Resolve fixed workspace contexts ---
        if timestamp is None:
            from sase.core.agent_launch_facade import reserve_launch_timestamp_batch
    
            timestamp = reserve_launch_timestamp_batch(1)[0]
    
        if not workspace_dir:
            if is_home_mode:
                workspace_dir = os.path.expanduser("~")
                workspace_num = 0
            elif has_wait:
                # Deferred workspace: use main workspace dir as CWD during wait
                from sase.running_field import get_workspace_directory
    
                workspace_num = 0
                workspace_dir = get_workspace_directory(project_name, 1)
    
        # --- Determine display name / sort key ---
        if vcs_ref is not None:
            cl_name = vcs_ref[1]
            history_sort_key = vcs_ref[1]
            from sase.vcs_provider import VCS_DEFAULT_REVISION
    
            update_target = VCS_DEFAULT_REVISION
        else:
            cl_name = project_name
            history_sort_key = ""
            update_target = ""
    
        try:
            from sase.agent.launch_validation import validate_launch_name_requests
    
            validate_launch_name_requests(
                [query],
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
            )
        except RuntimeError:
            recorder.record_failed()
            raise
    
        # --- Save prompt to history ---
        # Records the submitted invocation, not the expanded single slot: a
        # swarm that reduces to one slot must not record that member's text.
        recorder.record_submitted()
    
        from sase.agent.launch_executor import LaunchExecutionContext, execute_launch_plan
        from sase.core.agent_launch_facade import plan_fake_fanout
    
        extra_env, name_allocator = plan_single_agent_name(
            query,
            extra_env,
            project_name=project_name,
            timestamp=timestamp,
        )
    
        fixed_workspace = is_home_mode or has_wait
        try:
            execution = execute_launch_plan(
                plan_fake_fanout("single", [query]),
                LaunchExecutionContext(
                    cl_name=cl_name,
                    project_file=project_file,
                    project_name=project_name,
                    update_target=update_target,
                    history_sort_key=history_sort_key,
                    is_home_mode=is_home_mode,
                    vcs_ref=vcs_ref,
                    deferred_workspace=has_wait,
                    workspace_num=workspace_num if fixed_workspace else None,
                    workspace_dir=workspace_dir if fixed_workspace else None,
                    use_preallocated_workspace=False,
                ),
                extra_env=extra_env,
                base_timestamp=timestamp,
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
                before_spawn=(
                    None
                    if before_agent_spawn is None
                    else lambda slot, request: before_agent_spawn(
                        0, int(slot.slot_index), request, None
                    )
                ),
                on_slot_executed=(
                    None
                    if on_agent_launch_recorded is None
                    else lambda record: on_agent_launch_recorded(
                        0, int(record.slot.slot_index), record, None
                    )
                ),
                stop_requested=pause_requested_fn,
            )
        except Exception:
            if name_allocator is not None:
                name_allocator.release_uncommitted_template_reservations()
            recorder.record_failed()
            raise
>       if execution.paused:
           ^^^^^^^^^^^^^^^^
E       AttributeError: 'types.SimpleNamespace' object has no attribute 'paused'

src/sase/agent/launch_cwd_single.py:203: AttributeError
__________________ test_history_text_replaces_rewritten_query __________________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/test_history_text_replaces_rew0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa8f8764050>

    def test_history_text_replaces_rewritten_query(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """An explicit history_text wins over the rewritten launch query."""
        history_file = _history_file(tmp_path)
        monkeypatch.delenv("SASE_AGENT", raising=False)
        _isolated_successful_cwd_launch(monkeypatch)
        with patch("sase.history.prompt_store._PROMPT_HISTORY_FILE", history_file):
>           launch_agents_from_cwd(
                "remodeled member text launched here instead",
                origin="typed",
                history_text="please handle the original submission text now",
            )

tests/history/test_prompt_canonical_text.py:164: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/agent/launch_cwd.py:44: in launch_agents_from_cwd
    return launch_agents_from_cwd_impl(
src/sase/agent/launch_cwd_agents.py:318: in launch_agents_from_cwd_impl
    return launch_single_agent(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = 'remodeled member text launched here instead'
project_file = '/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/home-qj2hhnee/.sase/projects/home/home.sase'
project_name = 'home', is_home_mode = True, workspace_num = 0
extra_env = {'SASE_LAUNCH_SUBMITTED_AT': '2026-11-18T04:43:11.585197Z', 'SASE_PROMPT_ORIGIN': 'typed', 'SASE_PROMPT_AUTHORSHIP': 'human', 'SASE_PROMPT_SOURCE_SURFACE': 'unknown', ...}
timestamp = 'ts-0'
recorder = LaunchHistoryRecorder(text='please handle the original submission text now', origin='typed', allow_short=False)
before_agent_spawn = None, on_agent_launch_recorded = None
pause_requested_fn = None, on_launch_paused = None

    def launch_single_agent(
        query: str,
        *,
        project_file: str,
        project_name: str,
        is_home_mode: bool,
        workspace_num: int | None,
        extra_env: dict[str, str] | None,
        timestamp: str | None,
        recorder: LaunchHistoryRecorder,
        before_agent_spawn: Callable[[int, int, object, object | None], None] | None = None,
        on_agent_launch_recorded: Callable[[int, int, object, object | None], None]
        | None = None,
        pause_requested_fn: Callable[[], bool] | None = None,
        on_launch_paused: Callable[[], None] | None = None,
    ) -> list[AgentLaunchResult]:
        """Resolve the VCS/workspace context for one prompt and spawn it.
    
        History records the recorder's submitted invocation text, which may
        differ from *query* when a swarm expanded to this single slot.
        """
        from sase.ace.tui.actions.agent_workflow._ref_resolution import (
            resolve_ref_from_prompt,
        )
        from sase.workspace_provider import get_workflow_names
        from sase.macro.directives import has_deferred_start_directive
    
        has_wait = has_deferred_start_directive(query)
        vcs_ref: tuple[str, str] | None = None
        workspace_dir: str | None = None
    
        # Resolve VCS metadata without reserving a numbered workspace for normal
        # VCS refs. The executor claims the final slot atomically just before
        # spawn; deferred %wait launches carry a workspace here.
        for wf_name in get_workflow_names():
            resolved = resolve_ref_from_prompt(
                query,
                wf_name,
                skip_workspace=True,
            )
            if resolved is not None:
                project_file, project_name, resolved_dir, ws_num, ref_value = resolved
                if has_wait:
                    workspace_dir = resolved_dir
                    workspace_num = ws_num
                else:
                    workspace_dir = None
                    workspace_num = None
                vcs_ref = (wf_name, ref_value)
                is_home_mode = False
                break
    
        if vcs_ref is None:
            known_ref = resolve_known_project_vcs_launch_ref(query)
            if known_ref is not None:
                project_file = known_ref.project_file
                project_name = known_ref.ref
                workspace_dir = known_ref.workspace_dir if has_wait else None
                workspace_num = 0
                vcs_ref = (known_ref.workflow_type, known_ref.ref)
                is_home_mode = False
    
        if vcs_ref is None and not is_home_mode:
            from sase.workspace_provider import get_ref_patterns
    
            for wf_name, pattern in get_ref_patterns().items():
                match = pattern.search(query)
                if match is not None:
                    ref_value = match.group(1) or match.group(2)
                    if ref_value:
                        vcs_ref = (wf_name, ref_value)
                        break
    
        # If no workspace ref is found and we're not already in home mode, fall
        # back to direct home mode. Bare prompts normally gain the default
        # workspace ref before this point; this branch covers disabled/missing
        # workspace providers and explicit non-workspace contexts.
        if vcs_ref is None and not is_home_mode:
            from sase.ace.patch.project_spec_path import preferred_project_spec_path
    
            is_home_mode = True
            project_name = "home"
            home_dir = str(sase_projects_dir() / "home")
            project_file = preferred_project_spec_path(home_dir, "home")
    
        # --- Resolve fixed workspace contexts ---
        if timestamp is None:
            from sase.core.agent_launch_facade import reserve_launch_timestamp_batch
    
            timestamp = reserve_launch_timestamp_batch(1)[0]
    
        if not workspace_dir:
            if is_home_mode:
                workspace_dir = os.path.expanduser("~")
                workspace_num = 0
            elif has_wait:
                # Deferred workspace: use main workspace dir as CWD during wait
                from sase.running_field import get_workspace_directory
    
                workspace_num = 0
                workspace_dir = get_workspace_directory(project_name, 1)
    
        # --- Determine display name / sort key ---
        if vcs_ref is not None:
            cl_name = vcs_ref[1]
            history_sort_key = vcs_ref[1]
            from sase.vcs_provider import VCS_DEFAULT_REVISION
    
            update_target = VCS_DEFAULT_REVISION
        else:
            cl_name = project_name
            history_sort_key = ""
            update_target = ""
    
        try:
            from sase.agent.launch_validation import validate_launch_name_requests
    
            validate_launch_name_requests(
                [query],
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
            )
        except RuntimeError:
            recorder.record_failed()
            raise
    
        # --- Save prompt to history ---
        # Records the submitted invocation, not the expanded single slot: a
        # swarm that reduces to one slot must not record that member's text.
        recorder.record_submitted()
    
        from sase.agent.launch_executor import LaunchExecutionContext, execute_launch_plan
        from sase.core.agent_launch_facade import plan_fake_fanout
    
        extra_env, name_allocator = plan_single_agent_name(
            query,
            extra_env,
            project_name=project_name,
            timestamp=timestamp,
        )
    
        fixed_workspace = is_home_mode or has_wait
        try:
            execution = execute_launch_plan(
                plan_fake_fanout("single", [query]),
                LaunchExecutionContext(
                    cl_name=cl_name,
                    project_file=project_file,
                    project_name=project_name,
                    update_target=update_target,
                    history_sort_key=history_sort_key,
                    is_home_mode=is_home_mode,
                    vcs_ref=vcs_ref,
                    deferred_workspace=has_wait,
                    workspace_num=workspace_num if fixed_workspace else None,
                    workspace_dir=workspace_dir if fixed_workspace else None,
                    use_preallocated_workspace=False,
                ),
                extra_env=extra_env,
                base_timestamp=timestamp,
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
                before_spawn=(
                    None
                    if before_agent_spawn is None
                    else lambda slot, request: before_agent_spawn(
                        0, int(slot.slot_index), request, None
                    )
                ),
                on_slot_executed=(
                    None
                    if on_agent_launch_recorded is None
                    else lambda record: on_agent_launch_recorded(
                        0, int(record.slot.slot_index), record, None
                    )
                ),
                stop_requested=pause_requested_fn,
            )
        except Exception:
            if name_allocator is not None:
                name_allocator.release_uncommitted_template_reservations()
            recorder.record_failed()
            raise
>       if execution.paused:
           ^^^^^^^^^^^^^^^^
E       AttributeError: 'types.SimpleNamespace' object has no attribute 'paused'

src/sase/agent/launch_cwd_single.py:203: AttributeError
_______________ test_plain_single_launch_records_query_unchanged _______________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/test_plain_single_launch_recor0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa91aa14520>

    def test_plain_single_launch_records_query_unchanged(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """Without history_text (mobile and plain launches) the query records."""
        history_file = _history_file(tmp_path)
        monkeypatch.delenv("SASE_AGENT", raising=False)
        _isolated_successful_cwd_launch(monkeypatch)
        with patch("sase.history.prompt_store._PROMPT_HISTORY_FILE", history_file):
>           launch_agents_from_cwd(
                "please summarize these project notes for me now", origin="typed"
            )

tests/history/test_prompt_canonical_text.py:234: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/agent/launch_cwd.py:44: in launch_agents_from_cwd
    return launch_agents_from_cwd_impl(
src/sase/agent/launch_cwd_agents.py:318: in launch_agents_from_cwd_impl
    return launch_single_agent(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = 'please summarize these project notes for me now'
project_file = '/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/home-sc_uk5jx/.sase/projects/home/home.sase'
project_name = 'home', is_home_mode = True, workspace_num = 0
extra_env = {'SASE_LAUNCH_SUBMITTED_AT': '2026-11-18T04:43:11.928925Z', 'SASE_PROMPT_ORIGIN': 'typed', 'SASE_PROMPT_AUTHORSHIP': 'human', 'SASE_PROMPT_SOURCE_SURFACE': 'unknown', ...}
timestamp = 'ts-0'
recorder = LaunchHistoryRecorder(text='please summarize these project notes for me now', origin='typed', allow_short=False)
before_agent_spawn = None, on_agent_launch_recorded = None
pause_requested_fn = None, on_launch_paused = None

    def launch_single_agent(
        query: str,
        *,
        project_file: str,
        project_name: str,
        is_home_mode: bool,
        workspace_num: int | None,
        extra_env: dict[str, str] | None,
        timestamp: str | None,
        recorder: LaunchHistoryRecorder,
        before_agent_spawn: Callable[[int, int, object, object | None], None] | None = None,
        on_agent_launch_recorded: Callable[[int, int, object, object | None], None]
        | None = None,
        pause_requested_fn: Callable[[], bool] | None = None,
        on_launch_paused: Callable[[], None] | None = None,
    ) -> list[AgentLaunchResult]:
        """Resolve the VCS/workspace context for one prompt and spawn it.
    
        History records the recorder's submitted invocation text, which may
        differ from *query* when a swarm expanded to this single slot.
        """
        from sase.ace.tui.actions.agent_workflow._ref_resolution import (
            resolve_ref_from_prompt,
        )
        from sase.workspace_provider import get_workflow_names
        from sase.macro.directives import has_deferred_start_directive
    
        has_wait = has_deferred_start_directive(query)
        vcs_ref: tuple[str, str] | None = None
        workspace_dir: str | None = None
    
        # Resolve VCS metadata without reserving a numbered workspace for normal
        # VCS refs. The executor claims the final slot atomically just before
        # spawn; deferred %wait launches carry a workspace here.
        for wf_name in get_workflow_names():
            resolved = resolve_ref_from_prompt(
                query,
                wf_name,
                skip_workspace=True,
            )
            if resolved is not None:
                project_file, project_name, resolved_dir, ws_num, ref_value = resolved
                if has_wait:
                    workspace_dir = resolved_dir
                    workspace_num = ws_num
                else:
                    workspace_dir = None
                    workspace_num = None
                vcs_ref = (wf_name, ref_value)
                is_home_mode = False
                break
    
        if vcs_ref is None:
            known_ref = resolve_known_project_vcs_launch_ref(query)
            if known_ref is not None:
                project_file = known_ref.project_file
                project_name = known_ref.ref
                workspace_dir = known_ref.workspace_dir if has_wait else None
                workspace_num = 0
                vcs_ref = (known_ref.workflow_type, known_ref.ref)
                is_home_mode = False
    
        if vcs_ref is None and not is_home_mode:
            from sase.workspace_provider import get_ref_patterns
    
            for wf_name, pattern in get_ref_patterns().items():
                match = pattern.search(query)
                if match is not None:
                    ref_value = match.group(1) or match.group(2)
                    if ref_value:
                        vcs_ref = (wf_name, ref_value)
                        break
    
        # If no workspace ref is found and we're not already in home mode, fall
        # back to direct home mode. Bare prompts normally gain the default
        # workspace ref before this point; this branch covers disabled/missing
        # workspace providers and explicit non-workspace contexts.
        if vcs_ref is None and not is_home_mode:
            from sase.ace.patch.project_spec_path import preferred_project_spec_path
    
            is_home_mode = True
            project_name = "home"
            home_dir = str(sase_projects_dir() / "home")
            project_file = preferred_project_spec_path(home_dir, "home")
    
        # --- Resolve fixed workspace contexts ---
        if timestamp is None:
            from sase.core.agent_launch_facade import reserve_launch_timestamp_batch
    
            timestamp = reserve_launch_timestamp_batch(1)[0]
    
        if not workspace_dir:
            if is_home_mode:
                workspace_dir = os.path.expanduser("~")
                workspace_num = 0
            elif has_wait:
                # Deferred workspace: use main workspace dir as CWD during wait
                from sase.running_field import get_workspace_directory
    
                workspace_num = 0
                workspace_dir = get_workspace_directory(project_name, 1)
    
        # --- Determine display name / sort key ---
        if vcs_ref is not None:
            cl_name = vcs_ref[1]
            history_sort_key = vcs_ref[1]
            from sase.vcs_provider import VCS_DEFAULT_REVISION
    
            update_target = VCS_DEFAULT_REVISION
        else:
            cl_name = project_name
            history_sort_key = ""
            update_target = ""
    
        try:
            from sase.agent.launch_validation import validate_launch_name_requests
    
            validate_launch_name_requests(
                [query],
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
            )
        except RuntimeError:
            recorder.record_failed()
            raise
    
        # --- Save prompt to history ---
        # Records the submitted invocation, not the expanded single slot: a
        # swarm that reduces to one slot must not record that member's text.
        recorder.record_submitted()
    
        from sase.agent.launch_executor import LaunchExecutionContext, execute_launch_plan
        from sase.core.agent_launch_facade import plan_fake_fanout
    
        extra_env, name_allocator = plan_single_agent_name(
            query,
            extra_env,
            project_name=project_name,
            timestamp=timestamp,
        )
    
        fixed_workspace = is_home_mode or has_wait
        try:
            execution = execute_launch_plan(
                plan_fake_fanout("single", [query]),
                LaunchExecutionContext(
                    cl_name=cl_name,
                    project_file=project_file,
                    project_name=project_name,
                    update_target=update_target,
                    history_sort_key=history_sort_key,
                    is_home_mode=is_home_mode,
                    vcs_ref=vcs_ref,
                    deferred_workspace=has_wait,
                    workspace_num=workspace_num if fixed_workspace else None,
                    workspace_dir=workspace_dir if fixed_workspace else None,
                    use_preallocated_workspace=False,
                ),
                extra_env=extra_env,
                base_timestamp=timestamp,
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
                before_spawn=(
                    None
                    if before_agent_spawn is None
                    else lambda slot, request: before_agent_spawn(
                        0, int(slot.slot_index), request, None
                    )
                ),
                on_slot_executed=(
                    None
                    if on_agent_launch_recorded is None
                    else lambda record: on_agent_launch_recorded(
                        0, int(record.slot.slot_index), record, None
                    )
                ),
                stop_requested=pause_requested_fn,
            )
        except Exception:
            if name_allocator is not None:
                name_allocator.release_uncommitted_template_reservations()
            recorder.record_failed()
            raise
>       if execution.paused:
           ^^^^^^^^^^^^^^^^
E       AttributeError: 'types.SimpleNamespace' object has no attribute 'paused'

src/sase/agent/launch_cwd_single.py:203: AttributeError
___________________ test_single_agent_launch_threads_origin ____________________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa91a8bb4d0>

    def test_single_agent_launch_threads_origin(monkeypatch) -> None:
        """The single-agent launch path records the recorder's text and origin."""
        from sase.agent import launch_cwd_single
        from sase.agent.launch_cwd_common import LaunchHistoryRecorder
    
        monkeypatch.delenv("SASE_AGENT", raising=False)
        monkeypatch.setattr("sase.workspace_provider.get_workflow_names", lambda: set())
        monkeypatch.setattr(
            "sase.agent.launch_validation.validate_launch_name_requests",
            lambda *args, **kwargs: None,
        )
        monkeypatch.setattr(
            launch_cwd_single,
            "plan_single_agent_name",
            lambda *args, **kwargs: (kwargs.get("extra_env"), None),
        )
        monkeypatch.setattr(
            "sase.agent.launch_executor.execute_launch_plan",
            lambda *args, **kwargs: SimpleNamespace(results=[SimpleNamespace(pid=1)]),
        )
        seen: dict[str, object] = {}
    
        def _capture(text: str, **kwargs: object) -> None:
            seen["text"] = text
            seen.update(kwargs)
    
        monkeypatch.setattr("sase.history.prompt.add_or_update_prompt", _capture)
    
>       launch_cwd_single.launch_single_agent(
            "expanded single member text here",
            project_file="home.sase",
            project_name="home",
            is_home_mode=True,
            workspace_num=0,
            extra_env=None,
            timestamp="260929_071614",
            recorder=LaunchHistoryRecorder(
                text="please do something useful right now", origin="typed"
            ),
        )

tests/history/test_prompt_origin.py:337: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = 'expanded single member text here', project_file = 'home.sase'
project_name = 'home', is_home_mode = True, workspace_num = 0, extra_env = None
timestamp = '260929_071614'
recorder = LaunchHistoryRecorder(text='please do something useful right now', origin='typed', allow_short=False)
before_agent_spawn = None, on_agent_launch_recorded = None
pause_requested_fn = None, on_launch_paused = None

    def launch_single_agent(
        query: str,
        *,
        project_file: str,
        project_name: str,
        is_home_mode: bool,
        workspace_num: int | None,
        extra_env: dict[str, str] | None,
        timestamp: str | None,
        recorder: LaunchHistoryRecorder,
        before_agent_spawn: Callable[[int, int, object, object | None], None] | None = None,
        on_agent_launch_recorded: Callable[[int, int, object, object | None], None]
        | None = None,
        pause_requested_fn: Callable[[], bool] | None = None,
        on_launch_paused: Callable[[], None] | None = None,
    ) -> list[AgentLaunchResult]:
        """Resolve the VCS/workspace context for one prompt and spawn it.
    
        History records the recorder's submitted invocation text, which may
        differ from *query* when a swarm expanded to this single slot.
        """
        from sase.ace.tui.actions.agent_workflow._ref_resolution import (
            resolve_ref_from_prompt,
        )
        from sase.workspace_provider import get_workflow_names
        from sase.macro.directives import has_deferred_start_directive
    
        has_wait = has_deferred_start_directive(query)
        vcs_ref: tuple[str, str] | None = None
        workspace_dir: str | None = None
    
        # Resolve VCS metadata without reserving a numbered workspace for normal
        # VCS refs. The executor claims the final slot atomically just before
        # spawn; deferred %wait launches carry a workspace here.
        for wf_name in get_workflow_names():
            resolved = resolve_ref_from_prompt(
                query,
                wf_name,
                skip_workspace=True,
            )
            if resolved is not None:
                project_file, project_name, resolved_dir, ws_num, ref_value = resolved
                if has_wait:
                    workspace_dir = resolved_dir
                    workspace_num = ws_num
                else:
                    workspace_dir = None
                    workspace_num = None
                vcs_ref = (wf_name, ref_value)
                is_home_mode = False
                break
    
        if vcs_ref is None:
            known_ref = resolve_known_project_vcs_launch_ref(query)
            if known_ref is not None:
                project_file = known_ref.project_file
                project_name = known_ref.ref
                workspace_dir = known_ref.workspace_dir if has_wait else None
                workspace_num = 0
                vcs_ref = (known_ref.workflow_type, known_ref.ref)
                is_home_mode = False
    
        if vcs_ref is None and not is_home_mode:
            from sase.workspace_provider import get_ref_patterns
    
            for wf_name, pattern in get_ref_patterns().items():
                match = pattern.search(query)
                if match is not None:
                    ref_value = match.group(1) or match.group(2)
                    if ref_value:
                        vcs_ref = (wf_name, ref_value)
                        break
    
        # If no workspace ref is found and we're not already in home mode, fall
        # back to direct home mode. Bare prompts normally gain the default
        # workspace ref before this point; this branch covers disabled/missing
        # workspace providers and explicit non-workspace contexts.
        if vcs_ref is None and not is_home_mode:
            from sase.ace.patch.project_spec_path import preferred_project_spec_path
    
            is_home_mode = True
            project_name = "home"
            home_dir = str(sase_projects_dir() / "home")
            project_file = preferred_project_spec_path(home_dir, "home")
    
        # --- Resolve fixed workspace contexts ---
        if timestamp is None:
            from sase.core.agent_launch_facade import reserve_launch_timestamp_batch
    
            timestamp = reserve_launch_timestamp_batch(1)[0]
    
        if not workspace_dir:
            if is_home_mode:
                workspace_dir = os.path.expanduser("~")
                workspace_num = 0
            elif has_wait:
                # Deferred workspace: use main workspace dir as CWD during wait
                from sase.running_field import get_workspace_directory
    
                workspace_num = 0
                workspace_dir = get_workspace_directory(project_name, 1)
    
        # --- Determine display name / sort key ---
        if vcs_ref is not None:
            cl_name = vcs_ref[1]
            history_sort_key = vcs_ref[1]
            from sase.vcs_provider import VCS_DEFAULT_REVISION
    
            update_target = VCS_DEFAULT_REVISION
        else:
            cl_name = project_name
            history_sort_key = ""
            update_target = ""
    
        try:
            from sase.agent.launch_validation import validate_launch_name_requests
    
            validate_launch_name_requests(
                [query],
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
            )
        except RuntimeError:
            recorder.record_failed()
            raise
    
        # --- Save prompt to history ---
        # Records the submitted invocation, not the expanded single slot: a
        # swarm that reduces to one slot must not record that member's text.
        recorder.record_submitted()
    
        from sase.agent.launch_executor import LaunchExecutionContext, execute_launch_plan
        from sase.core.agent_launch_facade import plan_fake_fanout
    
        extra_env, name_allocator = plan_single_agent_name(
            query,
            extra_env,
            project_name=project_name,
            timestamp=timestamp,
        )
    
        fixed_workspace = is_home_mode or has_wait
        try:
            execution = execute_launch_plan(
                plan_fake_fanout("single", [query]),
                LaunchExecutionContext(
                    cl_name=cl_name,
                    project_file=project_file,
                    project_name=project_name,
                    update_target=update_target,
                    history_sort_key=history_sort_key,
                    is_home_mode=is_home_mode,
                    vcs_ref=vcs_ref,
                    deferred_workspace=has_wait,
                    workspace_num=workspace_num if fixed_workspace else None,
                    workspace_dir=workspace_dir if fixed_workspace else None,
                    use_preallocated_workspace=False,
                ),
                extra_env=extra_env,
                base_timestamp=timestamp,
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
                before_spawn=(
                    None
                    if before_agent_spawn is None
                    else lambda slot, request: before_agent_spawn(
                        0, int(slot.slot_index), request, None
                    )
                ),
                on_slot_executed=(
                    None
                    if on_agent_launch_recorded is None
                    else lambda record: on_agent_launch_recorded(
                        0, int(record.slot.slot_index), record, None
                    )
                ),
                stop_requested=pause_requested_fn,
            )
        except Exception:
            if name_allocator is not None:
                name_allocator.release_uncommitted_template_reservations()
            recorder.record_failed()
            raise
>       if execution.paused:
           ^^^^^^^^^^^^^^^^
E       AttributeError: 'types.SimpleNamespace' object has no attribute 'paused'

src/sase/agent/launch_cwd_single.py:203: AttributeError
_______________ test_chop_env_launch_records_nothing_on_success ________________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/test_chop_env_launch_records_n0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa8e2c899b0>

    def test_chop_env_launch_records_nothing_on_success(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """Chop markers in extra_env suppress the success write."""
        from sase.agent.launcher import launch_agents_from_cwd
        from sase.axe.chop_agents import ENV_CHOP_NAME
    
        monkeypatch.delenv("SASE_AGENT", raising=False)
        history_file = _history_file(tmp_path)
        placeholders, stashes = _patch_history_sinks(monkeypatch)
        _isolated_successful_cwd_launch(monkeypatch)
    
        with patch("sase.history.prompt_store._PROMPT_HISTORY_FILE", history_file):
>           launch_agents_from_cwd(
                "please refresh the project documentation now",
                extra_env={ENV_CHOP_NAME: "refresh_docs"},
                origin=None,
            )

tests/history/test_prompt_origin.py:498: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/agent/launch_cwd.py:44: in launch_agents_from_cwd
    return launch_agents_from_cwd_impl(
src/sase/agent/launch_cwd_agents.py:318: in launch_agents_from_cwd_impl
    return launch_single_agent(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = 'please refresh the project documentation now'
project_file = '/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/home-d7kdmkgk/.sase/projects/home/home.sase'
project_name = 'home', is_home_mode = True, workspace_num = 0
extra_env = {'SASE_CHOP_NAME': 'refresh_docs', 'SASE_LAUNCH_SUBMITTED_AT': '2026-11-18T04:43:15.650519Z', 'SASE_PROMPT_ORIGIN': 'generated', 'SASE_PROMPT_AUTHORSHIP': 'agent', ...}
timestamp = 'ts-0'
recorder = LaunchHistoryRecorder(text='please refresh the project documentation now', origin='generated', allow_short=False)
before_agent_spawn = None, on_agent_launch_recorded = None
pause_requested_fn = None, on_launch_paused = None

    def launch_single_agent(
        query: str,
        *,
        project_file: str,
        project_name: str,
        is_home_mode: bool,
        workspace_num: int | None,
        extra_env: dict[str, str] | None,
        timestamp: str | None,
        recorder: LaunchHistoryRecorder,
        before_agent_spawn: Callable[[int, int, object, object | None], None] | None = None,
        on_agent_launch_recorded: Callable[[int, int, object, object | None], None]
        | None = None,
        pause_requested_fn: Callable[[], bool] | None = None,
        on_launch_paused: Callable[[], None] | None = None,
    ) -> list[AgentLaunchResult]:
        """Resolve the VCS/workspace context for one prompt and spawn it.
    
        History records the recorder's submitted invocation text, which may
        differ from *query* when a swarm expanded to this single slot.
        """
        from sase.ace.tui.actions.agent_workflow._ref_resolution import (
            resolve_ref_from_prompt,
        )
        from sase.workspace_provider import get_workflow_names
        from sase.macro.directives import has_deferred_start_directive
    
        has_wait = has_deferred_start_directive(query)
        vcs_ref: tuple[str, str] | None = None
        workspace_dir: str | None = None
    
        # Resolve VCS metadata without reserving a numbered workspace for normal
        # VCS refs. The executor claims the final slot atomically just before
        # spawn; deferred %wait launches carry a workspace here.
        for wf_name in get_workflow_names():
            resolved = resolve_ref_from_prompt(
                query,
                wf_name,
                skip_workspace=True,
            )
            if resolved is not None:
                project_file, project_name, resolved_dir, ws_num, ref_value = resolved
                if has_wait:
                    workspace_dir = resolved_dir
                    workspace_num = ws_num
                else:
                    workspace_dir = None
                    workspace_num = None
                vcs_ref = (wf_name, ref_value)
                is_home_mode = False
                break
    
        if vcs_ref is None:
            known_ref = resolve_known_project_vcs_launch_ref(query)
            if known_ref is not None:
                project_file = known_ref.project_file
                project_name = known_ref.ref
                workspace_dir = known_ref.workspace_dir if has_wait else None
                workspace_num = 0
                vcs_ref = (known_ref.workflow_type, known_ref.ref)
                is_home_mode = False
    
        if vcs_ref is None and not is_home_mode:
            from sase.workspace_provider import get_ref_patterns
    
            for wf_name, pattern in get_ref_patterns().items():
                match = pattern.search(query)
                if match is not None:
                    ref_value = match.group(1) or match.group(2)
                    if ref_value:
                        vcs_ref = (wf_name, ref_value)
                        break
    
        # If no workspace ref is found and we're not already in home mode, fall
        # back to direct home mode. Bare prompts normally gain the default
        # workspace ref before this point; this branch covers disabled/missing
        # workspace providers and explicit non-workspace contexts.
        if vcs_ref is None and not is_home_mode:
            from sase.ace.patch.project_spec_path import preferred_project_spec_path
    
            is_home_mode = True
            project_name = "home"
            home_dir = str(sase_projects_dir() / "home")
            project_file = preferred_project_spec_path(home_dir, "home")
    
        # --- Resolve fixed workspace contexts ---
        if timestamp is None:
            from sase.core.agent_launch_facade import reserve_launch_timestamp_batch
    
            timestamp = reserve_launch_timestamp_batch(1)[0]
    
        if not workspace_dir:
            if is_home_mode:
                workspace_dir = os.path.expanduser("~")
                workspace_num = 0
            elif has_wait:
                # Deferred workspace: use main workspace dir as CWD during wait
                from sase.running_field import get_workspace_directory
    
                workspace_num = 0
                workspace_dir = get_workspace_directory(project_name, 1)
    
        # --- Determine display name / sort key ---
        if vcs_ref is not None:
            cl_name = vcs_ref[1]
            history_sort_key = vcs_ref[1]
            from sase.vcs_provider import VCS_DEFAULT_REVISION
    
            update_target = VCS_DEFAULT_REVISION
        else:
            cl_name = project_name
            history_sort_key = ""
            update_target = ""
    
        try:
            from sase.agent.launch_validation import validate_launch_name_requests
    
            validate_launch_name_requests(
                [query],
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
            )
        except RuntimeError:
            recorder.record_failed()
            raise
    
        # --- Save prompt to history ---
        # Records the submitted invocation, not the expanded single slot: a
        # swarm that reduces to one slot must not record that member's text.
        recorder.record_submitted()
    
        from sase.agent.launch_executor import LaunchExecutionContext, execute_launch_plan
        from sase.core.agent_launch_facade import plan_fake_fanout
    
        extra_env, name_allocator = plan_single_agent_name(
            query,
            extra_env,
            project_name=project_name,
            timestamp=timestamp,
        )
    
        fixed_workspace = is_home_mode or has_wait
        try:
            execution = execute_launch_plan(
                plan_fake_fanout("single", [query]),
                LaunchExecutionContext(
                    cl_name=cl_name,
                    project_file=project_file,
                    project_name=project_name,
                    update_target=update_target,
                    history_sort_key=history_sort_key,
                    is_home_mode=is_home_mode,
                    vcs_ref=vcs_ref,
                    deferred_workspace=has_wait,
                    workspace_num=workspace_num if fixed_workspace else None,
                    workspace_dir=workspace_dir if fixed_workspace else None,
                    use_preallocated_workspace=False,
                ),
                extra_env=extra_env,
                base_timestamp=timestamp,
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
                before_spawn=(
                    None
                    if before_agent_spawn is None
                    else lambda slot, request: before_agent_spawn(
                        0, int(slot.slot_index), request, None
                    )
                ),
                on_slot_executed=(
                    None
                    if on_agent_launch_recorded is None
                    else lambda record: on_agent_launch_recorded(
                        0, int(record.slot.slot_index), record, None
                    )
                ),
                stop_requested=pause_requested_fn,
            )
        except Exception:
            if name_allocator is not None:
                name_allocator.release_uncommitted_template_reservations()
            recorder.record_failed()
            raise
>       if execution.paused:
           ^^^^^^^^^^^^^^^^
E       AttributeError: 'types.SimpleNamespace' object has no attribute 'paused'

src/sase/agent/launch_cwd_single.py:203: AttributeError
_____________ test_job_process_env_does_not_suppress_typed_launch ______________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/test_job_process_env_does_not_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa8e2c8a4a0>

    def test_job_process_env_does_not_suppress_typed_launch(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """SASE_JOB_NAME in the process env still records (Telegram runs in jobs)."""
        monkeypatch.setenv("SASE_JOB_NAME", "nightly_tick")
        monkeypatch.delenv("SASE_AGENT", raising=False)
        history_file = _history_file(tmp_path)
        _patch_history_sinks(monkeypatch)
        _isolated_successful_cwd_launch(monkeypatch)
    
        from sase.agent.launcher import launch_agents_from_cwd
    
        with patch("sase.history.prompt_store._PROMPT_HISTORY_FILE", history_file):
>           launch_agents_from_cwd("please summarize these project notes now", origin=None)

tests/history/test_prompt_origin.py:557: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/agent/launch_cwd.py:44: in launch_agents_from_cwd
    return launch_agents_from_cwd_impl(
src/sase/agent/launch_cwd_agents.py:318: in launch_agents_from_cwd_impl
    return launch_single_agent(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = 'please summarize these project notes now'
project_file = '/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw4/home-n4s5tfbz/.sase/projects/home/home.sase'
project_name = 'home', is_home_mode = True, workspace_num = 0
extra_env = {'SASE_LAUNCH_SUBMITTED_AT': '2026-11-18T04:43:15.687544Z', 'SASE_PROMPT_ORIGIN': 'unknown', 'SASE_PROMPT_AUTHORSHIP': 'agent', 'SASE_PROMPT_SOURCE_SURFACE': 'unknown', ...}
timestamp = 'ts-0'
recorder = LaunchHistoryRecorder(text='please summarize these project notes now', origin=None, allow_short=False)
before_agent_spawn = None, on_agent_launch_recorded = None
pause_requested_fn = None, on_launch_paused = None

    def launch_single_agent(
        query: str,
        *,
        project_file: str,
        project_name: str,
        is_home_mode: bool,
        workspace_num: int | None,
        extra_env: dict[str, str] | None,
        timestamp: str | None,
        recorder: LaunchHistoryRecorder,
        before_agent_spawn: Callable[[int, int, object, object | None], None] | None = None,
        on_agent_launch_recorded: Callable[[int, int, object, object | None], None]
        | None = None,
        pause_requested_fn: Callable[[], bool] | None = None,
        on_launch_paused: Callable[[], None] | None = None,
    ) -> list[AgentLaunchResult]:
        """Resolve the VCS/workspace context for one prompt and spawn it.
    
        History records the recorder's submitted invocation text, which may
        differ from *query* when a swarm expanded to this single slot.
        """
        from sase.ace.tui.actions.agent_workflow._ref_resolution import (
            resolve_ref_from_prompt,
        )
        from sase.workspace_provider import get_workflow_names
        from sase.macro.directives import has_deferred_start_directive
    
        has_wait = has_deferred_start_directive(query)
        vcs_ref: tuple[str, str] | None = None
        workspace_dir: str | None = None
    
        # Resolve VCS metadata without reserving a numbered workspace for normal
        # VCS refs. The executor claims the final slot atomically just before
        # spawn; deferred %wait launches carry a workspace here.
        for wf_name in get_workflow_names():
            resolved = resolve_ref_from_prompt(
                query,
                wf_name,
                skip_workspace=True,
            )
            if resolved is not None:
                project_file, project_name, resolved_dir, ws_num, ref_value = resolved
                if has_wait:
                    workspace_dir = resolved_dir
                    workspace_num = ws_num
                else:
                    workspace_dir = None
                    workspace_num = None
                vcs_ref = (wf_name, ref_value)
                is_home_mode = False
                break
    
        if vcs_ref is None:
            known_ref = resolve_known_project_vcs_launch_ref(query)
            if known_ref is not None:
                project_file = known_ref.project_file
                project_name = known_ref.ref
                workspace_dir = known_ref.workspace_dir if has_wait else None
                workspace_num = 0
                vcs_ref = (known_ref.workflow_type, known_ref.ref)
                is_home_mode = False
    
        if vcs_ref is None and not is_home_mode:
            from sase.workspace_provider import get_ref_patterns
    
            for wf_name, pattern in get_ref_patterns().items():
                match = pattern.search(query)
                if match is not None:
                    ref_value = match.group(1) or match.group(2)
                    if ref_value:
                        vcs_ref = (wf_name, ref_value)
                        break
    
        # If no workspace ref is found and we're not already in home mode, fall
        # back to direct home mode. Bare prompts normally gain the default
        # workspace ref before this point; this branch covers disabled/missing
        # workspace providers and explicit non-workspace contexts.
        if vcs_ref is None and not is_home_mode:
            from sase.ace.patch.project_spec_path import preferred_project_spec_path
    
            is_home_mode = True
            project_name = "home"
            home_dir = str(sase_projects_dir() / "home")
            project_file = preferred_project_spec_path(home_dir, "home")
    
        # --- Resolve fixed workspace contexts ---
        if timestamp is None:
            from sase.core.agent_launch_facade import reserve_launch_timestamp_batch
    
            timestamp = reserve_launch_timestamp_batch(1)[0]
    
        if not workspace_dir:
            if is_home_mode:
                workspace_dir = os.path.expanduser("~")
                workspace_num = 0
            elif has_wait:
                # Deferred workspace: use main workspace dir as CWD during wait
                from sase.running_field import get_workspace_directory
    
                workspace_num = 0
                workspace_dir = get_workspace_directory(project_name, 1)
    
        # --- Determine display name / sort key ---
        if vcs_ref is not None:
            cl_name = vcs_ref[1]
            history_sort_key = vcs_ref[1]
            from sase.vcs_provider import VCS_DEFAULT_REVISION
    
            update_target = VCS_DEFAULT_REVISION
        else:
            cl_name = project_name
            history_sort_key = ""
            update_target = ""
    
        try:
            from sase.agent.launch_validation import validate_launch_name_requests
    
            validate_launch_name_requests(
                [query],
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
            )
        except RuntimeError:
            recorder.record_failed()
            raise
    
        # --- Save prompt to history ---
        # Records the submitted invocation, not the expanded single slot: a
        # swarm that reduces to one slot must not record that member's text.
        recorder.record_submitted()
    
        from sase.agent.launch_executor import LaunchExecutionContext, execute_launch_plan
        from sase.core.agent_launch_facade import plan_fake_fanout
    
        extra_env, name_allocator = plan_single_agent_name(
            query,
            extra_env,
            project_name=project_name,
            timestamp=timestamp,
        )
    
        fixed_workspace = is_home_mode or has_wait
        try:
            execution = execute_launch_plan(
                plan_fake_fanout("single", [query]),
                LaunchExecutionContext(
                    cl_name=cl_name,
                    project_file=project_file,
                    project_name=project_name,
                    update_target=update_target,
                    history_sort_key=history_sort_key,
                    is_home_mode=is_home_mode,
                    vcs_ref=vcs_ref,
                    deferred_workspace=has_wait,
                    workspace_num=workspace_num if fixed_workspace else None,
                    workspace_dir=workspace_dir if fixed_workspace else None,
                    use_preallocated_workspace=False,
                ),
                extra_env=extra_env,
                base_timestamp=timestamp,
                allow_reserved_agent_session_separator_names=internal_agent_name_bypass_for_launch(
                    extra_env
                ),
                before_spawn=(
                    None
                    if before_agent_spawn is None
                    else lambda slot, request: before_agent_spawn(
                        0, int(slot.slot_index), request, None
                    )
                ),
                on_slot_executed=(
                    None
                    if on_agent_launch_recorded is None
                    else lambda record: on_agent_launch_recorded(
                        0, int(record.slot.slot_index), record, None
                    )
                ),
                stop_requested=pause_requested_fn,
            )
        except Exception:
            if name_allocator is not None:
                name_allocator.release_uncommitted_template_reservations()
            recorder.record_failed()
            raise
>       if execution.paused:
           ^^^^^^^^^^^^^^^^
E       AttributeError: 'types.SimpleNamespace' object has no attribute 'paused'

src/sase/agent/launch_cwd_single.py:203: AttributeError
______________________ test_no_system_clock_display_sites ______________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

    def test_no_system_clock_display_sites() -> None:
        """Fix new hits by routing through sase.core.time before extending the allowlist."""
        violations: list[str] = []
        for path in sorted(_SRC_ROOT.rglob("*.py")):
            source = path.read_text(encoding="utf-8")
            if not any(name in source for name in _CLOCK_ATTR_NAMES):
                continue
            lines = source.splitlines()
            parents = _ast_parents(ast.parse(source, filename=str(path)))
            relpath = path.relative_to(_SRC_ROOT).as_posix()
    
            for node in sorted(parents, key=lambda item: getattr(item, "lineno", -1)):
                if not isinstance(node, ast.Call):
                    continue
                if not _is_bare_clock_call(node):
                    continue
                symbol = _enclosing_symbol(node, parents)
                if f"{relpath}:{symbol}" in _ALLOWED_CLOCK_DISPLAY_SITES:
                    continue
                line = lines[node.lineno - 1].strip()
                violations.append(f"src/sase/{relpath}:{node.lineno}: {line}")
    
>       assert not violations, "system-clock display sites:\n" + "\n".join(violations)
E       AssertionError: system-clock display sites:
E         src/sase/axe/chop_proposal_launch.py:146: "created_at": datetime.now().astimezone().isoformat(),
E         src/sase/axe/chop_proposal_launch.py:146: "created_at": datetime.now().astimezone().isoformat(),
E       assert not ['src/sase/axe/chop_proposal_launch.py:146: "created_at": datetime.now().astimezone().isoformat(),', 'src/sase/axe/chop_proposal_launch.py:146: "created_at": datetime.now().astimezone().isoformat(),']

tests/test_timezone_display_guard.py:46: AssertionError
________________ test_pre_expand_parallel_no_embedded_workflows ________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

    def test_pre_expand_parallel_no_embedded_workflows() -> None:
        """Test that steps without embedded workflows pass through unchanged."""
        nested_steps = [
            WorkflowStep(name="step_a", bash='echo "a=done"'),
            WorkflowStep(name="step_b", agent="Plain prompt with no refs"),
        ]
    
        workflow = _create_workflow("test", [])
        executor = _create_executor(workflow)
    
        with patch("sase.macro.loader.get_all_workflows") as mock_get:
            mock_get.return_value = {}
            modified, collected = executor._pre_expand_parallel_embedded_workflows(
                nested_steps
            )
    
        # Bash step passes through as-is
        assert modified[0] is nested_steps[0]
        # Prompt step without embedded refs also passes through as-is
>       assert modified[1] is nested_steps[1]
E       AssertionError: assert WorkflowStep(name='step_b', agent='Plain prompt with no refs', bash=None, python=None, prompt_part=None, output=None, ...fig=None, while_config=None, parallel_config=None, join=None, finally_=False, artifact=None, on_error=None, trust=None) is WorkflowStep(name='step_b', agent='Plain prompt with no refs', bash=None, python=None, prompt_part=None, output=None, ...fig=None, while_config=None, parallel_config=None, join=None, finally_=False, artifact=None, on_error=None, trust=None)

tests/test_workflow_executor_parallel.py:206: AssertionError
____ test_runner_batches_clan_proposals_with_per_member_env_and_full_waits _____
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

lumberjack_name = 'split'
chop = ChopConfig(name='split', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234944_329924'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 44, 329924, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_batches_clan_propo0/.sase/axe/lumberjacks/split/chops/split/runs/20261117T234944_329924.result.json')
chop_verbose = True
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id='first', prompt='Split first.py.', workspace='git:sase', agent_name='split_...tribe='chop', model=None, effort=None, env={'FILE': 'second.py'}, dedupe_key=None, wait_on='first', wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id='first', prompt='Split first.py.', workspace='git:sase', agent_name='split_...tribe='chop', model=None, effort=None, env={'FILE': 'second.py'}, dedupe_key=None, wait_on='first', wait_runners=None)]
proposals = [{'index': 0, 'id': 'first', 'agent_name': 'toobig-0.split_file.first', 'clan': 'toobig-0', ...}, {'index': 1, 'id': None, 'agent_name': 'toobig-0.split_file.second', 'clan': 'toobig-0', ...}]
once_per_decisions = {}, once_per_effective_waits = {0: None, 1: 'first'}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id='first', prompt='Split first.py.', workspace='...=None, prompt='#git:sase\n%id(split_file.second, clan=toobig-0)\n%wait:toobig-0.split_file.first\nSplit second.py.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300891149984'>
launch_agents_from_cwd_fn = <MagicMock name='launch_agents_from_cwd' id='140300891147968'>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
>           launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )

src/sase/axe/chop_runner_script_result_launch.py:145: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_proposal_launch.py:851: in launch_chop_proposals
    _call_with_supported_kwargs(
src/sase/axe/chop_proposal_launch.py:66: in _call_with_supported_kwargs
    return function(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1176: in __call__
    return self._mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1180: in _mock_call
    return self._execute_mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <MagicMock name='launch_agents_from_cwd' id='140300891147968'>
args = ('#git:sase\n%id:toobig-0.split_file.first\n%clan(toobig-0, tribe=chop, summary=[[[bold]Large modules[/bold]]])\nSplit first.py.\n---\n#git:sase\n%id(split_file.second, clan=toobig-0)\n%wait:toobig-0.split_file.first\nSplit second.py.\n',)
kwargs = {'segment_extra_env': [{'FILE': 'first.py', 'SASE_CHOP_LUMBERJACK': 'split', 'SASE_CHOP_NAME': 'split', 'SASE_CHOP_RUN...9a257cbd70>, 'on_agent_plan_prepared': <function launch_chop_proposals.<locals>._plan_prepared at 0x7f9a257ca560>, ...}

    def _execute_mock_call(self, /, *args, **kwargs):
        # separate from _increment_mock_call so that awaited functions are
        # executed separately from their call, also AsyncMock overrides this method
    
        effect = self.side_effect
        if effect is not None:
            if _is_exception(effect):
                raise effect
            elif not _callable(effect):
                result = next(effect)
                if _is_exception(result):
                    raise result
            else:
>               result = effect(*args, **kwargs)
                         ^^^^^^^^^^^^^^^^^^^^^^^
E               TypeError: test_runner_batches_clan_proposals_with_per_member_env_and_full_waits.<locals>._launch_many() got an unexpected keyword argument 'before_agent_spawn'

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1247: TypeError

During handling of the above exception, another exception occurred:

temp_state_dir = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_batches_clan_propo0/.sase/axe')
tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_batches_clan_propo0')

    def test_runner_batches_clan_proposals_with_per_member_env_and_full_waits(
        temp_state_dir: Path,
        tmp_path: Path,
    ) -> None:
        clan_summary = "[bold]Large modules[/bold]"
        _write_clan_result(tmp_path, with_env=True, clan_summary=clan_summary)
        calls: list[tuple[str, list[dict[str, str]]]] = []
    
        def _launch_many(
            query: str,
            *,
            segment_extra_env: list[dict[str, str]],
            origin: object = None,
        ) -> list[SimpleNamespace]:
            calls.append((query, segment_extra_env))
            return [
                SimpleNamespace(
                    pid=301,
                    agent_name="toobig-0.split_file.first",
                    timestamp="260719_120000",
                ),
                SimpleNamespace(
                    pid=302,
                    agent_name="toobig-0.split_file.second",
                    timestamp="260719_120001",
                ),
            ]
    
        with (
            patch("sase.axe.chop_runner.find_all_patches", return_value=[]),
            patch("sase.axe.chop_runner.launch_agent_from_cwd") as launch_one,
            patch("sase.axe.chop_runner.launch_agents_from_cwd", side_effect=_launch_many),
        ):
>           outcome = _run(tmp_path)
                      ^^^^^^^^^^^^^^

tests/test_axe_chop_clan_launch.py:266: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/test_axe_chop_clan_launch.py:62: in _run
    return run_configured_chop_once(
src/sase/axe/chop_runner.py:155: in run_configured_chop_once
    return _run_script_chop_once(
src/sase/axe/chop_runner.py:103: in _run_script_chop_once
    return run_script_chop_once(
src/sase/axe/chop_runner_script.py:466: in run_script_chop_once
    return process_script_chop_result(
src/sase/axe/chop_runner_script_result.py:408: in process_script_chop_result
    return launch_accepted_script_chop_proposals(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

lumberjack_name = 'split'
chop = ChopConfig(name='split', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234944_329924'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 44, 329924, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_batches_clan_propo0/.sase/axe/lumberjacks/split/chops/split/runs/20261117T234944_329924.result.json')
chop_verbose = True
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id='first', prompt='Split first.py.', workspace='git:sase', agent_name='split_...tribe='chop', model=None, effort=None, env={'FILE': 'second.py'}, dedupe_key=None, wait_on='first', wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id='first', prompt='Split first.py.', workspace='git:sase', agent_name='split_...tribe='chop', model=None, effort=None, env={'FILE': 'second.py'}, dedupe_key=None, wait_on='first', wait_runners=None)]
proposals = [{'index': 0, 'id': 'first', 'agent_name': 'toobig-0.split_file.first', 'clan': 'toobig-0', ...}, {'index': 1, 'id': None, 'agent_name': 'toobig-0.split_file.second', 'clan': 'toobig-0', ...}]
once_per_decisions = {}, once_per_effective_waits = {0: None, 1: 'first'}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id='first', prompt='Split first.py.', workspace='...=None, prompt='#git:sase\n%id(split_file.second, clan=toobig-0)\n%wait:toobig-0.split_file.first\nSplit second.py.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300891149984'>
launch_agents_from_cwd_fn = <MagicMock name='launch_agents_from_cwd' id='140300891147968'>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
            launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )
        except Exception as exc:
            tb = capture_traceback()
            proposals = _updated_proposal_previews()
            if not batch_created:
                release_unlaunched_once_per_keys(
                    lumberjack_name=lumberjack_name,
                    chop_name=chop.name,
                    run_id=run_id,
                    accepted_proposals=accepted_proposals,
                    successful_launches=successful_launches,
                )
            partial_launch = bool(successful_launches) or batch_created
            finalize_script_chop_run(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                started_at=started_at,
                status="launched" if partial_launch else "action_failed",
                exit_code=0,
>               agent_pid=(int(successful_launches[0]["pid"]) if partial_launch else None),
                               ^^^^^^^^^^^^^^^^^^^^^^
                error=exc,
                tb=tb,
                result_file=result_path.name,
                structured_result=structured_result,
                proposals=proposals,
                launches=successful_launches,
                dry_run=False,
                active=partial_launch,
                preflight=preflight,
            )
E           IndexError: list index out of range

src/sase/axe/chop_runner_script_result_launch.py:179: IndexError
__________ test_launch_failure_releases_only_unlaunched_once_per_keys __________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

lumberjack_name = 'docs'
chop = ChopConfig(name='docs', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[]..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234953_379586'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 53, 379586, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_launch_failure_releases_o0/.sase/axe/lumberjacks/docs/chops/docs/runs/20261117T234953_379586.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Refresh.', workspace='git:sase', agent_name='chop.docs.3_3795...ummary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key='docs:polish', wait_on=None, wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Refresh.', workspace='git:sase', agent_name='chop.docs.3_3795...ummary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key='docs:polish', wait_on=None, wait_runners=None)]
proposals = [{'index': 0, 'id': None, 'agent_name': 'chop.docs.3_379586.1', 'clan': None, ...}, {'index': 1, 'id': None, 'agent_name': 'chop.docs.3_379586.2', 'clan': None, ...}]
once_per_decisions = {0: {'outcome': 'accept', 'reason': 'recorded once-per key `docs:refresh`', 'key': 'docs:refresh'}, 1: {'outcome': 'accept', 'reason': 'recorded once-per key `docs:polish`', 'key': 'docs:polish'}}
once_per_effective_waits = {0: None, 1: None}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id=None, prompt='Refresh.', workspace='git:sase',...id=None, declares_clan=False, clan_summary=None, prompt='#git:sase\n%id(chop.docs.3_379586.2, tribe=chop)\nPolish.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916544848'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
>           launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )

src/sase/axe/chop_runner_script_result_launch.py:145: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_proposal_launch.py:935: in launch_chop_proposals
    result = _call_with_supported_kwargs(
src/sase/axe/chop_proposal_launch.py:66: in _call_with_supported_kwargs
    return function(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1176: in __call__
    return self._mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1180: in _mock_call
    return self._execute_mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <MagicMock name='launch_agent_from_cwd' id='140300916544848'>
args = ('#git:sase\n%id(chop.docs.3_379586.1, tribe=chop)\nRefresh.\n',)
kwargs = {'extra_env': {'SASE_CHOP_LUMBERJACK': 'docs', 'SASE_CHOP_NAME': 'docs', 'SASE_CHOP_RUN_ID': '20261117T234953_379586',...9a59acc720>, 'on_agent_plan_prepared': <function launch_chop_proposals.<locals>._plan_prepared at 0x7f9a59acf740>, ...}

    def _execute_mock_call(self, /, *args, **kwargs):
        # separate from _increment_mock_call so that awaited functions are
        # executed separately from their call, also AsyncMock overrides this method
    
        effect = self.side_effect
        if effect is not None:
            if _is_exception(effect):
                raise effect
            elif not _callable(effect):
                result = next(effect)
                if _is_exception(result):
                    raise result
            else:
>               result = effect(*args, **kwargs)
                         ^^^^^^^^^^^^^^^^^^^^^^^
E               TypeError: test_launch_failure_releases_only_unlaunched_once_per_keys.<locals>._launch() got an unexpected keyword argument 'before_agent_spawn'

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1247: TypeError

During handling of the above exception, another exception occurred:

temp_state_dir = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_launch_failure_releases_o0/.sase/axe')
tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_launch_failure_releases_o0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9a5afb3c40>

    def test_launch_failure_releases_only_unlaunched_once_per_keys(
        temp_state_dir: Path,
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setenv("SASE_HOME", str(tmp_path / ".sase"))
        _result_script(
            tmp_path,
            "docs",
            {
                "schema_version": 1,
                "status": "ok",
                "proposed_launches": [
                    {
                        "prompt": "Refresh.",
                        "workspace": "git:sase",
                        "dedupe_key": "docs:refresh",
                    },
                    {
                        "prompt": "Polish.",
                        "workspace": "git:sase",
                        "dedupe_key": "docs:polish",
                    },
                ],
            },
        )
        calls = 0
    
        def _launch(
            prompt: str, *, extra_env: dict[str, str], origin: object = None
        ) -> SimpleNamespace:
            nonlocal calls
            del prompt, extra_env, origin
            calls += 1
            if calls == 2:
                raise RuntimeError("launcher unavailable")
            return SimpleNamespace(
                pid=100,
                agent_name="actual.refresh",
                timestamp="260718_120000",
            )
    
        chop = ChopConfig(name="docs", description="")
        with (
            patch("sase.axe.chop_runner.find_all_patches", return_value=[]),
            patch("sase.axe.chop_runner.launch_agent_from_cwd", side_effect=_launch),
        ):
>           outcome = run_configured_chop_once(
                lumberjack_name="docs",
                chop=chop,
                axe_config=_config(tmp_path),
            )

tests/test_axe_chop_lifecycle_once_per.py:86: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_runner.py:155: in run_configured_chop_once
    return _run_script_chop_once(
src/sase/axe/chop_runner.py:103: in _run_script_chop_once
    return run_script_chop_once(
src/sase/axe/chop_runner_script.py:466: in run_script_chop_once
    return process_script_chop_result(
src/sase/axe/chop_runner_script_result.py:408: in process_script_chop_result
    return launch_accepted_script_chop_proposals(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

lumberjack_name = 'docs'
chop = ChopConfig(name='docs', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[]..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234953_379586'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 53, 379586, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_launch_failure_releases_o0/.sase/axe/lumberjacks/docs/chops/docs/runs/20261117T234953_379586.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Refresh.', workspace='git:sase', agent_name='chop.docs.3_3795...ummary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key='docs:polish', wait_on=None, wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Refresh.', workspace='git:sase', agent_name='chop.docs.3_3795...ummary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key='docs:polish', wait_on=None, wait_runners=None)]
proposals = [{'index': 0, 'id': None, 'agent_name': 'chop.docs.3_379586.1', 'clan': None, ...}, {'index': 1, 'id': None, 'agent_name': 'chop.docs.3_379586.2', 'clan': None, ...}]
once_per_decisions = {0: {'outcome': 'accept', 'reason': 'recorded once-per key `docs:refresh`', 'key': 'docs:refresh'}, 1: {'outcome': 'accept', 'reason': 'recorded once-per key `docs:polish`', 'key': 'docs:polish'}}
once_per_effective_waits = {0: None, 1: None}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id=None, prompt='Refresh.', workspace='git:sase',...id=None, declares_clan=False, clan_summary=None, prompt='#git:sase\n%id(chop.docs.3_379586.2, tribe=chop)\nPolish.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916544848'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
            launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )
        except Exception as exc:
            tb = capture_traceback()
            proposals = _updated_proposal_previews()
            if not batch_created:
                release_unlaunched_once_per_keys(
                    lumberjack_name=lumberjack_name,
                    chop_name=chop.name,
                    run_id=run_id,
                    accepted_proposals=accepted_proposals,
                    successful_launches=successful_launches,
                )
            partial_launch = bool(successful_launches) or batch_created
            finalize_script_chop_run(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                started_at=started_at,
                status="launched" if partial_launch else "action_failed",
                exit_code=0,
>               agent_pid=(int(successful_launches[0]["pid"]) if partial_launch else None),
                               ^^^^^^^^^^^^^^^^^^^^^^
                error=exc,
                tb=tb,
                result_file=result_path.name,
                structured_result=structured_result,
                proposals=proposals,
                launches=successful_launches,
                dry_run=False,
                active=partial_launch,
                preflight=preflight,
            )
E           IndexError: list index out of range

src/sase/axe/chop_runner_script_result_launch.py:179: IndexError
__ test_explicit_agent_name_collision_relinks_later_wait_and_keeps_launching ___
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

lumberjack_name = 'audits'
chop = ChopConfig(name='audit', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234954_276224'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 54, 276224, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_explicit_agent_name_colli0/.sase/axe/lumberjacks/audits/chops/audit/runs/20261117T234954_276224.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id='root', prompt='Prepare.', workspace='git:sase', agent_name='audit.prepare'...clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on='audit', wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id='root', prompt='Prepare.', workspace='git:sase', agent_name='audit.prepare'...clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on='audit', wait_runners=None)]
proposals = [{'index': 0, 'id': 'root', 'agent_name': 'audit.prepare', 'clan': None, ...}, {'index': 1, 'id': 'audit', 'agent_name': 'audit.taken', 'clan': None, ...}, {'index': 2, 'id': None, 'agent_name': 'audit.summary', 'clan': None, ...}]
once_per_decisions = {}
once_per_effective_waits = {0: None, 1: 'root', 2: 'audit'}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id='root', prompt='Prepare.', workspace='git:sase...es_clan=False, clan_summary=None, prompt='#git:sase\n%id(audit.summary, tribe=chop)\n%wait:audit.taken\nSummarize.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916542496'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
>           launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )

src/sase/axe/chop_runner_script_result_launch.py:145: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_proposal_launch.py:935: in launch_chop_proposals
    result = _call_with_supported_kwargs(
src/sase/axe/chop_proposal_launch.py:66: in _call_with_supported_kwargs
    return function(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1176: in __call__
    return self._mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1180: in _mock_call
    return self._execute_mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <MagicMock name='launch_agent_from_cwd' id='140300916542496'>
args = ('#git:sase\n%id(audit.prepare, tribe=chop)\nPrepare.\n',)
kwargs = {'extra_env': {'SASE_CHOP_LUMBERJACK': 'audits', 'SASE_CHOP_NAME': 'audit', 'SASE_CHOP_RUN_ID': '20261117T234954_27622...9a85342980>, 'on_agent_plan_prepared': <function launch_chop_proposals.<locals>._plan_prepared at 0x7f9a85342350>, ...}

    def _execute_mock_call(self, /, *args, **kwargs):
        # separate from _increment_mock_call so that awaited functions are
        # executed separately from their call, also AsyncMock overrides this method
    
        effect = self.side_effect
        if effect is not None:
            if _is_exception(effect):
                raise effect
            elif not _callable(effect):
                result = next(effect)
                if _is_exception(result):
                    raise result
            else:
>               result = effect(*args, **kwargs)
                         ^^^^^^^^^^^^^^^^^^^^^^^
E               TypeError: test_explicit_agent_name_collision_relinks_later_wait_and_keeps_launching.<locals>._launch() got an unexpected keyword argument 'before_agent_spawn'

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1247: TypeError

During handling of the above exception, another exception occurred:

temp_state_dir = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_explicit_agent_name_colli0/.sase/axe')
tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_explicit_agent_name_colli0')

    def test_explicit_agent_name_collision_relinks_later_wait_and_keeps_launching(
        temp_state_dir: Path,
        tmp_path: Path,
    ) -> None:
        _result_script(
            tmp_path,
            "audit",
            {
                "schema_version": 1,
                "status": "ok",
                "proposed_launches": [
                    {
                        "id": "root",
                        "prompt": "Prepare.",
                        "workspace": "git:sase",
                        "agent_name": "audit.prepare",
                    },
                    {
                        "id": "audit",
                        "prompt": "Audit.",
                        "workspace": "git:sase",
                        "agent_name": "audit.taken",
                        "wait_on": "root",
                    },
                    {
                        "prompt": "Summarize.",
                        "workspace": "git:sase",
                        "agent_name": "audit.summary",
                        "wait_on": "audit",
                    },
                ],
            },
        )
        calls: list[str] = []
    
        def _launch(
            prompt: str, *, extra_env: dict[str, str], origin: object = None
        ) -> SimpleNamespace:
            del extra_env, origin
            calls.append(prompt)
            if len(calls) == 2:
                raise AgentNameLaunchCollisionError("audit.taken", "audit.taken1")
            return SimpleNamespace(
                pid=300 + len(calls),
                agent_name="actual.root" if len(calls) == 1 else "actual.summary",
            )
    
        with (
            patch("sase.axe.chop_runner.find_all_patches", return_value=[]),
            patch("sase.axe.chop_runner.launch_agent_from_cwd", side_effect=_launch),
        ):
>           outcome = run_configured_chop_once(
                lumberjack_name="audits",
                chop=ChopConfig(name="audit", description=""),
                axe_config=_config(tmp_path),
            )

tests/test_axe_chop_name_collisions.py:167: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_runner.py:155: in run_configured_chop_once
    return _run_script_chop_once(
src/sase/axe/chop_runner.py:103: in _run_script_chop_once
    return run_script_chop_once(
src/sase/axe/chop_runner_script.py:466: in run_script_chop_once
    return process_script_chop_result(
src/sase/axe/chop_runner_script_result.py:408: in process_script_chop_result
    return launch_accepted_script_chop_proposals(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

lumberjack_name = 'audits'
chop = ChopConfig(name='audit', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234954_276224'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 54, 276224, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_explicit_agent_name_colli0/.sase/axe/lumberjacks/audits/chops/audit/runs/20261117T234954_276224.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id='root', prompt='Prepare.', workspace='git:sase', agent_name='audit.prepare'...clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on='audit', wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id='root', prompt='Prepare.', workspace='git:sase', agent_name='audit.prepare'...clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on='audit', wait_runners=None)]
proposals = [{'index': 0, 'id': 'root', 'agent_name': 'audit.prepare', 'clan': None, ...}, {'index': 1, 'id': 'audit', 'agent_name': 'audit.taken', 'clan': None, ...}, {'index': 2, 'id': None, 'agent_name': 'audit.summary', 'clan': None, ...}]
once_per_decisions = {}
once_per_effective_waits = {0: None, 1: 'root', 2: 'audit'}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id='root', prompt='Prepare.', workspace='git:sase...es_clan=False, clan_summary=None, prompt='#git:sase\n%id(audit.summary, tribe=chop)\n%wait:audit.taken\nSummarize.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916542496'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
            launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )
        except Exception as exc:
            tb = capture_traceback()
            proposals = _updated_proposal_previews()
            if not batch_created:
                release_unlaunched_once_per_keys(
                    lumberjack_name=lumberjack_name,
                    chop_name=chop.name,
                    run_id=run_id,
                    accepted_proposals=accepted_proposals,
                    successful_launches=successful_launches,
                )
            partial_launch = bool(successful_launches) or batch_created
            finalize_script_chop_run(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                started_at=started_at,
                status="launched" if partial_launch else "action_failed",
                exit_code=0,
>               agent_pid=(int(successful_launches[0]["pid"]) if partial_launch else None),
                               ^^^^^^^^^^^^^^^^^^^^^^
                error=exc,
                tb=tb,
                result_file=result_path.name,
                structured_result=structured_result,
                proposals=proposals,
                launches=successful_launches,
                dry_run=False,
                active=partial_launch,
                preflight=preflight,
            )
E           IndexError: list index out of range

src/sase/axe/chop_runner_script_result_launch.py:179: IndexError
___________ test_derived_agent_name_collision_remains_action_failed ____________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

lumberjack_name = 'audits'
chop = ChopConfig(name='audit', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234954_578901'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 54, 578901, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_derived_agent_name_collis0/.sase/axe/lumberjacks/audits/chops/audit/runs/20261117T234954_578901.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Audit.', workspace='git:sase', agent_name='chop.audit.4_57890...e, clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=None, wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Audit.', workspace='git:sase', agent_name='chop.audit.4_57890...e, clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=None, wait_runners=None)]
proposals = [{'index': 0, 'id': None, 'agent_name': 'chop.audit.4_578901.1', 'clan': None, ...}]
once_per_decisions = {}, once_per_effective_waits = {0: None}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id=None, prompt='Audit.', workspace='git:sase', a...id=None, declares_clan=False, clan_summary=None, prompt='#git:sase\n%id(chop.audit.4_578901.1, tribe=chop)\nAudit.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916544176'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
>           launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )

src/sase/axe/chop_runner_script_result_launch.py:145: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_proposal_launch.py:935: in launch_chop_proposals
    result = _call_with_supported_kwargs(
src/sase/axe/chop_proposal_launch.py:66: in _call_with_supported_kwargs
    return function(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1176: in __call__
    return self._mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1180: in _mock_call
    return self._execute_mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <MagicMock name='launch_agent_from_cwd' id='140300916544176'>
args = ('#git:sase\n%id(chop.audit.4_578901.1, tribe=chop)\nAudit.\n',)
kwargs = {'extra_env': {'SASE_CHOP_LUMBERJACK': 'audits', 'SASE_CHOP_NAME': 'audit', 'SASE_CHOP_RUN_ID': '20261117T234954_57890...9a41d60670>, 'on_agent_plan_prepared': <function launch_chop_proposals.<locals>._plan_prepared at 0x7f9a41d63c10>, ...}

    def _execute_mock_call(self, /, *args, **kwargs):
        # separate from _increment_mock_call so that awaited functions are
        # executed separately from their call, also AsyncMock overrides this method
    
        effect = self.side_effect
        if effect is not None:
            if _is_exception(effect):
>               raise effect
E               sase.agent.launch_validation.AgentNameLaunchCollisionError: Agent name 'audit.run' is taken. Try 'audit.run1'.

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1241: AgentNameLaunchCollisionError

During handling of the above exception, another exception occurred:

temp_state_dir = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_derived_agent_name_collis0/.sase/axe')
tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_derived_agent_name_collis0')

    def test_derived_agent_name_collision_remains_action_failed(
        temp_state_dir: Path,
        tmp_path: Path,
    ) -> None:
        _result_script(
            tmp_path,
            "audit",
            {
                "schema_version": 1,
                "status": "ok",
                "proposed_launches": [
                    {
                        "prompt": "Audit.",
                        "workspace": "git:sase",
                    }
                ],
            },
        )
    
        with (
            patch("sase.axe.chop_runner.find_all_patches", return_value=[]),
            patch(
                "sase.axe.chop_runner.launch_agent_from_cwd",
                side_effect=AgentNameLaunchCollisionError("audit.run", "audit.run1"),
            ),
        ):
>           outcome = run_configured_chop_once(
                lumberjack_name="audits",
                chop=ChopConfig(name="audit", description=""),
                axe_config=_config(tmp_path),
            )

tests/test_axe_chop_name_collisions.py:214: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_runner.py:155: in run_configured_chop_once
    return _run_script_chop_once(
src/sase/axe/chop_runner.py:103: in _run_script_chop_once
    return run_script_chop_once(
src/sase/axe/chop_runner_script.py:466: in run_script_chop_once
    return process_script_chop_result(
src/sase/axe/chop_runner_script_result.py:408: in process_script_chop_result
    return launch_accepted_script_chop_proposals(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

lumberjack_name = 'audits'
chop = ChopConfig(name='audit', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234954_578901'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 54, 578901, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_derived_agent_name_collis0/.sase/axe/lumberjacks/audits/chops/audit/runs/20261117T234954_578901.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Audit.', workspace='git:sase', agent_name='chop.audit.4_57890...e, clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=None, wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Audit.', workspace='git:sase', agent_name='chop.audit.4_57890...e, clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=None, wait_runners=None)]
proposals = [{'index': 0, 'id': None, 'agent_name': 'chop.audit.4_578901.1', 'clan': None, ...}]
once_per_decisions = {}, once_per_effective_waits = {0: None}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id=None, prompt='Audit.', workspace='git:sase', a...id=None, declares_clan=False, clan_summary=None, prompt='#git:sase\n%id(chop.audit.4_578901.1, tribe=chop)\nAudit.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916544176'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
            launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )
        except Exception as exc:
            tb = capture_traceback()
            proposals = _updated_proposal_previews()
            if not batch_created:
                release_unlaunched_once_per_keys(
                    lumberjack_name=lumberjack_name,
                    chop_name=chop.name,
                    run_id=run_id,
                    accepted_proposals=accepted_proposals,
                    successful_launches=successful_launches,
                )
            partial_launch = bool(successful_launches) or batch_created
            finalize_script_chop_run(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                started_at=started_at,
                status="launched" if partial_launch else "action_failed",
                exit_code=0,
>               agent_pid=(int(successful_launches[0]["pid"]) if partial_launch else None),
                               ^^^^^^^^^^^^^^^^^^^^^^
                error=exc,
                tb=tb,
                result_file=result_path.name,
                structured_result=structured_result,
                proposals=proposals,
                launches=successful_launches,
                dry_run=False,
                active=partial_launch,
                preflight=preflight,
            )
E           IndexError: list index out of range

src/sase/axe/chop_runner_script_result_launch.py:179: IndexError
_____________ test_clan_agent_name_collision_remains_action_failed _____________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

lumberjack_name = 'split'
chop = ChopConfig(name='split', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234954_870927'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 54, 870927, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_clan_agent_name_collision0/.sase/axe/lumberjacks/split/chops/split/runs/20261117T234954_870927.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Split.', workspace='git:sase', agent_name='split.member', exp...', clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=None, wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Split.', workspace='git:sase', agent_name='split.member', exp...', clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=None, wait_runners=None)]
proposals = [{'index': 0, 'id': None, 'agent_name': 'split-0.split.member', 'clan': 'split-0', ...}]
once_per_decisions = {}, once_per_effective_waits = {0: None}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id=None, prompt='Split.', workspace='git:sase', a...ares_clan=True, clan_summary=None, prompt='#git:sase\n%id:split-0.split.member\n%clan(split-0, tribe=chop)\nSplit.\n')]
launch_agent_from_cwd_fn = <function launch_agent_from_cwd at 0x7f9a89ef50c0>
launch_agents_from_cwd_fn = <MagicMock name='launch_agents_from_cwd' id='140300916547536'>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
>           launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )

src/sase/axe/chop_runner_script_result_launch.py:145: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_proposal_launch.py:851: in launch_chop_proposals
    _call_with_supported_kwargs(
src/sase/axe/chop_proposal_launch.py:66: in _call_with_supported_kwargs
    return function(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1176: in __call__
    return self._mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1180: in _mock_call
    return self._execute_mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <MagicMock name='launch_agents_from_cwd' id='140300916547536'>
args = ('#git:sase\n%id:split-0.split.member\n%clan(split-0, tribe=chop)\nSplit.\n',)
kwargs = {'segment_extra_env': [{'SASE_CHOP_LUMBERJACK': 'split', 'SASE_CHOP_NAME': 'split', 'SASE_CHOP_RUN_ID': '20261117T2349...9a41d63b60>, 'on_agent_plan_prepared': <function launch_chop_proposals.<locals>._plan_prepared at 0x7f9a41d61b10>, ...}

    def _execute_mock_call(self, /, *args, **kwargs):
        # separate from _increment_mock_call so that awaited functions are
        # executed separately from their call, also AsyncMock overrides this method
    
        effect = self.side_effect
        if effect is not None:
            if _is_exception(effect):
>               raise effect
E               sase.agent.launch_validation.AgentNameLaunchCollisionError: Agent name 'split-0.split.member' is taken. Try 'split-0.split.member1'.

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1241: AgentNameLaunchCollisionError

During handling of the above exception, another exception occurred:

temp_state_dir = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_clan_agent_name_collision0/.sase/axe')
tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_clan_agent_name_collision0')

    def test_clan_agent_name_collision_remains_action_failed(
        temp_state_dir: Path,
        tmp_path: Path,
    ) -> None:
        _result_script(
            tmp_path,
            "split",
            {
                "schema_version": 1,
                "status": "ok",
                "proposed_launches": [
                    {
                        "prompt": "Split.",
                        "workspace": "git:sase",
                        "agent_name": "split.member",
                        "clan": "split-@",
                    }
                ],
            },
        )
    
        with (
            patch("sase.axe.chop_runner.find_all_patches", return_value=[]),
            patch(
                "sase.axe.chop_runner.launch_agents_from_cwd",
                side_effect=AgentNameLaunchCollisionError(
                    "split-0.split.member",
                    "split-0.split.member1",
                ),
            ),
        ):
>           outcome = run_configured_chop_once(
                lumberjack_name="split",
                chop=ChopConfig(name="split", description=""),
                axe_config=_config(tmp_path),
            )

tests/test_axe_chop_name_collisions.py:260: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_runner.py:155: in run_configured_chop_once
    return _run_script_chop_once(
src/sase/axe/chop_runner.py:103: in _run_script_chop_once
    return run_script_chop_once(
src/sase/axe/chop_runner_script.py:466: in run_script_chop_once
    return process_script_chop_result(
src/sase/axe/chop_runner_script_result.py:408: in process_script_chop_result
    return launch_accepted_script_chop_proposals(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

lumberjack_name = 'split'
chop = ChopConfig(name='split', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T234954_870927'
started_at = datetime.datetime(2026, 11, 17, 23, 49, 54, 870927, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_clan_agent_name_collision0/.sase/axe/lumberjacks/split/chops/split/runs/20261117T234954_870927.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Split.', workspace='git:sase', agent_name='split.member', exp...', clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=None, wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id=None, prompt='Split.', workspace='git:sase', agent_name='split.member', exp...', clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=None, wait_runners=None)]
proposals = [{'index': 0, 'id': None, 'agent_name': 'split-0.split.member', 'clan': 'split-0', ...}]
once_per_decisions = {}, once_per_effective_waits = {0: None}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id=None, prompt='Split.', workspace='git:sase', a...ares_clan=True, clan_summary=None, prompt='#git:sase\n%id:split-0.split.member\n%clan(split-0, tribe=chop)\nSplit.\n')]
launch_agent_from_cwd_fn = <function launch_agent_from_cwd at 0x7f9a89ef50c0>
launch_agents_from_cwd_fn = <MagicMock name='launch_agents_from_cwd' id='140300916547536'>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
            launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )
        except Exception as exc:
            tb = capture_traceback()
            proposals = _updated_proposal_previews()
            if not batch_created:
                release_unlaunched_once_per_keys(
                    lumberjack_name=lumberjack_name,
                    chop_name=chop.name,
                    run_id=run_id,
                    accepted_proposals=accepted_proposals,
                    successful_launches=successful_launches,
                )
            partial_launch = bool(successful_launches) or batch_created
            finalize_script_chop_run(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                started_at=started_at,
                status="launched" if partial_launch else "action_failed",
                exit_code=0,
>               agent_pid=(int(successful_launches[0]["pid"]) if partial_launch else None),
                               ^^^^^^^^^^^^^^^^^^^^^^
                error=exc,
                tb=tb,
                result_file=result_path.name,
                structured_result=structured_result,
                proposals=proposals,
                launches=successful_launches,
                dry_run=False,
                active=partial_launch,
                preflight=preflight,
            )
E           IndexError: list index out of range

src/sase/axe/chop_runner_script_result_launch.py:179: IndexError
____________ test_clan_partial_launch_keeps_started_member_recorded ____________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

temp_state_dir = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_clan_partial_launch_keeps0/.sase/axe')
tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_clan_partial_launch_keeps0')

    def test_clan_partial_launch_keeps_started_member_recorded(
        temp_state_dir: Path,
        tmp_path: Path,
    ) -> None:
        result_script(
            tmp_path,
            "split",
            {
                "schema_version": 1,
                "status": "ok",
                "proposed_launches": [
                    {
                        "prompt": "First.",
                        "workspace": "git:sase",
                        "agent_name": "first",
                        "clan": "toobig-@",
                        "dedupe_key": "split:first",
                    },
                    {
                        "prompt": "Second.",
                        "workspace": "git:sase",
                        "agent_name": "second",
                        "clan": "toobig-@",
                        "dedupe_key": "split:second",
                    },
                ],
            },
        )
        started = SimpleNamespace(
            pid=401,
            agent_name="toobig-0.first",
            timestamp="260719_130000",
        )
    
        def _fail_batch(*args: object, **kwargs: object) -> object:
            del args, kwargs
            raise MultiPromptPartialLaunchError(
                [started],
                RuntimeError("second spawn failed"),
            )
    
        with (
            patch("sase.axe.chop_runner.find_all_patches", return_value=[]),
            patch("sase.axe.chop_runner.launch_agents_from_cwd", side_effect=_fail_batch),
        ):
            outcome = run_configured_chop_once(
                lumberjack_name="split",
                chop=ChopConfig(name="split", description=""),
                axe_config=config(tmp_path),
            )
    
>       assert outcome.status == "action_failed"
E       AssertionError: assert 'launched' == 'action_failed'
E         
E         - action_failed
E         + launched

tests/test_axe_chop_proposal_launch_runner.py:73: AssertionError
_________ test_runner_launches_proposals_in_order_with_wait_directive __________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

lumberjack_name = 'docs'
chop = ChopConfig(name='docs', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[]..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T235003_445636'
started_at = datetime.datetime(2026, 11, 17, 23, 50, 3, 445636, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_launches_proposals0/.sase/axe/lumberjacks/docs/chops/docs/runs/20261117T235003_445636.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id='refresh', prompt='Refresh.', workspace='git:sase', agent_name='chop.docs.3...None, clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=0, wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id='refresh', prompt='Refresh.', workspace='git:sase', agent_name='chop.docs.3...None, clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=0, wait_runners=None)]
proposals = [{'index': 0, 'id': 'refresh', 'agent_name': 'chop.docs.3_445636.1', 'clan': None, ...}, {'index': 1, 'id': None, 'agent_name': 'chop.docs.3_445636.2', 'clan': None, ...}]
once_per_decisions = {}, once_per_effective_waits = {0: None, 1: 0}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id='refresh', prompt='Refresh.', workspace='git:s..., clan_summary=None, prompt='#git:sase\n%id(chop.docs.3_445636.2, tribe=chop)\n%wait:chop.docs.3_445636.1\nPolish.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916553248'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
>           launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )

src/sase/axe/chop_runner_script_result_launch.py:145: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_proposal_launch.py:935: in launch_chop_proposals
    result = _call_with_supported_kwargs(
src/sase/axe/chop_proposal_launch.py:66: in _call_with_supported_kwargs
    return function(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1176: in __call__
    return self._mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1180: in _mock_call
    return self._execute_mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <MagicMock name='launch_agent_from_cwd' id='140300916553248'>
args = ('#git:sase\n%id(chop.docs.3_445636.1, tribe=chop)\nRefresh.\n',)
kwargs = {'extra_env': {'MODE': 'refresh', 'SASE_CHOP_LUMBERJACK': 'docs', 'SASE_CHOP_NAME': 'docs', 'SASE_CHOP_RUN_ID': '20261...9a41774250>, 'on_agent_plan_prepared': <function launch_chop_proposals.<locals>._plan_prepared at 0x7f9a41774930>, ...}

    def _execute_mock_call(self, /, *args, **kwargs):
        # separate from _increment_mock_call so that awaited functions are
        # executed separately from their call, also AsyncMock overrides this method
    
        effect = self.side_effect
        if effect is not None:
            if _is_exception(effect):
                raise effect
            elif not _callable(effect):
                result = next(effect)
                if _is_exception(result):
                    raise result
            else:
>               result = effect(*args, **kwargs)
                         ^^^^^^^^^^^^^^^^^^^^^^^
E               TypeError: test_runner_launches_proposals_in_order_with_wait_directive.<locals>._launch() got an unexpected keyword argument 'before_agent_spawn'

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1247: TypeError

During handling of the above exception, another exception occurred:

temp_state_dir = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_launches_proposals0/.sase/axe')
tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_launches_proposals0')

    def test_runner_launches_proposals_in_order_with_wait_directive(
        temp_state_dir: Path,
        tmp_path: Path,
    ) -> None:
        result_script(
            tmp_path,
            "docs",
            {
                "schema_version": 1,
                "status": "ok",
                "proposed_launches": [
                    {
                        "id": "refresh",
                        "prompt": "Refresh.",
                        "workspace": "git:sase",
                        "env": {"MODE": "refresh"},
                    },
                    {
                        "prompt": "Polish.",
                        "workspace": "git:sase",
                        "wait_on": 0,
                    },
                ],
            },
        )
        calls: list[tuple[str, dict[str, str]]] = []
    
        def _launch(
            prompt: str, *, extra_env: dict[str, str], origin: object = None
        ) -> SimpleNamespace:
            index = len(calls)
            calls.append((prompt, extra_env))
            return SimpleNamespace(
                pid=100 + index,
                agent_name=f"actual.{index + 1}",
                workspace_num=index + 1,
                workspace_dir=f"/workspace/{index + 1}",
                project_name="sase",
                workflow_name=f"ace(run)-{index}",
                cl_name="sase",
                timestamp=f"260718_12000{index}",
                artifacts_dir=f"/artifacts/{index}",
            )
    
        with (
            patch("sase.axe.chop_runner.find_all_patches", return_value=[]),
            patch("sase.axe.chop_runner.launch_agent_from_cwd", side_effect=_launch),
        ):
>           outcome = run_configured_chop_once(
                lumberjack_name="docs",
                chop=ChopConfig(name="docs", description=""),
                axe_config=config(tmp_path),
            )

tests/test_axe_chop_proposal_launch_runner.py:131: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_runner.py:155: in run_configured_chop_once
    return _run_script_chop_once(
src/sase/axe/chop_runner.py:103: in _run_script_chop_once
    return run_script_chop_once(
src/sase/axe/chop_runner_script.py:466: in run_script_chop_once
    return process_script_chop_result(
src/sase/axe/chop_runner_script_result.py:408: in process_script_chop_result
    return launch_accepted_script_chop_proposals(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

lumberjack_name = 'docs'
chop = ChopConfig(name='docs', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[]..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T235003_445636'
started_at = datetime.datetime(2026, 11, 17, 23, 50, 3, 445636, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_launches_proposals0/.sase/axe/lumberjacks/docs/chops/docs/runs/20261117T235003_445636.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id='refresh', prompt='Refresh.', workspace='git:sase', agent_name='chop.docs.3...None, clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=0, wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id='refresh', prompt='Refresh.', workspace='git:sase', agent_name='chop.docs.3...None, clan_summary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key=None, wait_on=0, wait_runners=None)]
proposals = [{'index': 0, 'id': 'refresh', 'agent_name': 'chop.docs.3_445636.1', 'clan': None, ...}, {'index': 1, 'id': None, 'agent_name': 'chop.docs.3_445636.2', 'clan': None, ...}]
once_per_decisions = {}, once_per_effective_waits = {0: None, 1: 0}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id='refresh', prompt='Refresh.', workspace='git:s..., clan_summary=None, prompt='#git:sase\n%id(chop.docs.3_445636.2, tribe=chop)\n%wait:chop.docs.3_445636.1\nPolish.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916553248'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
            launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )
        except Exception as exc:
            tb = capture_traceback()
            proposals = _updated_proposal_previews()
            if not batch_created:
                release_unlaunched_once_per_keys(
                    lumberjack_name=lumberjack_name,
                    chop_name=chop.name,
                    run_id=run_id,
                    accepted_proposals=accepted_proposals,
                    successful_launches=successful_launches,
                )
            partial_launch = bool(successful_launches) or batch_created
            finalize_script_chop_run(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                started_at=started_at,
                status="launched" if partial_launch else "action_failed",
                exit_code=0,
>               agent_pid=(int(successful_launches[0]["pid"]) if partial_launch else None),
                               ^^^^^^^^^^^^^^^^^^^^^^
                error=exc,
                tb=tb,
                result_file=result_path.name,
                structured_result=structured_result,
                proposals=proposals,
                launches=successful_launches,
                dry_run=False,
                active=partial_launch,
                preflight=preflight,
            )
E           IndexError: list index out of range

src/sase/axe/chop_runner_script_result_launch.py:179: IndexError
___________ test_runner_launches_with_wait_relinked_across_duplicate ___________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

lumberjack_name = 'docs'
chop = ChopConfig(name='docs', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[]..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T235003_768395'
started_at = datetime.datetime(2026, 11, 17, 23, 50, 3, 768395, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_launches_with_wait0/.sase/axe/lumberjacks/docs/chops/docs/runs/20261117T235003_768395.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id='root', prompt='Root.', workspace='git:sase', agent_name='chop.docs.3_76839...mary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key='docs:tail', wait_on='middle', wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id='root', prompt='Root.', workspace='git:sase', agent_name='chop.docs.3_76839...ummary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key='docs:tail', wait_on='root', wait_runners=None)]
proposals = [{'index': 0, 'id': 'root', 'agent_name': 'chop.docs.3_768395.1', 'clan': None, ...}, {'index': 1, 'id': 'middle', 'ag...ocs.3_768395.2', 'clan': None, ...}, {'index': 2, 'id': None, 'agent_name': 'chop.docs.3_768395.3', 'clan': None, ...}]
once_per_decisions = {1: {'outcome': 'duplicate', 'reason': 'once-per key `docs:middle` was already seen', 'key': 'docs:middle'}, 2: {'outcome': 'accept', 'reason': "wait dependency 'middle' was deduped; relinked to 'root'", 'key': 'docs:tail'}}
once_per_effective_waits = {0: None, 2: 'root'}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id='root', prompt='Root.', workspace='git:sase', ...se, clan_summary=None, prompt='#git:sase\n%id(chop.docs.3_768395.3, tribe=chop)\n%wait:chop.docs.3_768395.1\nTail.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916552912'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
>           launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )

src/sase/axe/chop_runner_script_result_launch.py:145: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_proposal_launch.py:935: in launch_chop_proposals
    result = _call_with_supported_kwargs(
src/sase/axe/chop_proposal_launch.py:66: in _call_with_supported_kwargs
    return function(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1176: in __call__
    return self._mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1180: in _mock_call
    return self._execute_mock_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <MagicMock name='launch_agent_from_cwd' id='140300916552912'>
args = ('#git:sase\n%id(chop.docs.3_768395.1, tribe=chop)\nRoot.\n',)
kwargs = {'extra_env': {'SASE_CHOP_LUMBERJACK': 'docs', 'SASE_CHOP_NAME': 'docs', 'SASE_CHOP_RUN_ID': '20261117T235003_768395',...9a84de7ed0>, 'on_agent_plan_prepared': <function launch_chop_proposals.<locals>._plan_prepared at 0x7f9a84de5d20>, ...}

    def _execute_mock_call(self, /, *args, **kwargs):
        # separate from _increment_mock_call so that awaited functions are
        # executed separately from their call, also AsyncMock overrides this method
    
        effect = self.side_effect
        if effect is not None:
            if _is_exception(effect):
                raise effect
            elif not _callable(effect):
                result = next(effect)
                if _is_exception(result):
                    raise result
            else:
>               result = effect(*args, **kwargs)
                         ^^^^^^^^^^^^^^^^^^^^^^^
E               TypeError: test_runner_launches_with_wait_relinked_across_duplicate.<locals>._launch() got an unexpected keyword argument 'before_agent_spawn'

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:1247: TypeError

During handling of the above exception, another exception occurred:

temp_state_dir = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_launches_with_wait0/.sase/axe')
tmp_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_launches_with_wait0')

    def test_runner_launches_with_wait_relinked_across_duplicate(
        temp_state_dir: Path,
        tmp_path: Path,
    ) -> None:
        chop = ChopConfig(name="docs", description="")
        seed = prepare_chop_proposals(
            "docs",
            {
                "proposed_launches": [
                    {
                        "prompt": "Seed.",
                        "workspace": "git:sase",
                        "dedupe_key": "docs:middle",
                    }
                ]
            },
        )
        apply_chop_once_per(
            lumberjack_name="docs",
            chop=chop,
            proposals=seed,
            persist=True,
        )
        result_script(
            tmp_path,
            "docs",
            {
                "schema_version": 1,
                "status": "ok",
                "proposed_launches": [
                    {"id": "root", "prompt": "Root.", "workspace": "git:sase"},
                    {
                        "id": "middle",
                        "prompt": "Middle.",
                        "workspace": "git:sase",
                        "dedupe_key": "docs:middle",
                        "wait_on": "root",
                    },
                    {
                        "prompt": "Tail.",
                        "workspace": "git:sase",
                        "dedupe_key": "docs:tail",
                        "wait_on": "middle",
                    },
                ],
            },
        )
        calls: list[str] = []
    
        def _launch(
            prompt: str, *, extra_env: dict[str, str], origin: object = None
        ) -> SimpleNamespace:
            del extra_env, origin
            index = len(calls)
            calls.append(prompt)
            return SimpleNamespace(
                pid=200 + index,
                agent_name=f"actual.{index + 1}",
            )
    
        with (
            patch("sase.axe.chop_runner.find_all_patches", return_value=[]),
            patch("sase.axe.chop_runner.launch_agent_from_cwd", side_effect=_launch),
        ):
>           outcome = run_configured_chop_once(
                lumberjack_name="docs",
                chop=chop,
                axe_config=config(tmp_path),
            )

tests/test_axe_chop_proposal_launch_runner.py:215: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/chop_runner.py:155: in run_configured_chop_once
    return _run_script_chop_once(
src/sase/axe/chop_runner.py:103: in _run_script_chop_once
    return run_script_chop_once(
src/sase/axe/chop_runner_script.py:466: in run_script_chop_once
    return process_script_chop_result(
src/sase/axe/chop_runner_script_result.py:408: in process_script_chop_result
    return launch_accepted_script_chop_proposals(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

lumberjack_name = 'docs'
chop = ChopConfig(name='docs', description='', script=None, enabled=True, run_every=None, timeout=None, env={}, inhibit_if=[]..._key='', target={}, vars={}, provenance={}, description_summary='', description_body='', source='user', declared_by='')
run_id = '20261117T235003_768395'
started_at = datetime.datetime(2026, 11, 17, 23, 50, 3, 768395, tzinfo=zoneinfo.ZoneInfo(key='America/New_York'))
result_path = PosixPath('/var/tmp/sase-f857384c/pytest-of-bryan/pytest-1/popen-gw5/test_runner_launches_with_wait0/.sase/axe/lumberjacks/docs/chops/docs/runs/20261117T235003_768395.result.json')
chop_verbose = False
preflight = ChopPreflight(outcome='fire', reason='always trigger selected', decision={'schema_version': 1, 'outcome': 'fire', 'rea...er': 'always', 'checkpoint_key': None, 'checkpoint_cursor': None, 'checkpoint_policy': None}, checkpoint_enabled=False)
structured_result = {'schema_version': 1, 'status': 'ok', 'summary': None, 'reason': None, ...}
prepared_proposals = [PreparedChopProposal(index=0, proposal_id='root', prompt='Root.', workspace='git:sase', agent_name='chop.docs.3_76839...mary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key='docs:tail', wait_on='middle', wait_runners=None)]
accepted_proposals = [PreparedChopProposal(index=0, proposal_id='root', prompt='Root.', workspace='git:sase', agent_name='chop.docs.3_76839...ummary=None, tribe='chop', model=None, effort=None, env={}, dedupe_key='docs:tail', wait_on='root', wait_runners=None)]
proposals = [{'index': 0, 'id': 'root', 'agent_name': 'chop.docs.3_768395.1', 'clan': None, ...}, {'index': 1, 'id': 'middle', 'ag...ocs.3_768395.2', 'clan': None, ...}, {'index': 2, 'id': None, 'agent_name': 'chop.docs.3_768395.3', 'clan': None, ...}]
once_per_decisions = {1: {'outcome': 'duplicate', 'reason': 'once-per key `docs:middle` was already seen', 'key': 'docs:middle'}, 2: {'outcome': 'accept', 'reason': "wait dependency 'middle' was deduped; relinked to 'root'", 'key': 'docs:tail'}}
once_per_effective_waits = {0: None, 2: 'root'}
launch_plans = [PlannedChopProposal(proposal=PreparedChopProposal(index=0, proposal_id='root', prompt='Root.', workspace='git:sase', ...se, clan_summary=None, prompt='#git:sase\n%id(chop.docs.3_768395.3, tribe=chop)\n%wait:chop.docs.3_768395.1\nTail.\n')]
launch_agent_from_cwd_fn = <MagicMock name='launch_agent_from_cwd' id='140300916552912'>
launch_agents_from_cwd_fn = <function launch_agents_from_cwd at 0x7f9a89ed6090>
pause_requested_fn = None

    def launch_accepted_script_chop_proposals(
        *,
        lumberjack_name: str,
        chop: ChopConfig,
        run_id: str,
        started_at: datetime,
        result_path: Path,
        chop_verbose: bool,
        preflight: ChopPreflight,
        structured_result: dict[str, Any],
        prepared_proposals: list[Any],
        accepted_proposals: list[Any],
        proposals: list[dict[str, Any]],
        once_per_decisions: dict[int, dict[str, str]],
        once_per_effective_waits: dict[int, int | str | None],
        launch_plans: list[Any],
        launch_agent_from_cwd_fn: Callable[..., Any] | None,
        launch_agents_from_cwd_fn: Callable[..., Any] | None,
        pause_requested_fn: Callable[[], bool] | None = None,
    ) -> ChopRunOutcome:
        """Launch accepted proposals and finalize the script-chop run."""
        successful_launches: list[dict[str, Any]] = []
        batch_created = False
    
        def _batch_created(_batch_id: str) -> None:
            nonlocal batch_created
            batch_created = True
    
        collision_decisions: dict[int, dict[str, str]] = {}
        collision_effective_waits: dict[int, int | str | None] = {}
    
        def _record_collision_skip(
            proposal: Any,
            reason: str,
            effective_wait: int | str | None,
        ) -> None:
            collision_decisions[proposal.index] = {
                "outcome": "name_collision",
                "reason": reason,
                "key": proposal.dedupe_key or "",
            }
            collision_effective_waits[proposal.index] = effective_wait
            append_chop_run_output(
                lumberjack_name,
                chop.name,
                run_id,
                (
                    f"Skipped proposal {proposal.index + 1} "
                    f"({proposal.agent_name}): {reason}\n"
                ),
            )
    
        def _updated_proposal_previews() -> list[dict[str, Any]]:
            decisions = dict(once_per_decisions)
            decisions.update(collision_decisions)
            effective_waits = dict(once_per_effective_waits)
            effective_waits.update(collision_effective_waits)
            effective_waits.update(
                {
                    int(launch["index"]): launch.get("wait_on")
                    for launch in successful_launches
                }
            )
            return proposal_previews(
                prepared_proposals,
                once_per_decisions=decisions,
                effective_waits=effective_waits,
                launch_plans=launch_plans,
            )
    
        try:
            launches = launch_chop_proposals(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                proposals=accepted_proposals,
                launch_agent_from_cwd_fn=launch_agent_from_cwd_fn,
                launch_agents_from_cwd_fn=launch_agents_from_cwd_fn,
                launch_plans=launch_plans,
                launch_recorded_fn=successful_launches.append,
                proposal_skipped_fn=_record_collision_skip,
                run_started_at=started_at,
                preflight=preflight,
                batch_created_fn=_batch_created,
                pause_requested_fn=pause_requested_fn,
            )
        except Exception as exc:
            tb = capture_traceback()
            proposals = _updated_proposal_previews()
            if not batch_created:
                release_unlaunched_once_per_keys(
                    lumberjack_name=lumberjack_name,
                    chop_name=chop.name,
                    run_id=run_id,
                    accepted_proposals=accepted_proposals,
                    successful_launches=successful_launches,
                )
            partial_launch = bool(successful_launches) or batch_created
            finalize_script_chop_run(
                lumberjack_name=lumberjack_name,
                chop_name=chop.name,
                run_id=run_id,
                started_at=started_at,
                status="launched" if partial_launch else "action_failed",
                exit_code=0,
>               agent_pid=(int(successful_launches[0]["pid"]) if partial_launch else None),
                               ^^^^^^^^^^^^^^^^^^^^^^
                error=exc,
                tb=tb,
                result_file=result_path.name,
                structured_result=structured_result,
                proposals=proposals,
                launches=successful_launches,
                dry_run=False,
                active=partial_launch,
                preflight=preflight,
            )
E           IndexError: list index out of range

src/sase/axe/chop_runner_script_result_launch.py:179: IndexError
________________ test_tui_app_import_stays_under_startup_budget ________________
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python

request = <FixtureRequest for <Function test_tui_app_import_stays_under_startup_budget>>

    def test_tui_app_import_stays_under_startup_budget(
        request: pytest.FixtureRequest,
    ) -> None:
        """Importing the app should not pull known heavy deferred profile edges."""
    
        cache = _footprint_cache(request.config)
        last_elapsed = 0.0
        last_footprint = 0
        last_count = 0
        for _ in range(2):
>           measurement = _measure_tui_app_import(cache)
                          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_app_import_budget.py:434: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/test_app_import_budget.py:258: in _measure_tui_app_import
    _assert_footprint_budget(measurement)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

measurement = ImportMeasurement(elapsed_seconds=2.0161043050000003, module_count=3461, first_party_modules=('sase', 'sase._git_remot...'sase.workspace_provider.registry': 4965, 'sase.workspace_provider.store': 7540, 'sase.workspace_provider.utils': 46}))
cap = 11894200

    def _assert_footprint_budget(
        measurement: footprint.ImportMeasurement,
        *,
        cap: int = _MAX_SASE_SOURCE_FOOTPRINT_BYTES,
    ) -> None:
>       assert measurement.footprint_bytes < cap, (
            f"TUI app import loads {measurement.footprint_bytes:,} normalized source "
            f"bytes from {measurement.first_party_count} sase.* modules against the "
            f"{cap:,} cap; attribute the growth with `tools/tui_import_closure --diff "
            f"$(git merge-base HEAD origin/master)` and defer the new edges"
        )
E       AssertionError: TUI app import loads 11,905,092 normalized source bytes from 2787 sase.* modules against the 11,894,200 cap; attribute the growth with `tools/tui_import_closure --diff $(git merge-base HEAD origin/master)` and defer the new edges
E       assert 11905092 < 11894200
E        +  where 11905092 = ImportMeasurement(elapsed_seconds=2.0161043050000003, module_count=3461, first_party_modules=('sase', 'sase._git_remot...'sase.workspace_provider.registry': 4965, 'sase.workspace_provider.store': 7540, 'sase.workspace_provider.utils': 46})).footprint_bytes

tests/ace/tui/test_app_import_budget.py:208: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=2104871) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=2104882) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/macro/workflow_runner.py:529: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/macro/workflow_runner.py:313: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/macro/workflow_runner.py:313: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object _recheck_grammar_key at 0x7fd4171cc590>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object _record_history_async.<locals>._record at 0x7fd40e63c2a0>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=2104917) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object CommandLineScreenSubmissionMixin._submit_worker at 0x7fd439e0ce50>: None
  
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorHostFinalizer::test_genuine_provider_500_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorHostFinalizer::test_genuine_provider_500_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=2104896) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=2104756) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/ace/tui/_agent_archive_column_helpers.py:55: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    row.update(extra)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_axe_chop_batch_store.py::test_stale_and_live_ownership
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/axe/test_axe_chop_batch_store.py:165: DeprecationWarning: This process (pid=2104756) is multi-threaded, use of fork() may lead to deadlocks in the child.
    pid = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_agent_archive_controller_lookup.py::test_overlapping_idle_rebuilds_coalesce_to_one_in_flight
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/ace/tui/util/pump_tasks.py:88: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_prewarm.py::test_complete_idle_prewarms_once_and_idle_tick_skips_compile
  <string>:270: RuntimeWarning: coroutine '_run_archive_request' was never awaited
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=2104756) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
87.09s call     tests/continuation/test_launch_local_capture_chain.py::test_twenty_launch_agent_monitor_cycles_keep_only_local_authored_text
65.51s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
63.99s call     tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows
62.89s call     tests/test_launch_request_staging.py::test_typed_plan_and_continuation_survive_adoption
46.03s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
33.80s call     tests/pager/test_app_actions.py::test_unregistered_attached_kind_falls_back_to_resolve_ref
33.59s call     tests/monitor/test_monitor_start_ack.py::test_startup_sigterm_settles_stopped_without_running_command
31.64s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
27.35s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
24.28s call     tests/fakey/test_agent_hijack_canary.py::test_anonymous_tmp_workflow_hijack_continue_same_workspace
24.18s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
22.27s call     tests/fakey/test_agent_hijack_canary.py::test_monitor_hijack_continue_same_workspace
21.91s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
21.33s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
20.65s call     tests/fakey/test_agent_hijack_canary.py::test_monitor_hijack_rerun_same_workspace
20.50s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
19.74s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
19.50s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
18.45s call     tests/fakey/test_agent_hijack_canary.py::test_session_hijack_chooses_running_member_one
17.93s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
=========================== short test summary info ============================
FAILED tests/history/test_prompt_canonical_text.py::test_single_slot_swarm_records_invocation
FAILED tests/history/test_prompt_canonical_text.py::test_repeat_records_parent_once_and_no_slot_rows
FAILED tests/history/test_prompt_canonical_text.py::test_history_text_replaces_rewritten_query
FAILED tests/history/test_prompt_canonical_text.py::test_plain_single_launch_records_query_unchanged
FAILED tests/history/test_prompt_origin.py::test_single_agent_launch_threads_origin
FAILED tests/history/test_prompt_origin.py::test_chop_env_launch_records_nothing_on_success
FAILED tests/history/test_prompt_origin.py::test_job_process_env_does_not_suppress_typed_launch
FAILED tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
FAILED tests/test_workflow_executor_parallel.py::test_pre_expand_parallel_no_embedded_workflows
FAILED tests/test_axe_chop_clan_launch.py::test_runner_batches_clan_proposals_with_per_member_env_and_full_waits
FAILED tests/test_axe_chop_lifecycle_once_per.py::test_launch_failure_releases_only_unlaunched_once_per_keys
FAILED tests/test_axe_chop_name_collisions.py::test_explicit_agent_name_collision_relinks_later_wait_and_keeps_launching
FAILED tests/test_axe_chop_name_collisions.py::test_derived_agent_name_collision_remains_action_failed
FAILED tests/test_axe_chop_name_collisions.py::test_clan_agent_name_collision_remains_action_failed
FAILED tests/test_axe_chop_proposal_launch_runner.py::test_clan_partial_launch_keeps_started_member_recorded
FAILED tests/test_axe_chop_proposal_launch_runner.py::test_runner_launches_proposals_in_order_with_wait_directive
FAILED tests/test_axe_chop_proposal_launch_runner.py::test_runner_launches_with_wait_relinked_across_duplicate
FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget
=== 18 failed, 61842 passed, 18 skipped, 137 warnings in 1576.19s (0:26:16) ====
error: recipe `test-scoped` failed on line 711 with exit code 1
error: recipe `check` failed on line 992 with exit code 1
failed  exit=1  duration=2250640ms
unattrib  34.6s
triage test (scoped): 1 KNOWN 17 NEW stopped
NEW test (scoped): FAILED tests/test_axe_chop_lifecycle_once_per.py::test_launch_failure_releases_only_unlaunched_once_per_keys — recorded evidence; no owner
NEW test (scoped): FAILED tests/history/test_prompt_origin.py::test_chop_env_launch_records_nothing_on_success — recorded evidence; no owner
NEW test (scoped): FAILED tests/history/test_prompt_canonical_text.py::test_single_slot_swarm_records_invocation — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_axe_chop_proposal_launch_runner.py::test_runner_launches_with_wait_relinked_across_duplicate — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_axe_chop_proposal_launch_runner.py::test_clan_partial_launch_keeps_started_member_recorded — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_axe_chop_name_collisions.py::test_clan_agent_name_collision_remains_action_failed — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_workflow_executor_parallel.py::test_pre_expand_parallel_no_embedded_workflows — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_axe_chop_name_collisions.py::test_explicit_agent_name_collision_relinks_later_wait_and_keeps_launching — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_axe_chop_proposal_launch_runner.py::test_runner_launches_proposals_in_order_with_wait_directive — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_axe_chop_clan_launch.py::test_runner_batches_clan_proposals_with_per_member_env_and_full_waits — recorded evidence; no owner
KNOWN test (scoped): FAILED tests/test_timezone_display_guard.py::test_no_system_clock_display_sites — witness 4601e39cd3f25c5f0c5de8427c8c5b73; no owner
verdict: new_failures — 17 NEW, 1 KNOWN; exit 1

