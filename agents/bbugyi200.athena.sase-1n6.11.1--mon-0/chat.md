# Chat History - ace-run (sase-1n6.11.1--mon-0)

- **TIMESTAMP:** 2026-11-03 18:29:27 EST
- **MODEL:** codex/gpt-6-astra
- **AGENT:** sase-1n6.11.1--mon-0

## Prompt

sase monitor start --command '.venv/bin/python .git/sase-merge-checks-verify.py' --reason 'Verify recovered merge-checks commits and source-pin containment after explicit host commit declarations'

## Response

sase tool run ce1624169b9def5609fe48a8e402002e
Verified all 14 recovered files committed in main
Verified all 7 recovered files committed in core
From github.com:sase-org/sase-core
 * branch              master     -> FETCH_HEAD
CORE_COMMIT=4b1b8aca1156bf0f91dbc0fb7a33048d948f4254 PIN=4b1b8aca1156bf0f91dbc0fb7a33048d948f4254 CONTAINED=true
sase tool run df54dcddede232d404e6ddc1aff450f9
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[core-source] linked sase-core source changed since the extension was built; flagging an extension rebuild.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
[setup] Rebuilding sase_core_rs: linked sase-core source changed since the extension was built.
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[rust-install] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev builds from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core ignore it. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling proc-macro2 v1.0.106
   Compiling quote v1.0.45
   Compiling unicode-ident v1.0.24
   Compiling libc v0.2.186
   Compiling cfg-if v1.0.4
   Compiling shlex v1.3.0
   Compiling find-msvc-tools v0.1.9
   Compiling zerocopy v0.8.48
   Compiling memchr v2.8.0
   Compiling serde_core v1.0.228
   Compiling autocfg v1.5.0
   Compiling itoa v1.0.18
   Compiling crossbeam-utils v0.8.21
   Compiling once_cell v1.21.4
   Compiling pin-project-lite v0.2.17
   Compiling bytes v1.11.1
   Compiling regex-syntax v0.8.10
   Compiling log v0.4.29
   Compiling serde v1.0.228
   Compiling siphasher v1.0.4
   Compiling version_check v0.9.5
   Compiling zmij v1.0.21
   Compiling futures-core v0.3.32
   Compiling crossbeam-epoch v0.9.21
   Compiling smallvec v1.15.1
   Compiling serde_json v1.0.149
   Compiling target-lexicon v0.12.16
   Compiling futures-sink v0.3.32
   Compiling crossbeam-deque v0.8.8
   Compiling stable_deref_trait v1.2.1
   Compiling equivalent v1.0.2
   Compiling hashbrown v0.17.0
   Compiling futures-task v0.3.32
   Compiling tower-service v0.3.3
   Compiling ucd-trie v0.1.7
   Compiling iana-time-zone v0.1.65
   Compiling slab v0.4.12
   Compiling futures-io v0.3.32
   Compiling bitflags v2.11.1
   Compiling libm v0.2.16
   Compiling same-file v1.0.6
   Compiling litemap v0.8.2
   Compiling heck v0.5.0
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling untrusted v0.9.0
   Compiling icu_normalizer_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling typenum v1.20.0
   Compiling tower-layer v0.3.3
   Compiling fnv v1.0.7
   Compiling deunicode v1.6.2
   Compiling parking_lot_core v0.9.12
   Compiling httpdate v1.0.3
   Compiling lazy_static v1.5.0
   Compiling clap_lex v1.1.1
   Compiling unicode-segmentation v1.13.3
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling encoding_rs v0.8.35
   Compiling cc v1.2.61
   Compiling rustls v0.21.12
   Compiling thiserror v1.0.69
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling pkg-config v0.3.33
   Compiling anstyle v1.0.14
   Compiling tracing-core v0.1.36
   Compiling percent-encoding v2.3.2
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling slug v0.1.6
   Compiling vcpkg v0.2.15
   Compiling scopeguard v1.2.0
   Compiling sync_wrapper v1.0.2
   Compiling num-traits v0.2.19
   Compiling http v1.4.0
   Compiling futures-channel v0.3.32
   Compiling ryu v1.0.23
   Compiling walkdir v2.5.0
   Compiling thiserror v2.0.18
   Compiling indexmap v2.14.0
   Compiling time-core v0.1.8
   Compiling winnow v1.0.4
   Compiling rustversion v1.0.22
   Compiling getrandom v0.4.2
   Compiling num-conv v0.2.1
   Compiling try-lock v0.2.5
   Compiling rustix v1.1.4
   Compiling powerfmt v0.2.0
   Compiling grep-matcher v0.1.9
   Compiling cpufeatures v0.2.17
   Compiling phf_shared v0.11.3
   Compiling humansize v2.1.3
   Compiling http v0.2.12
   Compiling mime v0.3.17
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling home v0.5.12
   Compiling atomic-waker v1.1.2
   Compiling pyo3-build-config v0.22.6
   Compiling winnow v0.7.15
   Compiling colored v2.2.0
   Compiling serde_spanned v1.1.2
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling linux-raw-sys v0.12.1
   Compiling itertools v0.11.0
   Compiling crossbeam-channel v0.5.17
   Compiling form_urlencoded v1.2.2
   Compiling memoffset v0.9.1
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling getrandom v0.2.17
   Compiling regex-automata v0.4.14
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling libsqlite3-sys v0.30.1
   Compiling clap_builder v4.6.7
   Compiling memmap2 v0.9.11
   Compiling socket2 v0.5.10
   Compiling lock_api v0.4.14
   Compiling encoding_rs_io v0.1.8
   Compiling term_size v0.3.2
   Compiling tinyvec v1.13.3
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling unsafe-libyaml v0.2.11
   Compiling base64 v0.22.1
   Compiling fastrand v2.4.1
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling time-macros v0.2.27
   Compiling want v0.3.1
   Compiling fallible-iterator v0.3.0
   Compiling ppv-lite86 v0.2.21
   Compiling deranged v0.5.8
   Compiling http-body v1.0.1
   Compiling base64 v0.21.7
   Compiling fallible-streaming-iterator v0.1.9
   Compiling phf v0.11.3
   Compiling tracing-log v0.2.0
   Compiling fs2 v0.4.3
   Compiling serde_path_to_error v0.1.20
   Compiling etcetera v0.8.0
   Compiling sharded-slab v0.1.7
   Compiling thread_local v1.1.9
   Compiling semver v1.0.28
   Compiling matchit v0.7.3
   Compiling unicode-width v0.2.2
   Compiling http-body v0.4.6
   Compiling unicode-casefold v0.2.0
   Compiling webpki-roots v0.25.4
   Compiling ipnet v2.12.0
   Compiling signal-hook-registry v1.4.8
   Compiling rand_core v0.6.4
   Compiling sync_wrapper v0.1.2
   Compiling nu-ansi-term v0.50.3
   Compiling hex v0.4.3
   Compiling unindent v0.2.4
   Compiling indoc v2.0.7
   Compiling parking_lot v0.12.5
   Compiling grep-searcher v0.1.17
   Compiling pem v3.0.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
   Compiling http-body-util v0.1.3
   Compiling digest v0.10.7
   Compiling unicode-normalization v0.1.25
   Compiling toml v0.9.12+spec-1.1.0
   Compiling rustls-pemfile v1.0.4
   Compiling hashbrown v0.14.5
   Compiling time v0.3.47
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling chrono v0.4.44
   Compiling num-integer v0.1.46
   Compiling rand_chacha v0.3.1
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling pest v2.9.4
   Compiling num-bigint v0.4.6
   Compiling hashlink v0.9.1
   Compiling ignore v0.4.32
   Compiling parse-zoneinfo v0.3.1
   Compiling rayon v1.12.0
   Compiling rand v0.8.6
   Compiling tempfile v3.27.0
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
   Compiling pest_meta v2.9.4
   Compiling phf_generator v0.11.3
   Compiling globwalk v0.9.1
   Compiling phf_codegen v0.11.3
   Compiling chrono-tz-build v0.3.0
   Compiling matchers v0.2.0
   Compiling chrono-tz v0.9.0
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling arbitrary v1.5.0
   Compiling synstructure v0.13.2
   Compiling serde_derive v1.0.228
   Compiling tokio-macros v2.7.0
   Compiling zerovec-derive v0.11.3
   Compiling tracing-attributes v0.1.31
   Compiling displaydoc v0.2.5
   Compiling futures-macro v0.3.32
   Compiling thiserror-impl v1.0.69
   Compiling thiserror-impl v2.0.18
   Compiling async-trait v0.1.89
   Compiling async-stream-impl v0.3.6
   Compiling pest_derive v2.9.4
   Compiling clap v4.6.7
   Compiling tokio v1.52.2
   Compiling async-stream v0.3.6
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling clap-cargo v0.18.3
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling table_formatter v0.6.1
   Compiling simple_asn1 v0.6.4
   Compiling zerofrom v0.1.7
   Compiling tracing-subscriber v0.3.23
   Compiling tower-http v0.5.2
   Compiling yoke v0.8.2
   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling serde_urlencoded v0.7.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling pyo3-macros v0.22.6
   Compiling axum-core v0.4.5
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling icu_collections v2.2.0
   Compiling icu_locale_core v2.2.0
   Compiling tokei v15.0.0
   Compiling icu_provider v2.2.0
   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling tokio-rustls v0.24.1
   Compiling hyper v1.9.0
   Compiling h2 v0.3.27
   Compiling idna_adapter v1.2.2
   Compiling hyper-util v0.1.20
   Compiling idna v1.1.0
   Compiling axum v0.7.9
   Compiling url v2.5.8
   Compiling hyper v0.14.32
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_gateway v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 15m 19s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-t4fn7hgn/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/8f8b73e1b664f879f29648238353eac193a721171edb3de45b46cd94e0b2afa7/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 2ms
Prepared 1 package in 155ms
Uninstalled 1 package in 1ms
Installed 1 package in 2ms
 - sase-core-rs==0.43.3 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core/crates/sase_core_py)
 + sase-core-rs==0.43.3 (from file:///home/bryan/.sase/cache/sase-core-artifacts/8f8b73e1b664f879f29648238353eac193a721171edb3de45b46cd94e0b2afa7/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: no exact cached wheel
    Finished `dev-update` profile [optimized] target(s) in 0.20s
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/c4461bae5c92cd2d456044807f0cbe5215916439e486d215a7cf59fb02a1f268/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/sase-macro-lsp
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.43.2 is missing 36 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] advance_agent_hijack_record: first appears in sase-core 65925ca (feat(agent-hijack): add core ledger and eligibility); no release tag contains it yet.
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
[core-floor-probe] hijack_recovery_preview: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); no release tag contains it yet.
[core-floor-probe] hijack_recovery_preview_wire_schema_version: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); no release tag contains it yet.
[core-floor-probe] hijack_recovery_reconcile: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); no release tag contains it yet.
[core-floor-probe] hijack_recovery_reconcile_wire_schema_version: first appears in sase-core bbef1df (feat(agent-hijack): add recovery identity, preview, and reconcile wires); no release tag contains it yet.
[core-floor-probe] normalize_hijack_rung: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); no release tag contains it yet.
[core-floor-probe] parse_wait_target: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] plan_checked_release_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] plan_pin_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] recovery_adoption_lock_filename: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] recovery_context_wire_schema_version: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] resolve_agent_run_state_observations: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_agent_run_state_discovery_window: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_agent_run_state_hoods: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_current_wait_turn: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] staged_handoff_receipt_transition_allowed: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] staged_reconcile_page: first appears in sase-core 16a3ed0 (feat(staged-handoff): add bounded discovery and automatic recovery policy); no release tag contains it yet.
[core-floor-probe] strip_hijack_launch_directives: first appears in sase-core f1bbb4f (feat(agent-hijack): add escalation policy and continuation-prompt core with bindings); no release tag contains it yet.
[core-floor-probe] validate_recovery_context: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] workspace_retention_wire_schema_version: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "65925ca", "name": "advance_agent_hijack_record", "release": null, "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "f1bbb4f", "name": "agent_hijack_continuation_prompt", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "f1bbb4f", "name": "agent_hijack_continuation_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "65925ca", "name": "agent_hijack_eligibility", "release": null, "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "f1bbb4f", "name": "agent_hijack_escalation_target", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "f1bbb4f", "name": "agent_hijack_escalation_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "65925ca", "name": "agent_hijack_status_for_done_marker", "release": null, "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "65925ca", "name": "agent_hijack_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add core ledger and eligibility"}, {"commit": "45c6a26", "name": "agent_prompt_select", "release": null, "subject": "feat(agent-prompts): add Rust-owned agent prompt selection policy"}, {"commit": "e60f3e1", "name": "bead_assess_epic_symbol_freshness", "release": null, "subject": "feat(bead): classify epic symbol freshness in Rust"}, {"commit": "e60f3e1", "name": "bead_parse_epic_symbol_entries", "release": null, "subject": "feat(bead): classify epic symbol freshness in Rust"}, {"commit": "6cd64a9", "name": "classify_instruction_readout", "release": null, "subject": "feat(core): add instruction handoff readout classifier"}, {"commit": "80338d6", "name": "decide_workspace_retention", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "154fe9e", "name": "decide_workspace_retention_dismissal", "release": null, "subject": "feat(stranded-work): retain held workspace as stranded unless live successor owns"}, {"commit": "f061f5f", "name": "default_publication_cleanup_timeout", "release": null, "subject": "fix(git-lock): enforce effective budget in backoff and aged-lock decisions"}, {"commit": "d7b00dd", "name": "effective_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "evaluate_recovery_decision", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "bbef1df", "name": "hijack_recovery_preview", "release": null, "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "bbef1df", "name": "hijack_recovery_preview_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "bbef1df", "name": "hijack_recovery_reconcile", "release": null, "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "bbef1df", "name": "hijack_recovery_reconcile_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add recovery identity, preview, and reconcile wires"}, {"commit": "f1bbb4f", "name": "normalize_hijack_rung", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "d7b00dd", "name": "parse_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "80338d6", "name": "plan_checked_release_workspace_claim_from_content", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "80338d6", "name": "plan_pin_workspace_claim_from_content", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "73ec04a", "name": "recovery_adoption_lock_filename", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "73ec04a", "name": "recovery_context_wire_schema_version", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "dc5383f", "name": "resolve_agent_run_state_observations", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "dc5383f", "name": "select_agent_run_state_discovery_window", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "dc5383f", "name": "select_agent_run_state_hoods", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "d7b00dd", "name": "select_current_wait_turn", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "staged_handoff_receipt_transition_allowed", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "16a3ed0", "name": "staged_reconcile_page", "release": null, "subject": "feat(staged-handoff): add bounded discovery and automatic recovery policy"}, {"commit": "f1bbb4f", "name": "strip_hijack_launch_directives", "release": null, "subject": "feat(agent-hijack): add escalation policy and continuation-prompt core with bindings"}, {"commit": "73ec04a", "name": "validate_recovery_context", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "80338d6", "name": "workspace_retention_wire_schema_version", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}], "declared_floor": "0.43.2", "exit_code": 4, "message": "sase-core-rs==0.43.2 is missing 36 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✓ test (scoped)
scoped: escalated to the full suite (rules: contract-set-only, core-identity-changed); contexts baseline not consulted
succeeded  exit=0  duration=2211500ms
unattrib  15m 48s
{"blocker_duration_uncertain":false,"details":"core-cut failed (CORE_CUT_RED check=cargo_fmt_+_clippy_+_test_(macos-latest) run=https://github.com/sase-org/sase-core/actions/runs/41664195679 attempt=1); steward does not multiply its retry","escalation":{"disposition":"proposed","key":"esc-comment:install_broken:325:cli","operation":{"body":"+1 immediate install_broken macos","family":"install_broken","issue_number":325,"kind":"comment","tick_identity":"cli"},"severity":"immediate"},"evidence":[],"primary":{"check":"CORE_CUT_RED check=cargo_fmt_+_clippy_+_test_(macos-latest) run=https://github.com/sase-org/sase-core/actions/runs/41664195679 attempt=1","kind":"core_cut_red"},"process_exit":0,"schema_version":2,"secondary":[{"detail":"contracted macos canary result is missing","state":{"kind":"install_broken","member":"macos"}}]}

release_watch: core_cut_red

POST-COMMIT CHECK AND LIVE READ PASSED
succeeded  exit=0  duration=2436003ms

