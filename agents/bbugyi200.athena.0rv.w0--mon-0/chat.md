# Chat History - ace-run (0rv.w0--mon-0)

- **TIMESTAMP:** 2026-09-25 11:22:21 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 0rv.w0--mon-0

## Prompt

sase monitor start --command 'just check' --reason 'Final gate for the XPROMPT card header change: the tree is rebased onto origin/master f648e88e4, docs/ace.md conflict resolved, ten header goldens refreshed, just fix clean. The earlier check was red only on failures that also fail on clean master (since fixed upstream) or that passed in isolation (contention flakes).'

## Response

sase tool run 945f3a716809a1eed2a035d9e2c5af93
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/linked/sase-core to origin/master
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
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling proc-macro2 v1.0.106
   Compiling quote v1.0.45
   Compiling unicode-ident v1.0.24
   Compiling libc v0.2.186
   Compiling itoa v1.0.18
   Compiling cfg-if v1.0.4
   Compiling pin-project-lite v0.2.17
   Compiling bytes v1.11.1
   Compiling once_cell v1.21.4
   Compiling shlex v1.3.0
   Compiling find-msvc-tools v0.1.9
   Compiling futures-core v0.3.32
   Compiling memchr v2.8.0
   Compiling version_check v0.9.5
   Compiling target-lexicon v0.12.16
   Compiling futures-sink v0.3.32
   Compiling autocfg v1.5.0
   Compiling stable_deref_trait v1.2.1
   Compiling log v0.4.29
   Compiling serde_core v1.0.228
   Compiling hashbrown v0.17.0
   Compiling zerocopy v0.8.48
   Compiling equivalent v1.0.2
   Compiling smallvec v1.15.1
   Compiling slab v0.4.12
   Compiling tower-service v0.3.3
   Compiling futures-task v0.3.32
   Compiling futures-io v0.3.32
   Compiling writeable v0.6.3
   Compiling untrusted v0.9.0
   Compiling litemap v0.8.2
   Compiling zmij v1.0.21
   Compiling httparse v1.10.1
   Compiling serde v1.0.228
   Compiling icu_normalizer_data v2.2.0
   Compiling serde_json v1.0.149
   Compiling icu_properties_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling tower-layer v0.3.3
   Compiling typenum v1.20.0
   Compiling httpdate v1.0.3
   Compiling fnv v1.0.7
   Compiling vcpkg v0.2.15
   Compiling bitflags v2.11.1
   Compiling sync_wrapper v1.0.2
   Compiling percent-encoding v2.3.2
   Compiling rustls v0.21.12
   Compiling ryu v1.0.23
   Compiling pkg-config v0.3.33
   Compiling powerfmt v0.2.0
   Compiling rustversion v1.0.22
   Compiling num-conv v0.2.1
   Compiling time-core v0.1.8
   Compiling regex-syntax v0.8.10
   Compiling thiserror v2.0.18
   Compiling try-lock v0.2.5
   Compiling getrandom v0.4.2
   Compiling rustix v1.1.4
   Compiling atomic-waker v1.1.2
   Compiling mime v0.3.17
   Compiling thiserror v1.0.69
   Compiling iana-time-zone v0.1.65
   Compiling linux-raw-sys v0.12.1
   Compiling unsafe-libyaml v0.2.11
   Compiling fastrand v2.4.1
   Compiling fallible-iterator v0.3.0
   Compiling heck v0.5.0
   Compiling cpufeatures v0.2.17
   Compiling base64 v0.21.7
   Compiling fallible-streaming-iterator v0.1.9
   Compiling base64 v0.22.1
   Compiling ipnet v2.12.0
   Compiling tracing-core v0.1.36
   Compiling want v0.3.1
   Compiling cc v1.2.61
   Compiling unicode-width v0.2.2
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling num-traits v0.2.19
   Compiling memoffset v0.9.1
   Compiling encoding_rs v0.8.35
   Compiling sync_wrapper v0.1.2
   Compiling webpki-roots v0.25.4
   Compiling matchit v0.7.3
   Compiling hex v0.4.3
   Compiling indoc v2.0.7
   Compiling unindent v0.2.4
   Compiling http v1.4.0
   Compiling http v0.2.12
   Compiling futures-channel v0.3.32
   Compiling aho-corasick v1.1.4
   Compiling deranged v0.5.8
   Compiling time-macros v0.2.27
   Compiling indexmap v2.14.0
   Compiling form_urlencoded v1.2.2
   Compiling pyo3-build-config v0.22.6
   Compiling rustls-pemfile v1.0.4
   Compiling pem v3.0.6
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling getrandom v0.2.17
   Compiling socket2 v0.5.10
   Compiling fs2 v0.4.3
   Compiling ring v0.17.14
   Compiling libsqlite3-sys v0.30.1
   Compiling signal-hook-registry v1.4.8
   Compiling rand_core v0.6.4
   Compiling crypto-common v0.1.7
   Compiling block-buffer v0.10.4
   Compiling http-body v1.0.1
   Compiling serde_path_to_error v0.1.20
   Compiling http-body v0.4.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
   Compiling http-body-util v0.1.3
   Compiling num-integer v0.1.46
   Compiling chrono v0.4.44
   Compiling time v0.3.47
   Compiling digest v0.10.7
   Compiling regex-automata v0.4.14
   Compiling ppv-lite86 v0.2.21
   Compiling num-bigint v0.4.6
   Compiling syn v2.0.117
   Compiling tempfile v3.27.0
   Compiling sha2 v0.10.9
   Compiling hashbrown v0.14.5
   Compiling rand_chacha v0.3.1
   Compiling rand v0.8.6
   Compiling hashlink v0.9.1
   Compiling synstructure v0.13.2
   Compiling tokio-macros v2.7.0
   Compiling zerovec-derive v0.11.3
   Compiling displaydoc v0.2.5
   Compiling tracing-attributes v0.1.31
   Compiling futures-macro v0.3.32
   Compiling serde_derive v1.0.228
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling thiserror-impl v2.0.18
   Compiling async-trait v0.1.89
   Compiling thiserror-impl v1.0.69
   Compiling async-stream-impl v0.3.6
   Compiling async-stream v0.3.6
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling tracing v0.1.44
   Compiling simple_asn1 v0.6.4
   Compiling zerofrom v0.1.7
   Compiling yoke v0.8.2
   Compiling tower-http v0.5.2
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling pyo3-macros v0.22.6
   Compiling serde_urlencoded v0.7.1
   Compiling serde_yaml v0.9.34+deprecated
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling icu_collections v2.2.0
   Compiling icu_locale_core v2.2.0
   Compiling regex v1.12.3
   Compiling axum-core v0.4.5
   Compiling rustls-webpki v0.101.7
   Compiling sct v0.7.1
   Compiling jsonwebtoken v9.3.1
   Compiling icu_provider v2.2.0
   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling idna_adapter v1.2.2
   Compiling idna v1.1.0
   Compiling url v2.5.8
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling hyper v1.9.0
   Compiling h2 v0.3.27
   Compiling hyper-util v0.1.20
   Compiling axum v0.7.9
   Compiling tokio-rustls v0.24.1
   Compiling hyper v0.14.32
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.34.73 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_gateway v0.34.73 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.34.73 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 11m 54s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-nboe_h_m/sase_core_rs-0.34.73-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/cb7b1929d2547a55e3690010cdea44b9b4737e377c445f371676831fb5252323/sase_core_rs-0.34.73-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 89ms
Uninstalled 1 package in 2ms
Installed 1 package in 9ms
 - sase-core-rs==0.34.73 (from file:///home/bryan/.sase/cache/sase-core-artifacts/8bf65fb3712429aec0795240cc86379b5d8195a9a1dd27b2a954079c821fcdd9/sase_core_rs-0.34.73-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.34.73 (from file:///home/bryan/.sase/cache/sase-core-artifacts/cb7b1929d2547a55e3690010cdea44b9b4737e377c445f371676831fb5252323/sase_core_rs-0.34.73-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: no exact cached wheel
[sase-core-wheel-cache] Waiting for the shared build lock for 74f069bc3318 (up to 900s).
[rust-lsp-install] Installing cached sase-xprompt-lsp from /home/bryan/.sase/cache/sase-core-artifacts/74f069bc331845bdc7c76b10ccf7b4245e0833bca1f85f2cc2c2c45d91277d82/sase-xprompt-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/bin/sase-xprompt-lsp
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
test selection escalated to the full suite (rules: core-identity-changed, src-data-asset); 4362 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed, src-data-asset)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1, hypothesis-6.168.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 11/11 workers
11 workers [47406 items]

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
........................................................................ [ 11%]
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
........................................................................ [ 23%]
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
........................................................................ [ 35%]
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
............................................................F........... [ 37%]
........................................................................ [ 38%]
..........................................................s............. [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
...............................................................s........ [ 39%]
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
........................................................................ [ 42%]
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
..............................s......................................... [ 44%]
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
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
.................s....................s.s............................... [ 48%]
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
......ssss.............................................................. [ 52%]
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
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
...........................s............................................ [ 55%]
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
....................F................................................... [ 57%]
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
........................................................................ [ 59%]
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
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
.....................................................s.................. [ 63%]
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
........................................................................ [ 69%]
....................s................................................... [ 69%]
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
........................................................................ [ 71%]
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
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
.............s.......................................................... [ 74%]
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
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
...s.................................................................... [ 84%]
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
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
...................................s.................................... [ 92%]
......................................................ss................ [ 92%]
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
........................................................................ [ 94%]
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
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
..............................                                           [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____ test_ppid_walk_teardown_of_starter_descendants_leaves_monitor_running _____
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-b9943262/pytest-of-bryan/pytest-8/popen-gw6/test_ppid_walk_teardown_of_sta0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6490b73770>

    @pytest.mark.skipif(not Path("/proc").is_dir(), reason="/proc ancestry is required")
    def test_ppid_walk_teardown_of_starter_descendants_leaves_monitor_running(
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
        command = _python_command(
            "import time; print('survived teardown', flush=True); "
            "time.sleep(0.2); print('finished', flush=True)"
        )
    
        record = start_monitor(
            StartMonitorRequest(
                command=command,
                reason="verify ppid walk survival",
                timeout_seconds=30.0,
                cwd=str(tmp_path),
                project_name="proj",
                start_status="MONITORING",
                stop_status="MONITORED",
                lane="acme",
                inherit_lane_workspace_claim=False,
            )
        )
    
        _signal_descendants(os.getpid(), signal.SIGTERM)
    
>       done = wait_for_done(record.artifacts_dir, timeout=10.0)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/monitor/test_monitor_start_supervisor.py:329: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

artifacts_dir = '/var/tmp/sase-b9943262/pytest-of-bryan/pytest-8/popen-gw6/test_ppid_walk_teardown_of_sta0/.sase/projects/proj/artifacts/ace-run/202609/25/20260925110654'
timeout = 10.0

    def wait_for_done(
        artifacts_dir: str,
        *,
        timeout: float = POLL_TIMEOUT,
    ) -> dict[str, object]:
        """Block until a monitor member writes ``done.json`` and return it."""
        done_path = Path(artifacts_dir) / "done.json"
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            if done_path.exists():
                try:
                    return json.loads(done_path.read_text())
                except json.JSONDecodeError:
                    pass
            time.sleep(POLL_INTERVAL)
>       raise AssertionError(f"monitor at {artifacts_dir} never finished")
E       AssertionError: monitor at /var/tmp/sase-b9943262/pytest-of-bryan/pytest-8/popen-gw6/test_ppid_walk_teardown_of_sta0/.sase/projects/proj/artifacts/ace-run/202609/25/20260925110654 never finished

tests/monitor/_fixtures.py:177: AssertionError
______ test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway _______
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f3eff2b3bd0>
tmp_path = PosixPath('/var/tmp/sase-b9943262/pytest-of-bryan/pytest-8/popen-gw4/test_bootstrap_issue_enroll_he0')
gateway = RealGateway(home=PosixPath('/var/tmp/sase-b9943262/pytest-of-bryan/pytest-8/popen-gw4/test_bootstrap_issue_enroll_he0/...sixPath('/var/tmp/sase-b9943262/pytest-of-bryan/pytest-8/popen-gw4/test_bootstrap_issue_enroll_he0/gw/gateway.stderr'))

    def test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        gateway: RealGateway,
    ) -> None:
        redirect_sase_home(monkeypatch, gateway.home)
        issued = MachineService().issue_bootstrap()
        bundle_text = json.dumps(issued.bundle, sort_keys=True)
        bootstrap_secret = str(issued.bundle["bootstrap_secret"])
        assert bootstrap_secret not in repr(issued)
    
        client, config_dir = _client_service(monkeypatch, tmp_path, "client", gateway)
        result = client.add_machine(
            alias="apollo",
            endpoint=gateway.https_endpoint,
            provider_ref="builtin@https",
            bundle_text=bundle_text,
        )
    
        assert result.quarantined is False
        assert result.installation_id == issued.pinned_installation_id
    
        credential = client.credential_store.get(result.credential_ref)
        assert credential is not None
        assert credential.token
    
        config_text = (config_dir / "sase.yml").read_text(encoding="utf-8")
        assert credential.token not in config_text
        assert bootstrap_secret not in config_text
    
        deadline = time.monotonic() + _HELLO_RETRY_WINDOW_SECONDS
        while True:
            (status,) = client.status(("apollo",))
            if status.state == "ok":
                break
            if (
                status.state == "error"
                and status.message.startswith("hello failed:")
                and time.monotonic() < deadline
            ):
                time.sleep(_HELLO_RETRY_SLEEP_SECONDS)  # sase-test-wait: hello transport
                continue
>           raise AssertionError(_status_detail(status, gateway))
E           AssertionError: state='error' message='hello failed: timeout'
E           gateway stdout:
E           
E           gateway stderr:

tests/dispatch/test_machine_bootstrap_real_gateway.py:119: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 11 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/src/sase/config/loading.py:60: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/tests/ace/tui/command_line/test_panel_shell.py:431: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_panel_shell.py::test_submit_happy_path_settles_on_exit_completion
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_proc_submit_captures_confirm_flags
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    obj, end = self.scan_once(s, idx)
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

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/src/sase/xprompt/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=220579) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=220598) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42' to '<deleted>'; restored it.
    next(it)

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=220589) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
254.81s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
117.33s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
115.44s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
90.88s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
83.15s call     tests/test_plugin_cli_install.py::test_install_requires_plugin
70.66s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
68.87s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
61.02s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
58.75s call     tests/gate_conformance/test_gate_shell_conformance.py::test_shell_gate_settles_identically_across_every_surface
42.45s call     tests/monitor/test_monitor_resume_delivery.py::test_resume_dispatch_real_preprocess_adopt_budget_and_provider_invoke_combine
40.62s call     tests/test_bead/test_cli_at_path_values.py::test_close_missing_note_file_mutates_nothing
38.66s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
37.80s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
36.65s call     tests/ace/tui/test_plugins_browser_pane_scopes.py::test_scope_membership_includes_manual_cli_error_and_excludes_available
36.15s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
32.74s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
32.09s setup    tests/llm_provider/test_model_advisories.py::test_model_picker_row_carries_the_advisory[muse-spark-1.3-contributor]
31.34s call     tests/pager/test_app_actions.py::test_attached_handler_receives_the_pending_copy_action
31.31s call     tests/ace/tui/test_plugins_browser_pane_scopes.py::test_empty_identity_open_lands_on_first_outdated_row
30.82s call     tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_done_row_dismissed_without_signal_and_stays_hidden
=========================== short test summary info ============================
FAILED tests/monitor/test_monitor_start_supervisor.py::test_ppid_walk_teardown_of_starter_descendants_leaves_monitor_running
FAILED tests/dispatch/test_machine_bootstrap_real_gateway.py::test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway
==== 2 failed, 47386 passed, 19 skipped, 98 warnings in 1385.97s (0:23:05) =====
error: recipe `test-scoped` failed on line 486 with exit code 1
error: recipe `check` failed on line 735 with exit code 1
failed  exit=1  duration=3036382ms
unattrib  21m 39s

