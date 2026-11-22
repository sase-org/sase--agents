# Chat History - ace-run (1f5--mon-0)

- **TIMESTAMP:** 2026-11-22 10:05:56 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** 1f5--mon-0

## Prompt

sase monitor start --command 'just check' --reason 'Verify lazy running_field import-cycle fix and Gate Debug split before host completion'

## Response

sase tool run af5fee1cac58e5627d6ec27ea0e24d93
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core to origin/master
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
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling proc-macro2 v1.0.106
   Compiling quote v1.0.45
   Compiling unicode-ident v1.0.24
   Compiling libc v0.2.186
   Compiling cfg-if v1.0.4
   Compiling find-msvc-tools v0.1.9
   Compiling shlex v1.3.0
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
   Compiling serde v1.0.228
   Compiling cc v1.2.61
   Compiling log v0.4.29
   Compiling siphasher v1.0.4
   Compiling zmij v1.0.21
   Compiling version_check v0.9.5
   Compiling futures-core v0.3.32
   Compiling crossbeam-epoch v0.9.21
   Compiling num-traits v0.2.19
   Compiling smallvec v1.15.1
   Compiling aho-corasick v1.1.4
   Compiling serde_json v1.0.149
   Compiling stable_deref_trait v1.2.1
   Compiling target-lexicon v0.12.16
   Compiling futures-sink v0.3.32
   Compiling crossbeam-deque v0.8.8
   Compiling getrandom v0.2.17
   Compiling phf_shared v0.11.3
   Compiling tracing-core v0.1.36
   Compiling equivalent v1.0.2
   Compiling hashbrown v0.17.0
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling futures-channel v0.3.32
   Compiling errno v0.3.14
   Compiling phf v0.11.3
   Compiling rand_core v0.6.4
   Compiling regex-automata v0.4.14
   Compiling mio v1.2.0
   Compiling socket2 v0.6.3
   Compiling indexmap v2.14.0
   Compiling pyo3-build-config v0.22.6
   Compiling signal-hook-registry v1.4.8
   Compiling ring v0.17.14
   Compiling slab v0.4.12
   Compiling ucd-trie v0.1.7
   Compiling tower-service v0.3.3
   Compiling futures-task v0.3.32
   Compiling iana-time-zone v0.1.65
   Compiling futures-io v0.3.32
   Compiling pest v2.9.4
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling bitflags v2.11.1
   Compiling regex v1.12.3
   Compiling chrono v0.4.44
   Compiling generic-array v0.14.7
   Compiling ahash v0.8.12
   Compiling bstr v1.13.1
   Compiling litemap v0.8.2
   Compiling writeable v0.6.3
   Compiling parse-zoneinfo v0.3.1
   Compiling httparse v1.10.1
   Compiling untrusted v0.9.0
   Compiling ppv-lite86 v0.2.21
   Compiling heck v0.5.0
   Compiling same-file v1.0.6
   Compiling libm v0.2.16
   Compiling http v1.4.0
   Compiling pest_meta v2.9.4
   Compiling globset v0.4.19
   Compiling icu_normalizer_data v2.2.0
   Compiling typenum v1.20.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling walkdir v2.5.0
   Compiling rand_chacha v0.3.1
   Compiling deunicode v1.6.2
   Compiling fnv v1.0.7
   Compiling httpdate v1.0.3
   Compiling pest_generator v2.9.4
   Compiling ignore v0.4.32
   Compiling rand v0.8.6
   Compiling http-body v1.0.1
   Compiling lazy_static v1.5.0
   Compiling tower-layer v0.3.3
   Compiling parking_lot_core v0.9.12
   Compiling http v0.2.12
   Compiling slug v0.1.6
   Compiling hashbrown v0.14.5
   Compiling pest_derive v2.9.4
   Compiling humansize v2.1.3
   Compiling encoding_rs v0.8.35
   Compiling globwalk v0.9.1
   Compiling thiserror v1.0.69
   Compiling ryu v1.0.23
   Compiling synstructure v0.13.2
   Compiling serde_derive v1.0.228
   Compiling tokio-macros v2.7.0
   Compiling zerovec-derive v0.11.3
   Compiling phf_generator v0.11.3
   Compiling tokio v1.52.2
   Compiling tracing-attributes v0.1.31
   Compiling displaydoc v0.2.5
   Compiling futures-macro v0.3.32
   Compiling percent-encoding v2.3.2
   Compiling unicode-segmentation v1.13.3
   Compiling futures-util v0.3.32
   Compiling vcpkg v0.2.15
   Compiling anstyle v1.0.14
   Compiling either v1.19.0
   Compiling tracing v0.1.44
   Compiling sync_wrapper v1.0.2
   Compiling phf_codegen v0.11.3
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling rustls v0.21.12
   Compiling zerofrom v0.1.7
   Compiling pkg-config v0.3.33
   Compiling clap_lex v1.1.1
   Compiling rayon-core v1.13.0
   Compiling scopeguard v1.2.0
   Compiling chrono-tz-build v0.3.0
   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
   Compiling form_urlencoded v1.2.2
   Compiling json5 v0.4.1
   Compiling thiserror-impl v1.0.69
   Compiling yoke v0.8.2
   Compiling crypto-common v0.1.7
   Compiling block-buffer v0.10.4
   Compiling clap_derive v4.6.7
   Compiling libsqlite3-sys v0.30.1
   Compiling lock_api v0.4.14
   Compiling clap_builder v4.6.7
   Compiling chrono-tz v0.9.0
   Compiling time-core v0.1.8
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling rustix v1.1.4
   Compiling winnow v1.0.4
   Compiling thiserror v2.0.18
   Compiling try-lock v0.2.5
   Compiling powerfmt v0.2.0
   Compiling num-conv v0.2.1
   Compiling getrandom v0.4.2
   Compiling rustversion v1.0.22
   Compiling deranged v0.5.8
   Compiling digest v0.10.7
   Compiling want v0.3.1
   Compiling time-macros v0.2.27
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling encoding_rs_io v0.1.8
   Compiling itertools v0.11.0
   Compiling http-body v0.4.6
   Compiling clap v4.6.7
   Compiling thiserror-impl v2.0.18
   Compiling colored v2.2.0
   Compiling tera v1.20.1
   Compiling icu_locale_core v2.2.0
   Compiling icu_collections v2.2.0
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling http-body-util v0.1.3
   Compiling derive_arbitrary v1.5.0
   Compiling num-integer v0.1.46
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling serde_spanned v1.1.2
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling memmap2 v0.9.11
   Compiling socket2 v0.5.10
   Compiling grep-matcher v0.1.9
   Compiling h2 v0.3.27
   Compiling linux-raw-sys v0.12.1
   Compiling icu_provider v2.2.0
   Compiling cpufeatures v0.2.17
   Compiling home v0.5.12
   Compiling mime v0.3.17
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling atomic-waker v1.1.2
   Compiling winnow v0.7.15
   Compiling tokio-rustls v0.24.1
   Compiling grep-searcher v0.1.17
   Compiling etcetera v0.8.0
   Compiling num-bigint v0.4.6
   Compiling table_formatter v0.6.1
   Compiling rayon v1.12.0
   Compiling tokei v15.0.0
   Compiling time v0.3.47
   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling arbitrary v1.5.0
   Compiling hyper v1.9.0
   Compiling clap-cargo v0.18.3
   Compiling parking_lot v0.12.5
   Compiling dashmap v6.1.0
   Compiling idna_adapter v1.2.2
   Compiling toml v0.9.12+spec-1.1.0
   Compiling serde_urlencoded v0.7.1
   Compiling hashlink v0.9.1
   Compiling async-trait v0.1.89
   Compiling idna v1.1.0
   Compiling crossbeam-channel v0.5.17
   Compiling term_size v0.3.2
   Compiling memoffset v0.9.1
   Compiling fastrand v2.4.1
   Compiling base64 v0.22.1
   Compiling tinyvec v1.13.3
   Compiling hyper v0.14.32
   Compiling fallible-iterator v0.3.0
   Compiling base64 v0.21.7
   Compiling unsafe-libyaml v0.2.11
   Compiling fallible-streaming-iterator v0.1.9
   Compiling simple_asn1 v0.6.4
   Compiling axum-core v0.4.5
   Compiling hyper-util v0.1.20
   Compiling tempfile v3.27.0
   Compiling pem v3.0.6
   Compiling rustls-pemfile v1.0.4
   Compiling url v2.5.8
   Compiling sha1 v0.10.7
   Compiling unicode-normalization v0.1.25
   Compiling sha2 v0.10.9
   Compiling serde_yaml v0.9.34+deprecated
   Compiling matchers v0.2.0
   Compiling async-stream-impl v0.3.6
   Compiling sharded-slab v0.1.7
   Compiling pyo3 v0.22.6
   Compiling serde_path_to_error v0.1.20
   Compiling tracing-log v0.2.0
   Compiling fs2 v0.4.3
   Compiling thread_local v1.1.9
   Compiling nu-ansi-term v0.50.3
   Compiling ipnet v2.12.0
   Compiling unicode-width v0.2.2
   Compiling webpki-roots v0.25.4
   Compiling matchit v0.7.3
   Compiling hyper-rustls v0.24.2
   Compiling unicode-casefold v0.2.0
   Compiling semver v1.0.28
   Compiling sync_wrapper v0.1.2
   Compiling hex v0.4.3
   Compiling async-stream v0.3.6
   Compiling jsonwebtoken v9.3.1
   Compiling pyo3-macros v0.22.6
   Compiling tracing-subscriber v0.3.23
   Compiling tower-http v0.5.2
   Compiling unindent v0.2.4
   Compiling indoc v2.0.7
   Compiling axum v0.7.9
   Compiling reqwest v0.11.27
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_gateway v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 15m 42s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-r9e7w68c/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/ed070a14a42967be3a8686c48c94fcc8b2aff9efe62e59e2bcb70932687c5c25/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 156ms
Uninstalled 1 package in 2ms
Installed 1 package in 10ms
 - sase-core-rs==0.44.2 (from file:///home/bryan/.sase/cache/sase-core-artifacts/c91b6363b41a683571c2e1f96210c136d8c47c664d80a9bc76fdf96dd3f77db7/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.44.2 (from file:///home/bryan/.sase/cache/sase-core-artifacts/ed070a14a42967be3a8686c48c94fcc8b2aff9efe62e59e2bcb70932687c5c25/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: no exact cached wheel
[sase-core-wheel-cache] Waiting for the shared build lock for fea7f2ae773d (up to 900s).
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/fea7f2ae773d61934396f3c791480ff24863dff62a59a2cacf7635df8792610f/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/sase-macro-lsp
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.44.2 is missing 54 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] agent_artifact_list_wire_schema_version: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_decide: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] agent_hijack_eligibility_wire_schema_version: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] agent_hijack_latch_observe: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_latch_wire_schema_version: first appears in sase-core e9b1cf0 (feat(agent-hijack): add latch ledger policy and bindings); no release tag contains it yet.
[core-floor-probe] agent_hijack_select_occupant: first appears in sase-core 9940715 (feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger); no release tag contains it yet.
[core-floor-probe] append_notification_counts_with_options: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); no release tag contains it yet.
[core-floor-probe] append_notification_with_options: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); no release tag contains it yet.
[core-floor-probe] apply_chop_batch_transition: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] artifact_file_association_query: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); no release tag contains it yet.
[core-floor-probe] artifact_file_association_query_wire_schema_version: first appears in sase-core 19b89ac (feat(artifact-file): add targeted association query over JSONL index); no release tag contains it yet.
[core-floor-probe] artifact_read_audit_query: first appears in sase-core 3992fce (feat(audit-query): query artifact-read audit logs); no release tag contains it yet.
[core-floor-probe] artifact_read_audit_query_wire_schema_version: first appears in sase-core 3992fce (feat(audit-query): query artifact-read audit logs); no release tag contains it yet.
[core-floor-probe] axe_error_wire_schema_version: first appears in sase-core 3a32a23 (feat(axe-error): add volatile-token normalizer and signature grouping); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query_wire_schema_version: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_triage_owner_candidates: first appears in sase-core cb76eb2 (feat(bead): project triage owner candidates from the read model); no release tag contains it yet.
[core-floor-probe] bead_view_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] chop_batch_generation_matches: first appears in sase-core b1a0363 (feat(axe-chop): add clan-scoped generation match and cancelled settlement); no release tag contains it yet.
[core-floor-probe] compact_notification_store: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); no release tag contains it yet.
[core-floor-probe] decide_local_command_trust: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] decide_publication_standing: first appears in sase-core 3c3263f (feat(publication): add standing-alert decider with capped backoff); no release tag contains it yet.
[core-floor-probe] digest_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] filter_trusted_local_layer: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] gate_failure_resurface_decision: first appears in sase-core f0034a7 (feat(agent-scan,notifications): project gate failure and dismissal timestamps with shared resurface policy); no release tag contains it yet.
[core-floor-probe] group_axe_errors: first appears in sase-core 3a32a23 (feat(axe-error): add volatile-token normalizer and signature grouping); no release tag contains it yet.
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
[core-floor-probe] normalize_error_signature: first appears in sase-core 3a32a23 (feat(axe-error): add volatile-token normalizer and signature grouping); no release tag contains it yet.
[core-floor-probe] plan_prompt_command_substitution: first appears in sase-core 1191f9a (feat: add prompt command-substitution source policy); no release tag contains it yet.
[core-floor-probe] project_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] prompt_command_substitution_wire_schema_version: first appears in sase-core 1191f9a (feat: add prompt command-substitution source policy); no release tag contains it yet.
[core-floor-probe] query_agent_artifact_index_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] reconcile_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] reconcile_notification_rows_with_options: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); no release tag contains it yet.
[core-floor-probe] resolve_notification_payloads: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); no release tag contains it yet.
[core-floor-probe] scan_agent_artifact_dirs_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] scan_agent_artifacts_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] select_agent_artifact_group: first appears in sase-core b9f33b0 (feat(agent-scan): select indexed session and clan generations); no release tag contains it yet.
[core-floor-probe] select_named_agent: first appears in sase-core d201086 (feat(agent-scan): add bounded named lookup selection); no release tag contains it yet.
[core-floor-probe] select_unscanned_coverage: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); no release tag contains it yet.
[core-floor-probe] suggest_unscanned_repair: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); no release tag contains it yet.
[core-floor-probe] summarize_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] unscanned_wire_schema_version: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); no release tag contains it yet.
[core-floor-probe] upsert_notification_with_options: first appears in sase-core 6524f37 (feat(notifications): store oversized payloads in sidecars); no release tag contains it yet.
[core-floor-probe] validate_chop_batch_manifest: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "8cedd45", "name": "agent_artifact_list_wire_schema_version", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "9940715", "name": "agent_hijack_decide", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "9940715", "name": "agent_hijack_eligibility_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_observe", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "9940715", "name": "agent_hijack_select_occupant", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "6524f37", "name": "append_notification_counts_with_options", "release": null, "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "6524f37", "name": "append_notification_with_options", "release": null, "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "6cd9a0c", "name": "apply_chop_batch_transition", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "19b89ac", "name": "artifact_file_association_query", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "19b89ac", "name": "artifact_file_association_query_wire_schema_version", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "3992fce", "name": "artifact_read_audit_query", "release": null, "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "3992fce", "name": "artifact_read_audit_query_wire_schema_version", "release": null, "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "3a32a23", "name": "axe_error_wire_schema_version", "release": null, "subject": "feat(axe-error): add volatile-token normalizer and signature grouping"}, {"commit": "9f9341e", "name": "bead_touch_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "9f9341e", "name": "bead_touch_member_query_wire_schema_version", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "cb76eb2", "name": "bead_triage_owner_candidates", "release": null, "subject": "feat(bead): project triage owner candidates from the read model"}, {"commit": "9f9341e", "name": "bead_view_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "b1a0363", "name": "chop_batch_generation_matches", "release": null, "subject": "feat(axe-chop): add clan-scoped generation match and cancelled settlement"}, {"commit": "6524f37", "name": "compact_notification_store", "release": null, "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "e7647bf", "name": "decide_local_command_trust", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "3c3263f", "name": "decide_publication_standing", "release": null, "subject": "feat(publication): add standing-alert decider with capped backoff"}, {"commit": "e7647bf", "name": "digest_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "filter_trusted_local_layer", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "f0034a7", "name": "gate_failure_resurface_decision", "release": null, "subject": "feat(agent-scan,notifications): project gate failure and dismissal timestamps with shared resurface policy"}, {"commit": "3a32a23", "name": "group_axe_errors", "release": null, "subject": "feat(axe-error): add volatile-token normalizer and signature grouping"}, {"commit": "e9b1cf0", "name": "hijack_latch_force_eligibility", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "hijack_latch_reconcile", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "233cb41", "name": "local_command_trust_store_allow", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_get", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_revoke", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "e7647bf", "name": "local_command_trust_wire_schema_version", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "a4b1c84", "name": "lookup_agent_artifacts", "release": null, "subject": "feat(agent-scan): add read-only indexed artifact identity lookups"}, {"commit": "d201086", "name": "lookup_named_dismissed_bundle", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "c5e60d7", "name": "memory_audit_query", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "c5e60d7", "name": "memory_audit_query_wire_schema_version", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "3a32a23", "name": "normalize_error_signature", "release": null, "subject": "feat(axe-error): add volatile-token normalizer and signature grouping"}, {"commit": "1191f9a", "name": "plan_prompt_command_substitution", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "e7647bf", "name": "project_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "1191f9a", "name": "prompt_command_substitution_wire_schema_version", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "8cedd45", "name": "query_agent_artifact_index_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "6cd9a0c", "name": "reconcile_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "6524f37", "name": "reconcile_notification_rows_with_options", "release": null, "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "6524f37", "name": "resolve_notification_payloads", "release": null, "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "8cedd45", "name": "scan_agent_artifact_dirs_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "8cedd45", "name": "scan_agent_artifacts_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "b9f33b0", "name": "select_agent_artifact_group", "release": null, "subject": "feat(agent-scan): select indexed session and clan generations"}, {"commit": "d201086", "name": "select_named_agent", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "7ac2081", "name": "select_unscanned_coverage", "release": null, "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "7ac2081", "name": "suggest_unscanned_repair", "release": null, "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "6cd9a0c", "name": "summarize_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "7ac2081", "name": "unscanned_wire_schema_version", "release": null, "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "6524f37", "name": "upsert_notification_with_options", "release": null, "subject": "feat(notifications): store oversized payloads in sidecars"}, {"commit": "6cd9a0c", "name": "validate_chop_batch_manifest", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}], "declared_floor": "0.44.2", "exit_code": 4, "message": "sase-core-rs==0.44.2 is missing 54 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✓ docs (build + links)
✗ test (scoped)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 5946 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.12.3, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [63313 items]

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
.................s...................................................... [  4%]
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
.....................................s.................................. [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
...........s............................................................ [ 10%]
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
............s........................................................... [ 15%]
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
................F....................................................... [ 20%]
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
........................................................................ [ 22%]
........................................................................ [ 23%]
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
........................................................................ [ 34%]
..............F......................................................... [ 34%]
.......................F................................................ [ 34%]
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
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
....................................................................F... [ 41%]
...................................s.................................... [ 41%]
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
....F................................................................... [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
................s....................................................... [ 46%]
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
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
......................................F................................. [ 49%]
........................................................................ [ 49%]
.............................F.......................................... [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
.......................................................................s [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
......................................................s.s............... [ 50%]
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
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
......................................................................F. [ 53%]
....F................................................................... [ 53%]
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
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
................................................ssss.................... [ 58%]
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
...F.................................................................... [ 63%]
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
...........................................F............................ [ 65%]
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
.........................................s.............................. [ 71%]
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
........................................................................ [ 84%]
........................................................................ [ 84%]
..................................................s..................... [ 84%]
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
...............................s........................................ [ 91%]
............................................F........................... [ 91%]
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
.........................                                                [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f2f70b25c70>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 497, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______________________ test_no_system_clock_display_sites ______________________
[gw13] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

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
E         src/sase/axe/_lumberjack_core.py:54: return datetime.now() + timedelta(seconds=seconds)
E       assert not ['src/sase/axe/_lumberjack_core.py:54: return datetime.now() + timedelta(seconds=seconds)']

tests/test_timezone_display_guard.py:48: AssertionError
_____ test_project_metadata_loaders_stay_at_reviewed_tui_worker_boundaries _____
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    def test_project_metadata_loaders_stay_at_reviewed_tui_worker_boundaries() -> None:
        """Audited render/navigation flows cannot grow lifecycle metadata I/O."""
        actual: set[tuple[str, str, str]] = set()
        for path in _PROJECT_METADATA_FLOW_FILES:
            tree = parse_source(path)
            parents = parent_map(tree)
            for call in (node for node in ast.walk(tree) if isinstance(node, ast.Call)):
                name = _metadata_loadercall_name(call)
                if name is None:
                    continue
                actual.add((path, enclosing_function(call, parents), name))
    
>       assert actual == set(_ALLOWED_METADATA_LOADERS), (
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
            "project metadata loader sites changed:\n"
            f"unexpected={sorted(actual - set(_ALLOWED_METADATA_LOADERS))}\n"
            f"missing={sorted(set(_ALLOWED_METADATA_LOADERS) - actual)}"
        )
E       AssertionError: project metadata loader sites changed:
E       unexpected=[]
E       missing=[('src/sase/axe/lumberjack.py', '_run_tick', 'refresh_project_display_snapshot')]

tests/_project_display_presentation_audit_metadata.py:142: AssertionError
___________ test_settled_monitor_replay_converges_after_index_upsert ___________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw1/test_settled_monitor_replay_co0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5a48dea4a0>

    @pytest.mark.skipif(
        importlib.util.find_spec(RUST_EXTENSION_MODULE_NAME) is None,
        reason="sase_core_rs is required for the artifact-index incident replay",
    )
    def test_settled_monitor_replay_converges_after_index_upsert(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Replay the stale-session incident through loader, merge, apply, and tokens."""
        sase_home = tmp_path / ".sase"
        monkeypatch.setenv("SASE_HOME", str(sase_home))
        tree = _build_incident_tree(sase_home)
        rebuild_agent_artifact_index(
            default_agent_artifact_index_path(),
            tree.projects_root,
            AgentArtifactScanOptionsWire(),
        )
    
        app = _PreparedApplyHarness()
        failures: list[str] = []
        with patch("sase.ace.agent_tribes.load_agent_tribes", return_value={}):
            initial = _load_bounded_agents("startup")
            _apply_result(app, initial, source="startup")
            initial_tokens = probe_surface_tokens()
            EventAutoRefreshMixin._accept_surface_token(app, "agents", initial_tokens)
    
            if not _load_state_is_bounded(initial.load_state):
                failures.append(
                    f"step 1 expected bounded Tier-1 load, got {initial.load_state}"
                )
            if _statuses_for_suffix(app, _ROOT_TS) != ("EPIC APPROVED",):
                failures.append(
                    f"step 1 root should mirror running monitor, got "
                    f"{_statuses_for_suffix(app, _ROOT_TS)!r}"
                )
            if _statuses_for_suffix(app, _MONITOR_TS) != ("EPIC APPROVED",):
                failures.append(
                    f"step 1 monitor should be running, got "
                    f"{_statuses_for_suffix(app, _MONITOR_TS)!r}"
                )
    
            _settle_monitor(tree)
            settlement_tokens = probe_surface_tokens()
>           if not EventAutoRefreshMixin._surface_token_drifted(
                app,
                settlement_tokens,
                "agents",
            ):

tests/ace/tui/test_agent_session_status_convergence_repro.py:573: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <tests.ace.tui.test_agent_session_status_convergence_repro._PreparedApplyHarness object at 0x7f5a43581e80>
snapshot = SurfaceTokenSnapshot(agents=SurfaceToken(surface='agents', parts=(('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/po...y_co0/.sase/agent_holds.json', False, None, None)), indeterminate=False, part_kinds=('content', 'content', 'content')))
surface = 'agents'

    def _surface_token_drifted(
        self,
        snapshot: SurfaceTokenSnapshot | None,
        surface: str,
    ) -> bool:
        if snapshot is None:
            return True
        last = getattr(self, "_last_completed_surface_tokens", {}).get(surface)
        last_token = last if isinstance(last, SurfaceToken) else None
        if surface == "axe":
            return axe_token_consumer_drifted(
                snapshot.token_for(surface),
                last_token,
                consume_details=self._axe_consumes_detail_parts(),
            )
        drifted = surface_token_drifted(snapshot.token_for(surface), last_token)
        if surface == "agents":
>           kind = self._agents_token_reload_kind(snapshot)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E           AttributeError: '_PreparedApplyHarness' object has no attribute '_agents_token_reload_kind'

src/sase/ace/tui/actions/event_refresh/_auto_refresh_tokens.py:93: AttributeError
----------------------------- Captured stdout call -----------------------------
{"context": "monitor-settlement", "event": "launch_scratch_cleanup", "reason": "no-scratch-key", "removed": 0, "removed_bytes": 0, "scratch_key": null, "skipped": 0, "status": "skipped"}
____________ TestRetryLoop.test_was_killed_during_wait_aborts_retry ____________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.test_axe_run_agent_runner_retry_loop.TestRetryLoop object at 0x7fd35fa8d7b0>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw8/test_was_killed_during_wait_ab0')

    def test_was_killed_during_wait_aborts_retry(self, tmp_path: Path) -> None:
        """was_killed() returning True during sleep aborts the retry loop."""
        patches = base_patches(str(tmp_path / "artifacts"))
        config = make_retry_config(max_retries=2, wait_times=[5])
        execute_mock = MagicMock(side_effect=RuntimeError("rate limit exceeded"))
        patches[f"{EXEC}.get_retry_config"] = MagicMock(return_value=config)
        patches["sase.macro.workflow_runner.execute_workflow"] = execute_mock
    
        kill_calls = 0
    
        def mock_was_killed() -> bool:
            nonlocal kill_calls
            kill_calls += 1
            return kill_calls >= 2
    
        patches[f"{RUNNER}.was_killed"] = mock_was_killed
        patches[f"{EXEC}.was_killed"] = mock_was_killed
        patches[f"{RETRY}.was_killed"] = mock_was_killed
        patches[f"{RETRY}.time.sleep"] = MagicMock()
    
        run_main(patches, tmp_path)
    
>       assert execute_mock.call_count == 1
E       AssertionError: assert 0 == 1
E        +  where 0 = <MagicMock id='140545072404128'>.call_count

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_axe_run_agent_runner_retry_loop.py:173: AssertionError
----------------------------- Captured stdout call -----------------------------
Starting agent run
Patch: test-cl
Workspace: /var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw8/test_was_killed_during_wait_ab0
Workflow: test-workflow

=== Prompt ===
test prompt
==============

Workspace released
{"context": "runner-exit", "event": "launch_scratch_cleanup", "reason": "no-matching-candidates", "removed": 0, "removed_bytes": 0, "scratch_key": "gh_sase-org__sase-ws12-261122_091411", "skipped": 0, "status": "skipped"}
----------------------------- Captured stderr call -----------------------------
Kill source: external (no user-kill intent)
___ test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs ____
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_var_cli_end_to_end_refres0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f022a68cec0>
capsys = <_pytest.capture.CaptureFixture object at 0x7f022e178750>

    def test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        home, projects = isolate_sase_home(tmp_path, monkeypatch)
        current = write_indexed_agent(
            projects,
            project="alpha",
            timestamp="20260815120000",
            name="worker",
            variables={"status": "old"},
        )
        write_indexed_agent(
            projects,
            project="beta",
            timestamp="20260815120500",
            name="worker",
            variables={"status": "beta"},
        )
        write_indexed_agent(
            projects,
            project="alpha",
            timestamp="20260815121000",
            name="hidden",
            variables={"status": "hidden"},
            hidden=True,
        )
        index = rebuild_home_index(home, projects)
        write_agent_artifact_index_meta(
            index,
            "schema_version",
            str(AGENT_ARTIFACT_INDEX_SCHEMA_VERSION - 1),
        )
    
        assert (
            _run_var(["list", "--format", "json", "--key", "status", "--limit", "0"]) == 0
        )
        upgraded = json.loads(capsys.readouterr().out)
        assert upgraded["groups"][0]["key"] == "status"
>       assert int(read_agent_artifact_index_meta(index, "schema_version")) in (
            SUPPORTED_AGENT_ARTIFACT_INDEX_SCHEMA_VERSIONS
        )
E       AssertionError: assert 39 in frozenset({33, 34, 35, 36, 37, 38})
E        +  where 39 = int('39')
E        +    where '39' = read_agent_artifact_index_meta(PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw6/test_var_cli_end_to_end_refres0/sase-home/agent_artifact_index.sqlite'), 'schema_version')

tests/main/test_var_integration.py:73: AssertionError
__________________ test_no_undo_on_shared_monkeypatch_fixture __________________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    def test_no_undo_on_shared_monkeypatch_fixture() -> None:
        """Fail when `.undo()` is called on the injected `monkeypatch` fixture.
    
        Locally constructed `pytest.MonkeyPatch()` instances stay allowed; only
        the function or fixture parameter named `monkeypatch` is guarded. Use
        `monkeypatch.context()` for scoped patches instead.
        """
        offenders: list[str] = []
        for path in sorted(_TESTS_ROOT.rglob("*.py")):
            try:
                text = path.read_text(encoding="utf-8")
            except OSError:
                continue
            if ".undo()" not in text or "monkeypatch" not in text:
                continue
            try:
                tree = ast.parse(text)
            except SyntaxError:
                continue
            for hit in _undo_on_injected_monkeypatch(tree):
                _def_line, call_line = hit.split(":")
                offenders.append(f"{path.relative_to(_REPO_ROOT)}:{call_line}")
>       assert not offenders, (
            "monkeypatch.undo() on the shared fixture drops home isolation; "
            "use monkeypatch.context() instead: " + ", ".join(offenders)
        )
E       AssertionError: monkeypatch.undo() on the shared fixture drops home isolation; use monkeypatch.context() instead: tests/ace/tui/test_native_failure_gc.py:82
E       assert not ['tests/ace/tui/test_native_failure_gc.py:82']

tests/test_pytest_isolation_guards.py:67: AssertionError
_________________ test_session_sandbox_seal_is_not_first_test __________________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

pytester = <Pytester PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_session_sandbox_seal_is_not_first_test0')>

    def test_session_sandbox_seal_is_not_first_test(
        pytester: pytest.Pytester,
    ) -> None:
        """Guarantee the seal test never runs as a worker's first test."""
        result = pytester.runpytest_subprocess(
            "-p",
            "no:randomly",
            "-c",
            str(_REPO_ROOT / "pyproject.toml"),
            "--rootdir",
            str(_REPO_ROOT),
            f"{_THIS_FILE}::test_no_undo_on_shared_monkeypatch_fixture",
            f"{_THIS_FILE}::test_session_sandbox_seals_home_after_function_patches_lost",
            timeout=60,
        )
>       result.assert_outcomes(passed=2)
E       AssertionError: assert {'passed': 1,...rors': 0, ...} == {'passed': 2,...rors': 0, ...}
E         
E         Omitting 4 identical items, use -vv to show
E         Differing items:
E         {'failed': 1} != {'failed': 0}
E         {'passed': 1} != {'passed': 2}
E         Use -v to get more diff

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_pytest_isolation_guards.py:141: AssertionError
----------------------------- Captured stdout call -----------------------------
running: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python -mpytest --basetemp=/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_session_sandbox_seal_is_not_first_test0/runpytest-0 -p no:randomly -c /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/pyproject.toml --rootdir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_pytest_isolation_guards.py::test_session_sandbox_seals_home_after_function_patches_lost
     in: /var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_session_sandbox_seal_is_not_first_test0
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.12.3, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 2 items

../../../../../../../home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_pytest_isolation_guards.py F [ 50%]
.                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.



=================================== FAILURES ===================================
__________________ test_no_undo_on_shared_monkeypatch_fixture __________________

    def test_no_undo_on_shared_monkeypatch_fixture() -> None:
        """Fail when `.undo()` is called on the injected `monkeypatch` fixture.
    
        Locally constructed `pytest.MonkeyPatch()` instances stay allowed; only
        the function or fixture parameter named `monkeypatch` is guarded. Use
        `monkeypatch.context()` for scoped patches instead.
        """
        offenders: list[str] = []
        for path in sorted(_TESTS_ROOT.rglob("*.py")):
            try:
                text = path.read_text(encoding="utf-8")
            except OSError:
                continue
            if ".undo()" not in text or "monkeypatch" not in text:
                continue
            try:
                tree = ast.parse(text)
            except SyntaxError:
                continue
            for hit in _undo_on_injected_monkeypatch(tree):
                _def_line, call_line = hit.split(":")
                offenders.append(f"{path.relative_to(_REPO_ROOT)}:{call_line}")
>       assert not offenders, (
            "monkeypatch.undo() on the shared fixture drops home isolation; "
            "use monkeypatch.context() instead: " + ", ".join(offenders)
        )
E       AssertionError: monkeypatch.undo() on the shared fixture drops home isolation; use monkeypatch.context() instead: tests/ace/tui/test_native_failure_gc.py:82
E       assert not ['tests/ace/tui/test_native_failure_gc.py:82']

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_pytest_isolation_guards.py:67: AssertionError
============================= slowest 20 durations =============================
1.68s setup    tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture
0.27s call     tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
=========================== short test summary info ============================
FAILED ../../../../../../../home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture
========================= 1 failed, 1 passed in 2.54s ==========================
_______________ test_tracked_marker_mutation_sites_are_reviewed ________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

marker_contexts = {'src/sase/ace/tui/actions/agents/_directive_persistence_autonomy.py:persist_autonomy_toggle': ContextInfo(mutation_ca...k',), lifecycle_calls=('delete_agent_artifact_index_artifacts', 'delete_agent_artifact_index_artifacts_bounded')), ...}

    def test_tracked_marker_mutation_sites_are_reviewed(
        marker_contexts: dict[str, ContextInfo],
    ) -> None:
>       assert set(marker_contexts) == set(_REVIEWED_MARKER_MUTATION_CONTEXTS)
E       AssertionError: assert {'src/sase/ac...pproved', ...} == {'src/sase/ac...pproved', ...}
E         
E         Extra items in the left set:
E         'src/sase/axe/run_agent_wait.py:_remove_wait_markers'
E         'src/sase/axe/run_agent_runner.py:_restore_killed_lean_wait_state'
E         Use -v to get more diff

tests/test_agent_artifact_marker_mutation_audit.py:339: AssertionError
_________ test_reviewed_marker_mutation_sites_match_expected_mutations _________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

marker_contexts = {'src/sase/ace/tui/actions/agents/_directive_persistence_autonomy.py:persist_autonomy_toggle': ContextInfo(mutation_ca...k',), lifecycle_calls=('delete_agent_artifact_index_artifacts', 'delete_agent_artifact_index_artifacts_bounded')), ...}

    def test_reviewed_marker_mutation_sites_match_expected_mutations(
        marker_contexts: dict[str, ContextInfo],
    ) -> None:
        expected = {
            context: review.mutation_calls
            for context, review in _REVIEWED_MARKER_MUTATION_CONTEXTS.items()
        }
        actual = {
            context: info.mutation_calls
            for context, info in marker_contexts.items()
            if context in _REVIEWED_MARKER_MUTATION_CONTEXTS
        }
>       assert actual == expected
E       AssertionError: assert {'src/sase/ac...nlink',), ...} == {'src/sase/ac...nlink',), ...}
E         
E         Omitting 42 identical items, use -vv to show
E         Differing items:
E         {'src/sase/axe/run_agent_wait.py:wait_for_dependencies': ('open', 'dump', 'open', 'dump')} != {'src/sase/axe/run_agent_wait.py:wait_for_dependencies': ('unlink', 'open', 'dump', 'unlink', 'open', 'dump', ...)}
E         Use -v to get more diff

tests/test_agent_artifact_marker_mutation_audit.py:354: AssertionError
__________________ test_prompt_rewrite_failure_skips_refresh ___________________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <MagicMock name='execv' id='140615622163632'>

    def assert_not_called(self):
        """assert that the mock was never called.
        """
        if self.call_count != 0:
            msg = ("Expected '%s' to not have been called. Called %s times.%s"
                   % (self._mock_name or 'mock',
                      self.call_count,
                      self._calls_repr()))
>           raise AssertionError(msg)
E           AssertionError: Expected 'execv' to not have been called. Called 1 times.
E           Calls: [call('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python', ['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python', 'sase listen'])].

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:947: AssertionError

During handling of the above exception, another exception occurred:

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_prompt_rewrite_failure_sk0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3a85f6900>
capsys = <_pytest.capture.CaptureFixture object at 0x7fe38a424cd0>

    def test_prompt_rewrite_failure_skips_refresh(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        monkeypatch.delenv(RUNNER_CODE_REFRESHED_ENV, raising=False)
        prompt_file = tmp_path / "missing" / "prompt.md"
        with (
            patch(
                "sase.axe.run_agent_runner_refresh.runner_code_identity",
                return_value="b" * 40,
            ),
            patch("sase.axe.run_agent_runner_refresh.os.execv") as execv,
        ):
            refresh_runner_code_after_wait(
                "a" * 40,
                blocking_wait_occurred=True,
                killed=False,
                prompt_file=str(prompt_file),
                submitted_prompt="prompt",
            )
    
>       execv.assert_not_called()
E       AssertionError: Expected 'execv' to not have been called. Called 1 times.
E       Calls: [call('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python', ['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python', 'sase listen'])].
E       
E       pytest introspection follows:
E       
E       Args:
E       assert ('/home/bryan...sase listen']) == ()
E         
E         Left contains 2 more items, first extra item: '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python'
E         Use -v to get more diff

tests/test_run_agent_runner_refresh_handoff.py:197: AssertionError
----------------------------- Captured stdout call -----------------------------
Refreshing sase runner code after dependency wait: aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa -> bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb
__________ test_runner_forwards_blocking_wait_result_to_code_refresh ___________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <MagicMock name='refresh_runner_code_after_wait' id='140616500688416'>
args = ('3a9eb9d96f751e359b99198563de0dd94fbb6d41',)
kwargs = {'blocking_wait_occurred': True, 'killed': False, 'prompt_file': '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/prompt.md', 'submitted_prompt': '%i(reviewer, session=foo)\nDo work', ...}

    def assert_called_with(self, /, *args, **kwargs):
        """assert that the last call was made with the specified arguments.
    
        Raises an AssertionError if the args and keyword args passed in are
        different to the last call to the mock."""
        if self.call_args is None:
            expected = self._format_mock_call_signature(args, kwargs)
            actual = 'not called.'
            error_message = ('expected call not found.\nExpected: %s\n  Actual: %s'
                    % (expected, actual))
            raise AssertionError(error_message)
    
        def _error_message():
            msg = self._format_mock_failure_message(args, kwargs)
            return msg
        expected = self._call_matcher(_Call((args, kwargs), two=True))
        actual = self._call_matcher(self.call_args)
        if actual != expected:
            cause = expected if isinstance(expected, Exception) else None
>           raise AssertionError(_error_message()) from cause
E           AssertionError: expected call not found.
E           Expected: refresh_runner_code_after_wait('3a9eb9d96f751e359b99198563de0dd94fbb6d41', blocking_wait_occurred=True, killed=False, prompt_file='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/prompt.md', submitted_prompt='%i(reviewer, session=foo)\nDo work', agent_name='foo--reviewer', artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/artifacts', local_macros={}, is_killed=<function was_killed at 0x7fe3cc14e4b0>)
E             Actual: refresh_runner_code_after_wait('3a9eb9d96f751e359b99198563de0dd94fbb6d41', blocking_wait_occurred=True, killed=False, prompt_file='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/prompt.md', submitted_prompt='%i(reviewer, session=foo)\nDo work', agent_name='foo--reviewer', artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/artifacts', local_macros={}, is_killed=<MagicMock name='was_killed' id='140616500690096'>)

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:986: AssertionError

During handling of the above exception, another exception occurred:

self = <MagicMock name='refresh_runner_code_after_wait' id='140616500688416'>
args = ('3a9eb9d96f751e359b99198563de0dd94fbb6d41',)
kwargs = {'blocking_wait_occurred': True, 'killed': False, 'prompt_file': '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/prompt.md', 'submitted_prompt': '%i(reviewer, session=foo)\nDo work', ...}

    def assert_called_once_with(self, /, *args, **kwargs):
        """assert that the mock was called exactly once and that that call was
        with the specified arguments."""
        if not self.call_count == 1:
            msg = ("Expected '%s' to be called once. Called %s times.%s"
                   % (self._mock_name or 'mock',
                      self.call_count,
                      self._calls_repr()))
            raise AssertionError(msg)
>       return self.assert_called_with(*args, **kwargs)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AssertionError: expected call not found.
E       Expected: refresh_runner_code_after_wait('3a9eb9d96f751e359b99198563de0dd94fbb6d41', blocking_wait_occurred=True, killed=False, prompt_file='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/prompt.md', submitted_prompt='%i(reviewer, session=foo)\nDo work', agent_name='foo--reviewer', artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/artifacts', local_macros={}, is_killed=<function was_killed at 0x7fe3cc14e4b0>)
E         Actual: refresh_runner_code_after_wait('3a9eb9d96f751e359b99198563de0dd94fbb6d41', blocking_wait_occurred=True, killed=False, prompt_file='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/prompt.md', submitted_prompt='%i(reviewer, session=foo)\nDo work', agent_name='foo--reviewer', artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/artifacts', local_macros={}, is_killed=<MagicMock name='was_killed' id='140616500690096'>)
E       
E       pytest introspection follows:
E       
E       Kwargs:
E       assert {'blocking_wa...Do work', ...} == {'blocking_wa...Do work', ...}
E         
E         Omitting 7 identical items, use -vv to show
E         Differing items:
E         {'is_killed': <MagicMock name='was_killed' id='140616500690096'>} != {'is_killed': <function was_killed at 0x7fe3cc14e4b0>}
E         Use -v to get more diff

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:998: AssertionError

During handling of the above exception, another exception occurred:

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0')

    def test_runner_forwards_blocking_wait_result_to_code_refresh(tmp_path: Path) -> None:
        result = _run_runner_with_wait_result(tmp_path, True)
    
        refresh = result["refresh_runner_code_after_wait"]
        assert isinstance(refresh, MagicMock)
>       refresh.assert_called_once_with(
            run_agent_runner._STARTUP_CODE_IDENTITY,
            blocking_wait_occurred=True,
            killed=False,
            prompt_file=str(tmp_path / "prompt.md"),
            submitted_prompt="%i(reviewer, session=foo)\nDo work",
            agent_name="foo--reviewer",
            artifacts_dir=str(tmp_path / "artifacts"),
            local_macros={},
            is_killed=run_agent_runner.was_killed,
        )
E       AssertionError: expected call not found.
E       Expected: refresh_runner_code_after_wait('3a9eb9d96f751e359b99198563de0dd94fbb6d41', blocking_wait_occurred=True, killed=False, prompt_file='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/prompt.md', submitted_prompt='%i(reviewer, session=foo)\nDo work', agent_name='foo--reviewer', artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/artifacts', local_macros={}, is_killed=<function was_killed at 0x7fe3cc14e4b0>)
E         Actual: refresh_runner_code_after_wait('3a9eb9d96f751e359b99198563de0dd94fbb6d41', blocking_wait_occurred=True, killed=False, prompt_file='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/prompt.md', submitted_prompt='%i(reviewer, session=foo)\nDo work', agent_name='foo--reviewer', artifacts_dir='/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw12/test_runner_forwards_blocking_0/artifacts', local_macros={}, is_killed=<MagicMock name='was_killed' id='140616500690096'>)
E       
E       pytest introspection follows:
E       
E       Kwargs:
E       assert {'blocking_wa...Do work', ...} == {'blocking_wa...Do work', ...}
E         
E         Omitting 7 identical items, use -vv to show
E         Differing items:
E         {'is_killed': <MagicMock name='was_killed' id='140616500690096'>} != {'is_killed': <function was_killed at 0x7fe3cc14e4b0>}
E         Use -v to get more diff

tests/test_run_agent_runner_wait_queue.py:370: AssertionError
----------------------------- Captured stdout call -----------------------------
⚠️ wait_chats: no done agent found for 'foo' — skipping

Agent completed with status: SUCCESS
Duration: 0s
{"context": "runner-exit", "event": "launch_scratch_cleanup", "reason": "no-matching-candidates", "removed": 0, "removed_bytes": 0, "scratch_key": "gh_sase-org__sase-ws12-261122_091411", "skipped": 0, "status": "skipped"}
________ test_plan_protects_live_continuation_ancestry_from_audit_probe ________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw7/test_plan_protects_live_contin0')

    def test_plan_protects_live_continuation_ancestry_from_audit_probe(
        tmp_path: Path,
    ) -> None:
        projects_root = tmp_path / "projects"
        old = _run_dir(
            projects_root,
            "proj",
            "20260501000000",
            meta={"continuation_node_id": "agent-delta:old"},
        )
        live = _run_dir(
            projects_root,
            "proj",
            "20260901000000",
            done=False,
            running=True,
            meta={
                "continuation_parent_node_ids": ["agent-delta:old"],
                "monitor_starter_artifacts_dir": str(old),
            },
        )
        unrelated = _run_dir(projects_root, "proj", "20260401000000")
        snapshot = protection.collect_ace_run_retention_protections(
            projects_root=projects_root,
            artifact_index_path=tmp_path / "missing.sqlite",
            inventory=RepoInventory(()),
        )
    
        plan = plan_ace_run_retention(_policy(projects_root), protections=snapshot)
    
        selected = {Path(item.artifact_dir) for item in plan.selected}
        reasons = {Path(item.artifact_dir): set(item.reasons) for item in plan.protected}
        assert unrelated in selected
>       assert old not in selected
E       AssertionError: assert PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw7/test_plan_protects_live_contin0/projects/proj/artifacts/ace-run/202605/01/20260501000000') not in {PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw7/test_plan_protects_live_contin0/projects/proj/ar...of-bryan/pytest-0/popen-gw7/test_plan_protects_live_contin0/projects/proj/artifacts/ace-run/202605/01/20260501000000')}

tests/core/test_continuation_retention.py:90: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/core/content_layout_wire.py:330: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    formats=tuple(str(item) for item in raw.get("formats", [])),
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/macro/workflow_runner_execute.py:254: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/macro/workflow_runner_flatten.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/macro/workflow_runner_flatten.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = flatten_anonymous_workflow(workflow)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=443560) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=443646) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorHostFinalizer::test_genuine_provider_500_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorHostFinalizer::test_genuine_provider_500_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-0/popen-gw8/test_was_killed_during_wait_ab0'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/textual/css/tokenizer.py:289: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    match = expect.match(line, col_no)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object _record_history_async.<locals>._record at 0x7f2785af68a0>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=443530) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object CommandLineScreenSubmissionMixin._submit_worker at 0x7f277493b560>: None
  
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/main/parser_gettext.py:54: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    tuple(os.environ.get(key) for key in _GETTEXT_ENV_KEYS)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_bootstrap_errors.py::test_preprocessing_failure_records_failed_done_and_finalizes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_bootstrap_errors.py::test_preprocessing_failure_records_failed_done_and_finalizes changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_bootstrap_errors.py::test_refreshed_bootstrap_preserves_phase_launch_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_bootstrap_errors.py::test_refreshed_bootstrap_preserves_phase_launch_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_bootstrap_errors.py::test_user_kill_during_bootstrap_preserves_exit_and_skips_error_recording
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_bootstrap_errors.py::test_user_kill_during_bootstrap_preserves_exit_and_skips_error_recording changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=443506) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/ace/tui/_agent_archive_column_helpers.py:49: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    "last_activity_at": f"{day}T{hour:02d}:00:00Z",
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=443646) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=443560) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/ace/tui/test_refresh_freshness.py::test_manual_refresh_stamps_requested_surface[artifacts-patches-patches]
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:110: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    def deepcopy(x, memo=None, _nil=[]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/actions/_launchable_mru.py:308: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_axe_chop_batch_store.py::test_stale_and_live_ownership
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/axe/test_axe_chop_batch_store.py:220: DeprecationWarning: This process (pid=443506) is multi-threaded, use of fork() may lead to deadlocks in the child.
    pid = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
63.47s call     tests/test_launch_request_staging.py::test_typed_plan_and_continuation_survive_adoption
63.06s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
53.50s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
50.96s call     tests/continuation/test_launch_local_capture_chain.py::test_twenty_launch_agent_monitor_cycles_keep_only_local_authored_text
33.66s call     tests/monitor/test_monitor_start_ack.py::test_startup_sigterm_settles_stopped_without_running_command
33.03s call     tests/ace/tui/test_refresh_warmup_gc.py::test_auto_refresh_merge_live_hints_and_warmup_release_obsolete_payloads
32.45s call     tests/monitor/test_monitor_start_stage_adopt.py::test_session_member_staged_join_reserves_env_starter_identity
32.21s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
27.18s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
26.85s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
26.31s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
24.44s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
23.53s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
21.38s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
21.34s call     tests/fakey/test_agent_hijack_canary.py::test_monitor_hijack_continue_same_workspace
20.39s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
18.07s call     tests/test_axe_error_groups.py::test_loud_signature_cannot_evict_rare_ones
17.08s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
16.39s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
16.33s call     tests/fakey/test_agent_hijack_canary.py::test_monitor_hijack_rerun_same_workspace
=========================== short test summary info ============================
FAILED tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
FAILED tests/test_project_display_presentation_audit.py::test_project_metadata_loaders_stay_at_reviewed_tui_worker_boundaries
FAILED tests/ace/tui/test_agent_session_status_convergence_repro.py::test_settled_monitor_replay_converges_after_index_upsert
FAILED tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
FAILED tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs
FAILED tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture
FAILED tests/test_pytest_isolation_guards.py::test_session_sandbox_seal_is_not_first_test
FAILED tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
FAILED tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_match_expected_mutations
FAILED tests/test_run_agent_runner_refresh_handoff.py::test_prompt_rewrite_failure_skips_refresh
FAILED tests/test_run_agent_runner_wait_queue.py::test_runner_forwards_blocking_wait_result_to_code_refresh
FAILED tests/core/test_continuation_retention.py::test_plan_protects_live_continuation_ancestry_from_audit_probe
==== 12 failed, 63285 passed, 17 skipped, 164 warnings in 870.46s (0:14:30) ====
error: recipe `test-scoped` failed on line 696 with exit code 1
error: recipe `check` failed on line 977 with exit code 1
failed  exit=1  duration=2350704ms
unattrib  19m 35s
triage test (scoped): 3 FLAKY 2 KNOWN 8 NEW stopped
NEW test (scoped): FAILED tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry — recorded evidence; no owner
NEW test (scoped): FAILED tests/core/test_continuation_retention.py::test_plan_protects_live_continuation_ancestry_from_audit_probe — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/test_agent_session_status_convergence_repro.py::test_settled_monitor_replay_converges_after_index_upsert — recorded evidence; no owner
NEW test (scoped): FAILED ../../../../../../..tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_pytest_isolation_guards.py::test_session_sandbox_seal_is_not_first_test — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture — recorded evidence; no owner
NEW test (scoped): FAILED tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_run_agent_runner_refresh_handoff.py::test_prompt_rewrite_failure_skips_refresh — recorded evidence; no owner
KNOWN test (scoped): FAILED tests/test_timezone_display_guard.py::test_no_system_clock_display_sites — witness c870023d890311519be12b58a917d769; no owner
KNOWN test (scoped): FAILED tests/test_project_display_presentation_audit.py::test_project_metadata_loaders_stay_at_reviewed_tui_worker_boundaries — witness 7299a65a71dd99310bc2d167a4fe275d; no owner
FLAKY test (scoped): FAILED tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_match_expected_mutations — recorded evidence; no owner
FLAKY test (scoped): FAILED tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed — recorded evidence; no owner
FLAKY test (scoped): FAILED tests/test_run_agent_runner_wait_queue.py::test_runner_forwards_blocking_wait_result_to_code_refresh — recorded evidence; no owner
verdict: new_failures — 8 NEW, 2 KNOWN, 3 FLAKY; exit 1

