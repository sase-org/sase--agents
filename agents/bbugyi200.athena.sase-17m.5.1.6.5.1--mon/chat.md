# Chat History - ace-run (sase-17m.5.1.6.5.1--mon)

- **TIMESTAMP:** 2026-09-25 11:38:53 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17m.5.1.6.5.1--mon

## Prompt

sase monitor start --command 'just check' --reason 'Verify retry-visual bead before host completion'

## Response

sase tool run 99cce2f2c13803c4cabf0c2d095575df
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
[sase-core-wheel-cache] miss: no exact cached wheel
[sase-core-wheel-cache] Waiting for the shared build lock for cb7b1929d254 (up to 900s).
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/cb7b1929d2547a55e3690010cdea44b9b4737e377c445f371676831fb5252323/sase_core_rs-0.34.73-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 6ms
Prepared 1 package in 118ms
Uninstalled 1 package in 2ms
Installed 1 package in 10ms
 - sase-core-rs==0.34.73 (from file:///home/bryan/.sase/cache/sase-core-artifacts/8bf65fb3712429aec0795240cc86379b5d8195a9a1dd27b2a954079c821fcdd9/sase_core_rs-0.34.73-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.34.73 (from file:///home/bryan/.sase/cache/sase-core-artifacts/cb7b1929d2547a55e3690010cdea44b9b4737e377c445f371676831fb5252323/sase_core_rs-0.34.73-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: no exact cached wheel
[sase-core-wheel-cache] Waiting for the shared build lock for 74f069bc3318 (up to 900s).
[rust-lsp-install] Installing cached sase-xprompt-lsp from /home/bryan/.sase/cache/sase-core-artifacts/74f069bc331845bdc7c76b10ccf7b4245e0833bca1f85f2cc2c2c45d91277d82/sase-xprompt-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/bin/sase-xprompt-lsp
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.34.71 is missing 28 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] CommandLineGrammar: first appears in sase-core 1bdadab (feat(command-line): CommandLineGrammar resolver and sase adapter); no release tag contains it yet.
[core-floor-probe] capture_agent_clan_record_from_artifacts: first appears in sase-core 7fc3501 (feat(core): durable per-clan record store with scan overlay and bindings); no release tag contains it yet.
[core-floor-probe] fleet_followed_batch_agent_session_promotions: first appears in sase-core b814a0f (refactor(fleet): rename family to agent session with session key acceptance); no release tag contains it yet.
[core-floor-probe] load_agent_clan_record: first appears in sase-core 7fc3501 (feat(core): durable per-clan record store with scan overlay and bindings); no release tag contains it yet.
[core-floor-probe] parse_agent_session_name: first appears in sase-core c5b9c0d (feat(core): additive agent-session rename for identity, launch, holds, and editor surfaces); no release tag contains it yet.
[core-floor-probe] project_tag_apply_selection: first appears in sase-core 096d42a (feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5); release v0.34.73 contains it.
[core-floor-probe] project_tag_expand: first appears in sase-core 096d42a (feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5); release v0.34.73 contains it.
[core-floor-probe] project_tag_resolve: first appears in sase-core 096d42a (feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5); release v0.34.73 contains it.
[core-floor-probe] project_tag_scan: first appears in sase-core 096d42a (feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5); release v0.34.73 contains it.
[core-floor-probe] project_tag_trigger: first appears in sase-core 096d42a (feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5); release v0.34.73 contains it.
[core-floor-probe] provider_usage_list_refresh_reservations: first appears in sase-core cfe1902 (feat!: adaptive admission policy for provider usage); no release tag contains it yet.
[core-floor-probe] provider_usage_mark_hot: first appears in sase-core cfe1902 (feat!: adaptive admission policy for provider usage); no release tag contains it yet.
[core-floor-probe] reconcile_agent_artifact_index_dismissed_agent_session_members: first appears in sase-core ef82848 (feat(core): additive agent-session rename for scan, runtime, lifecycle, runner, and stats wires); no release tag contains it yet.
[core-floor-probe] record_agent_clan_attributes: first appears in sase-core 7fc3501 (feat(core): durable per-clan record store with scan overlay and bindings); no release tag contains it yet.
[core-floor-probe] resolve_agent_clan_launch_defaults: first appears in sase-core 7fc3501 (feat(core): durable per-clan record store with scan overlay and bindings); no release tag contains it yet.
[core-floor-probe] resolve_agent_session_parent: first appears in sase-core c5b9c0d (feat(core): additive agent-session rename for identity, launch, holds, and editor surfaces); no release tag contains it yet.
[core-floor-probe] tool_run_claim: first appears in sase-core 9956773 (feat(tool-run): add reservation, claim, stop requests, and owner-aware settlement); no release tag contains it yet.
[core-floor-probe] tool_run_failures: first appears in sase-core 321e7b4 (feat(triage): pure classification, verdict, stage/settle, and failures aggregation); no release tag contains it yet.
[core-floor-probe] tool_run_observe: first appears in sase-core 4b536cd (feat(tool): add tool_run observe core, reap wire types, and telemetry binding); release v0.34.73 contains it.
[core-floor-probe] tool_run_request_stop: first appears in sase-core 9956773 (feat(tool-run): add reservation, claim, stop requests, and owner-aware settlement); no release tag contains it yet.
[core-floor-probe] tool_run_triage_classify: first appears in sase-core 321e7b4 (feat(triage): pure classification, verdict, stage/settle, and failures aggregation); no release tag contains it yet.
[core-floor-probe] tool_run_triage_extract: first appears in sase-core 8315364 (feat(triage): durable failure items, extractors, normalization, and extract/record/show bindings); no release tag contains it yet.
[core-floor-probe] tool_run_triage_record: first appears in sase-core 8315364 (feat(triage): durable failure items, extractors, normalization, and extract/record/show bindings); no release tag contains it yet.
[core-floor-probe] tool_run_triage_settle: first appears in sase-core 321e7b4 (feat(triage): pure classification, verdict, stage/settle, and failures aggregation); no release tag contains it yet.
[core-floor-probe] tool_run_triage_show: first appears in sase-core 8315364 (feat(triage): durable failure items, extractors, normalization, and extract/record/show bindings); no release tag contains it yet.
[core-floor-probe] tool_run_triage_stage: first appears in sase-core 321e7b4 (feat(triage): pure classification, verdict, stage/settle, and failures aggregation); no release tag contains it yet.
[core-floor-probe] tool_run_triage_verdict: first appears in sase-core 321e7b4 (feat(triage): pure classification, verdict, stage/settle, and failures aggregation); no release tag contains it yet.
[core-floor-probe] update_dismissed_agents_index: first appears in sase-core f226caf (feat(cleanup): add runner_is_live to cleanup target wire (schema 4->5)); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "1bdadab", "name": "CommandLineGrammar", "release": null, "subject": "feat(command-line): CommandLineGrammar resolver and sase adapter"}, {"commit": "7fc3501", "name": "capture_agent_clan_record_from_artifacts", "release": null, "subject": "feat(core): durable per-clan record store with scan overlay and bindings"}, {"commit": "b814a0f", "name": "fleet_followed_batch_agent_session_promotions", "release": null, "subject": "refactor(fleet): rename family to agent session with session key acceptance"}, {"commit": "7fc3501", "name": "load_agent_clan_record", "release": null, "subject": "feat(core): durable per-clan record store with scan overlay and bindings"}, {"commit": "c5b9c0d", "name": "parse_agent_session_name", "release": null, "subject": "feat(core): additive agent-session rename for identity, launch, holds, and editor surfaces"}, {"commit": "096d42a", "name": "project_tag_apply_selection", "release": "v0.34.73", "subject": "feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5"}, {"commit": "096d42a", "name": "project_tag_expand", "release": "v0.34.73", "subject": "feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5"}, {"commit": "096d42a", "name": "project_tag_resolve", "release": "v0.34.73", "subject": "feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5"}, {"commit": "096d42a", "name": "project_tag_scan", "release": "v0.34.73", "subject": "feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5"}, {"commit": "096d42a", "name": "project_tag_trigger", "release": "v0.34.73", "subject": "feat(core-tags): add project_tag scan/resolve/expand/accept with catalog wire v5"}, {"commit": "cfe1902", "name": "provider_usage_list_refresh_reservations", "release": null, "subject": "feat!: adaptive admission policy for provider usage"}, {"commit": "cfe1902", "name": "provider_usage_mark_hot", "release": null, "subject": "feat!: adaptive admission policy for provider usage"}, {"commit": "ef82848", "name": "reconcile_agent_artifact_index_dismissed_agent_session_members", "release": null, "subject": "feat(core): additive agent-session rename for scan, runtime, lifecycle, runner, and stats wires"}, {"commit": "7fc3501", "name": "record_agent_clan_attributes", "release": null, "subject": "feat(core): durable per-clan record store with scan overlay and bindings"}, {"commit": "7fc3501", "name": "resolve_agent_clan_launch_defaults", "release": null, "subject": "feat(core): durable per-clan record store with scan overlay and bindings"}, {"commit": "c5b9c0d", "name": "resolve_agent_session_parent", "release": null, "subject": "feat(core): additive agent-session rename for identity, launch, holds, and editor surfaces"}, {"commit": "9956773", "name": "tool_run_claim", "release": null, "subject": "feat(tool-run): add reservation, claim, stop requests, and owner-aware settlement"}, {"commit": "321e7b4", "name": "tool_run_failures", "release": null, "subject": "feat(triage): pure classification, verdict, stage/settle, and failures aggregation"}, {"commit": "4b536cd", "name": "tool_run_observe", "release": "v0.34.73", "subject": "feat(tool): add tool_run observe core, reap wire types, and telemetry binding"}, {"commit": "9956773", "name": "tool_run_request_stop", "release": null, "subject": "feat(tool-run): add reservation, claim, stop requests, and owner-aware settlement"}, {"commit": "321e7b4", "name": "tool_run_triage_classify", "release": null, "subject": "feat(triage): pure classification, verdict, stage/settle, and failures aggregation"}, {"commit": "8315364", "name": "tool_run_triage_extract", "release": null, "subject": "feat(triage): durable failure items, extractors, normalization, and extract/record/show bindings"}, {"commit": "8315364", "name": "tool_run_triage_record", "release": null, "subject": "feat(triage): durable failure items, extractors, normalization, and extract/record/show bindings"}, {"commit": "321e7b4", "name": "tool_run_triage_settle", "release": null, "subject": "feat(triage): pure classification, verdict, stage/settle, and failures aggregation"}, {"commit": "8315364", "name": "tool_run_triage_show", "release": null, "subject": "feat(triage): durable failure items, extractors, normalization, and extract/record/show bindings"}, {"commit": "321e7b4", "name": "tool_run_triage_stage", "release": null, "subject": "feat(triage): pure classification, verdict, stage/settle, and failures aggregation"}, {"commit": "321e7b4", "name": "tool_run_triage_verdict", "release": null, "subject": "feat(triage): pure classification, verdict, stage/settle, and failures aggregation"}, {"commit": "f226caf", "name": "update_dismissed_agents_index", "release": null, "subject": "feat(cleanup): add runner_is_live to cleanup target wire (schema 4->5)"}], "declared_floor": "0.34.71", "exit_code": 4, "message": "sase-core-rs==0.34.71 is missing 28 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✗ test (scoped)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 4362 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 37s, heartbeat 27s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 31s, heartbeat 30s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 67s, heartbeat 1s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 61s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 97s, heartbeat 1s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 91s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 127s, heartbeat 0s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 121s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 157s, heartbeat 5s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 151s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 187s, heartbeat 9s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 181s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 1 token: holder metadata unavailable; 11 tokens: pid 217866, grant 11, age 217s, heartbeat 4s, argv 'tools/run_pytest scoped'; 10 tokens: pid 219924, grant 11, age 212s, heartbeat 12s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 247s, heartbeat 0s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 242s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 278s, heartbeat 5s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 272s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 308s, heartbeat 5s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 302s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 338s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 332s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 368s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 362s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 398s, heartbeat 2s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 392s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 428s, heartbeat 1s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 422s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 458s, heartbeat 1s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 452s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 488s, heartbeat 1s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 482s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 518s, heartbeat 5s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 512s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 548s, heartbeat 4s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 542s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 578s, heartbeat 4s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 572s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 608s, heartbeat 4s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 602s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 638s, heartbeat 4s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 632s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 668s, heartbeat 4s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 662s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 698s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 692s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 728s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 722s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 758s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 752s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 788s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 782s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 818s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 813s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 848s, heartbeat 2s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 843s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 878s, heartbeat 2s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 873s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 908s, heartbeat 1s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 903s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 938s, heartbeat 1s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 933s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 969s, heartbeat 1s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 963s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 999s, heartbeat 0s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 993s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1029s, heartbeat 5s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1023s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1059s, heartbeat 5s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1053s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 1 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1089s, heartbeat 5s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1083s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1119s, heartbeat 4s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1113s, heartbeat 4s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 20s, heartbeat 15s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1149s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1143s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 50s, heartbeat 45s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1179s, heartbeat 2s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1173s, heartbeat 4s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 80s, heartbeat 76s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1209s, heartbeat 6s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1203s, heartbeat 4s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 110s, heartbeat 106s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1239s, heartbeat 0s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1233s, heartbeat 2s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 140s, heartbeat 136s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1269s, heartbeat 5s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1263s, heartbeat 1s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 170s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1299s, heartbeat 4s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1293s, heartbeat 5s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 200s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1329s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1323s, heartbeat 5s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 230s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1359s, heartbeat 3s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1353s, heartbeat 5s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 260s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-11 worker tokens; 0 tokens were available below the floor. Current holders: 11 tokens: pid 217866, grant 11, age 1389s, heartbeat 4s, argv 'tools/run_pytest scoped'; 11 tokens: pid 219924, grant 11, age 1383s, heartbeat 8s, argv 'tools/run_pytest scoped'; 1 token: pid 600107, grant 1, age 290s, heartbeat 5s, argv 'tools/run_pytest scoped'
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 11/11 workers
11 workers [47383 items]

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
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
.............................s.......................................... [ 24%]
........................................................................ [ 24%]
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
..........s............................................................. [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
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
..........................s............................................. [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
......................................s................................. [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
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
...................................................................F.... [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
.....................s.................................................. [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
..........................................s............................. [ 64%]
................sss.s................................................... [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
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
............s........................................................... [ 68%]
........................................................................ [ 68%]
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
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
.........................................................F.............. [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
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
..........................................................F............. [ 83%]
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
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
.........s.............................................................. [ 89%]
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
.s...................................................................... [ 94%]
......................................s.s............................... [ 95%]
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
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
.......                                                                  [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________ test_inline_caller_group_sigkill_leaves_no_survivors _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-209af3f4/pytest-of-bryan/pytest-11/popen-gw9/test_inline_caller_group_sigki0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fae59366dd0>

    @NEEDS_LINUX
    @NEEDS_SASE
    def test_inline_caller_group_sigkill_leaves_no_survivors(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """A SIGKILL of an inline caller's group leaves nothing behind."""
    
        home = _home(monkeypatch, tmp_path)
        env = _env(home)
        pidfile = tmp_path / "child.pid"
        caller_py = tmp_path / "caller.py"
        caller_py.write_text(
            "import os\n"
            f"os.execv({str(SASE)!r}, [{str(SASE)!r}, 'tool', 'run', '--', "
            f"'sh', '-c', 'echo $$ > {pidfile}; exec sleep 60'])\n",
            encoding="utf-8",
        )
        caller = subprocess.Popen(
            [sys.executable, str(caller_py)],
            env=env,
            cwd=tmp_path,
            start_new_session=True,
            stdout=subprocess.DEVNULL,
            stderr=subprocess.DEVNULL,
        )
        child_pid: int | None = None
        try:
            run = _wait_running(env)
            child_pid = _wait_pidfile(pidfile)
            # Inline children run in their own group (so the wrapper can signal
            # them without signaling itself); the parent-death signal covers the
            # caller-group SIGKILL no handler can catch.
            assert os.getpgid(child_pid) == child_pid
            assert os.getpgid(child_pid) != caller.pid
>           observed = _wait_child_facts(str(run["run_id"]))
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/tool/test_wrapper_fidelity.py:277: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/tool/test_wrapper_fidelity.py:91: in _wait_child_facts
    listed = tool_run_list({"schema_version": 1, "limit": 10})
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

request = {'schema_version': 1, 'limit': 10}, store_path = None
busy_timeout_ms = 250

    def tool_run_list(
        request: Mapping[str, Any] | None = None,
        *,
        store_path: str | None = None,
        busy_timeout_ms: int = 250,
    ) -> dict[str, Any]:
        payload = {"schema_version": 1, "limit": 50}
        if request:
            payload.update(dict(request))
        return dict(
>           require_rust_binding("tool_run_list")(
                store_path or str(tool_run_store_path()),
                payload,
                busy_timeout_ms,
            )
        )
E       RuntimeError: tool run store is busy: database is locked

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/core/tool_run.py:279: RuntimeError
_ test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap _
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-209af3f4/pytest-of-bryan/pytest-11/popen-gw3/test_weight_two_land_agent_ses0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f7bddadc750>

    def test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A ``--next`` authored at creation is dispatched by the real settlement
        path into a controlled fakey successor, and a weight-2 competitor stays
        parked -- proving a gapless handoff -- through the starter's release and
        the monitor's own real completion.
    
        Unlike the former hand-authored variant, ``next_action`` is authored on
        the monitor's own persisted proc request at creation (never injected into
        an in-memory copy afterward), dispatch is driven by the real
        ``settle_proc_shell`` -> ``launch_followup_agent`` ->
        ``claim_ordinary_continuation_dispatch`` reservation/adoption path (only
        the low-level OS process spawn is faked, the same seam every monitor
        lifecycle test in this suite uses), and the successor's weight/priority
        are parsed from its real ``%queue`` prompt prefix rather than hard-coded
        in the spawn stub.
    
        The competitor is released -- not killed -- immediately before the real
        dispatch call, rather than before the monitor's own completion as the
        former variant did: this test found that a competitor left polling
        through the successor's own admission reliably wins that specific
        window (its already-hot poll loop beats the brand-new successor
        thread's first scan), which a fresh weight-2 waiter introduced only
        once the successor is confirmed live cannot do. See PROPOSED FOLLOW-UP
        on this bead for the reproducible gap this uncovered in the
        monitor-to-successor handoff specifically (the starter-to-monitor
        handoff proven gapless above is unaffected).
        """
        import tests.fakey._runner_slot_harness as harness_module
    
        monkeypatch.setattr(harness_module, "_WAIT_TIMEOUT", 5.0)
        monkeypatch.setattr(harness_module, "_FAKEY_RELEASE_TIMEOUT", 5.0)
        harness = _RunnerSlotFakeyHarness(tmp_path, monkeypatch, cap=2)
        monkeypatch.delenv("SASE_AGENT_NAME", raising=False)
        write_project_file(_MONITOR_PROJECT, workspace_dir=str(harness.workspace))
    
        starter = harness.create_agent(
            0,
            name="land--0",
            agent_session="land",
            queue_weight=2.0,
            queue_weight_explicit=True,
        )
        # `%i(@, session=...)` resolution (exercised below by the real ``--next``
        # handoff) matches on `workflow_name`, the durable agent-session key -- not on
        # `agent_session` alone -- so a real starter must carry both. A real
        # starter also always carries its own continuation-graph node id from
        # its own captured turn; without one, monitor-result capture treats the
        # starter link as broken and blocks automatic dispatch outright.
        starter.meta["workflow_name"] = "land"
        starter.meta["continuation_node_id"] = "agent-turn:land--0:sentinel"
        write_agent_meta(str(starter.artifacts_dir), starter.meta)
        harness.start(starter)
        harness.wait_started(starter)
        starter_owner_key = harness.agent_meta(starter).get("runner_claim_owner_key")
        assert isinstance(starter_owner_key, str) and starter_owner_key
    
        competitor = harness.create_agent(
            1, name="competitor", queue_weight=2.0, queue_weight_explicit=True
        )
        harness.start(competitor)
        harness.wait_parked(competitor)
    
        patch_project_records(monkeypatch, [str(starter.artifacts_dir)])
        # A real, currently-live (but otherwise unrelated) dummy process stands
        # in for the detached supervisor's PID: the weighted-capacity liveness
        # check must see the monitor's claim as genuinely live throughout.
        dummy_supervisor = subprocess.Popen(
            [sys.executable, "-c", "import time; time.sleep(30)"]
        )
        monkeypatch.setattr(
            spawn_module.subprocess, "Popen", _make_bootstrap_popen(dummy_supervisor.pid)
        )
    
        try:
            # `next_action` is authored right here, at creation, on the request
            # the real proc-supervisor settlement path reads back from disk --
            # never injected into an in-memory metadata copy after the fact.
            record = start_monitor(
                StartMonitorRequest(
                    command="true",
                    reason="weight-2 land agent-session acceptance",
                    timeout_seconds=30.0,
                    cwd=str(harness.workspace),
                    project_name=_MONITOR_PROJECT,
                    start_status="MONITORING",
                    stop_status="MONITORED",
                    lane="land",
                    inherit_lane_workspace_claim=False,
                    next_action="Report that the land agent session finished.",
                )
            )
    
            monitor_meta = json.loads(
                (Path(record.artifacts_dir) / "agent_meta.json").read_text(encoding="utf-8")
            )
            assert monitor_meta["runner_claim_owner_key"] == starter_owner_key
            assert monitor_meta["queue_weight"] == 2.0
            assert monitor_meta["queue_weight_explicit"] is True
    
            # Production kills the starter's runner group as part of a real
            # handoff; release its fakey process so only the monitor represents
            # live lineage.
            harness.release_agent(starter)
>           harness.join(starter)

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/fakey/test_monitor_capacity_e2e.py:205: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <tests.fakey._runner_slot_harness._RunnerSlotFakeyHarness object at 0x7f7b9de39650>
agent = _Agent(name='land--0', artifacts_dir=PosixPath('/var/tmp/sase-209af3f4/pytest-of-bryan/pytest-11/popen-gw3/test_weight...t=2.0, queue_weight_explicit=True, crash=False, killed=False, thread=<Thread(land--0, stopped daemon 140169143383744)>)

    def join(self, agent: _Agent) -> None:
        assert agent.thread is not None
        agent.thread.join(_WAIT_TIMEOUT)
        assert not agent.thread.is_alive(), (
            f"agent {agent.name} did not finish; {self._diagnostics(agent)}"
        )
        errors = [error for name, error in self._errors if name == agent.name]
>       assert not errors, f"agent {agent.name} failed: {errors!r}"
               ^^^^^^^^^^
E       AssertionError: agent land--0 failed: [CalledProcessError(124, ['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/bin/fakey', '--model', 'fakey-large'])]

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/fakey/_runner_slot_harness.py:226: AssertionError
----------------------------- Captured stdout call -----------------------------
Waiting for a runner slot
____________ test_sudo_local_flow_never_persists_canary_credentials ____________
[gw10] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/bin/python

gate_home = PosixPath('/var/tmp/sase-209af3f4/pytest-of-bryan/pytest-11/popen-gw10/test_sudo_local_flow_never_per0')
tmp_path = PosixPath('/var/tmp/sase-209af3f4/pytest-of-bryan/pytest-11/popen-gw10/test_sudo_local_flow_never_per0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f2cd9e597f0>
capsys = <_pytest.capture.CaptureFixture object at 0x7f2cd71a13d0>

    def test_sudo_local_flow_never_persists_canary_credentials(
        gate_home: Path,
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        credential_tty = tmp_path / "review-terminal-input.txt"
        credential_tty.write_text(_CANARY, encoding="utf-8")
        sase_home = tmp_path / "sase-home"
        monkeypatch.setenv("SASE_HOME", str(sase_home))
    
        with override_flags(agent_sudo_requests=True):
            gate = create_gate(
                build_sudo_gate_request(_request(), request_id="sudo-canary-flow")
            )
    
        parser = argparse.ArgumentParser(prog="sase")
        register_sudo_parser(parser.add_subparsers(dest="command"))
        args = parser.parse_args(
            ["sudo", "answer", gate.request_id, "--run", "--no-detach", "--json"]
        )
        monkeypatch.setattr("sase.sudo.cli.has_controlling_tty", lambda: True)
        monkeypatch.setattr(
            "sase.notification_gates.executor.has_controlling_tty",
            lambda: True,
        )
    
        def fake_runner(
            manifest: Mapping[str, Any],
            *,
            manifest_sha256: str,
            **_kwargs: Any,
        ) -> dict[str, Any]:
            assert credential_tty.read_text(encoding="utf-8") == _CANARY
            manifest_bytes = canonical_json_bytes(dict(manifest))
            for token in _sensitive_tokens(_CANARY).values():
                assert token not in manifest_bytes
            return _runner_ledger(manifest, manifest_sha256)
    
        monkeypatch.setattr("sase.sudo.cli.run_sudo_runner", fake_runner)
    
        with override_flags(agent_sudo_requests=True):
            assert handle_sudo_command(args) == 0
    
        output = json.loads(capsys.readouterr().out)
        assert output["status"] == "answered"
        assert output["outcome"] == "completed"
        assert gate.response_path.is_file()
        assert (gate.bundle_path / DECISION_RECEIPT_FILENAME).is_file()
>       _assert_sensitive_tokens_absent(
            (
                gate_home / "requests",
                gate_home / "notifications",
                gate_home / "pending.json",
                gate_home / "legacy.json",
                sase_home,
            ),
            canary=_CANARY,
        )

tests/test_sudo_acceptance_credentials.py:81: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

paths = (PosixPath('/var/tmp/sase-209af3f4/pytest-of-bryan/pytest-11/popen-gw10/test_sudo_local_flow_never_per0/requests'), Po...'), PosixPath('/var/tmp/sase-209af3f4/pytest-of-bryan/pytest-11/popen-gw10/test_sudo_local_flow_never_per0/sase-home'))
canary = 'SASE_CANARY_CREDENTIAL_VALUE_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx...xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'

    def _assert_sensitive_tokens_absent(
        paths: Iterable[Path],
        *,
        canary: str,
    ) -> None:
        tokens = _sensitive_tokens(canary)
        for path in _iter_files(paths):
            raw = path.read_bytes()
            for label, token in tokens.items():
>               assert token not in raw, f"{label} leaked into {path}"
                       ^^^^^^^^^^^^^^^^
E               AssertionError: credential length leaked into /var/tmp/sase-209af3f4/pytest-of-bryan/pytest-11/popen-gw10/test_sudo_local_flow_never_per0/requests/sudo/sudo-canary-flow/decision_receipt.json

tests/_sudo_acceptance_helpers.py:84: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 11 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/config/loading.py:60: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/ace/tui/command_line/test_panel_shell.py:431: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_policy_io.py::test_reopen_reuses_session_history_without_disk_reads
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:228: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def _reconstruct(x, memo, func, args,
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/xprompt/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

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

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_transcript_blocks.py::test_block_keys_select_move_and_switch_hints
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:2308: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def cast(typ, val):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:189: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for k, j in zip(x, y):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
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

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=667349) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=667317) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34' to '<deleted>'; restored it.
    next(it)

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=667321) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
122.39s call     tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows
80.38s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
71.10s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
58.52s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
58.12s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
56.15s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
45.15s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
33.49s call     tests/test_agent_group_revival_e2e.py::test_mark_save_preview_and_revive_saved_agent_group
32.52s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
30.94s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
25.73s call     tests/test_bead/test_task_beads.py::test_create_plan_prefers_frontmatter_proposer
24.53s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
23.49s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
23.33s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
21.62s call     tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_j_k_wrap_visible_tree_and_arrows_clamp
17.33s call     tests/pager/test_app_goto.py::test_semicolon_and_colon_both_open_the_goto_prompt
17.12s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_core_only_success_restarts_once_and_receipts
16.51s call     tests/ace/tui/test_plugins_browser_pane_marks.py::test_plugin_mark_survives_scope_switch_and_is_consumed_by_install
16.23s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
15.83s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
=========================== short test summary info ============================
FAILED tests/tool/test_wrapper_fidelity.py::test_inline_caller_group_sigkill_leaves_no_survivors
FAILED tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
FAILED tests/test_sudo_acceptance_credentials.py::test_sudo_local_flow_never_persists_canary_credentials
===== 3 failed, 47365 passed, 16 skipped, 98 warnings in 990.47s (0:16:30) =====
error: recipe `test-scoped` failed on line 486 with exit code 1
error: recipe `check` failed on line 735 with exit code 1
failed  exit=1  duration=3479699ms
unattrib  12m 30s

