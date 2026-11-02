# Chat History - ace-run (sase-1pj.7.1.4--mon)

- **TIMESTAMP:** 2026-11-02 16:09:02 EST
- **MODEL:** codex/gpt-6-astra
- **AGENT:** sase-1pj.7.1.4--mon

## Prompt

sase monitor start --command 'just --set sase_core_dir sase/repos/linked/sase-core install-venv && .venv/bin/python -m pytest -q --tb=short tests/core/test_workspace_retention.py tests/turns/test_workspace_retention.py tests/test_stale_running_cleanup_held_claims.py tests/test_stranded_collector_recovery.py tests/test_stranded_work_facade.py tests/ace/tui/actions/test_workspace_retention_dismissal.py tests/ace/tui/widgets/test_identity_header_compact.py tests/test_run_agent_runner_notifications.py' --reason 'Restore the local Rust binding and verify landed recovery-surfaces work before phase closure'

## Response

sase tool run 1a07af2d9d76ac4435a9d510ee499c89
[install-venv] Installing local sase_core_rs from sase/repos/linked/sase-core for local dev.
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[rust-install] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev builds from sase/repos/linked/sase-core ignore it. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python
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
   Compiling stable_deref_trait v1.2.1
   Compiling target-lexicon v0.12.16
   Compiling futures-sink v0.3.32
   Compiling crossbeam-deque v0.8.8
   Compiling hashbrown v0.17.0
   Compiling equivalent v1.0.2
   Compiling slab v0.4.12
   Compiling futures-io v0.3.32
   Compiling futures-task v0.3.32
   Compiling tower-service v0.3.3
   Compiling ucd-trie v0.1.7
   Compiling iana-time-zone v0.1.65
   Compiling bitflags v2.11.1
   Compiling heck v0.5.0
   Compiling untrusted v0.9.0
   Compiling libm v0.2.16
   Compiling same-file v1.0.6
   Compiling litemap v0.8.2
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling typenum v1.20.0
   Compiling icu_normalizer_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling httpdate v1.0.3
   Compiling lazy_static v1.5.0
   Compiling tower-layer v0.3.3
   Compiling fnv v1.0.7
   Compiling deunicode v1.6.2
   Compiling parking_lot_core v0.9.12
   Compiling scopeguard v1.2.0
   Compiling sync_wrapper v1.0.2
   Compiling encoding_rs v0.8.35
   Compiling tracing-core v0.1.36
   Compiling percent-encoding v2.3.2
   Compiling ryu v1.0.23
   Compiling clap_lex v1.1.1
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling unicode-segmentation v1.13.3
   Compiling num-traits v0.2.19
   Compiling rustls v0.21.12
   Compiling thiserror v1.0.69
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling pkg-config v0.3.33
   Compiling anstyle v1.0.14
   Compiling vcpkg v0.2.15
   Compiling try-lock v0.2.5
   Compiling rustix v1.1.4
   Compiling powerfmt v0.2.0
   Compiling time-core v0.1.8
   Compiling walkdir v2.5.0
   Compiling thiserror v2.0.18
   Compiling futures-channel v0.3.32
   Compiling slug v0.1.6
   Compiling winnow v1.0.4
   Compiling rustversion v1.0.22
   Compiling getrandom v0.4.2
   Compiling num-conv v0.2.1
   Compiling aho-corasick v1.1.4
   Compiling cc v1.2.61
   Compiling bstr v1.13.1
   Compiling colored v2.2.0
   Compiling indexmap v2.14.0
   Compiling pyo3-build-config v0.22.6
   Compiling winnow v0.7.15
   Compiling http v1.4.0
   Compiling http v0.2.12
   Compiling linux-raw-sys v0.12.1
   Compiling cpufeatures v0.2.17
   Compiling mime v0.3.17
   Compiling phf_shared v0.11.3
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling home v0.5.12
   Compiling atomic-waker v1.1.2
   Compiling crossbeam-channel v0.5.17
   Compiling humansize v2.1.3
   Compiling grep-matcher v0.1.9
   Compiling lock_api v0.4.14
   Compiling want v0.3.1
   Compiling memoffset v0.9.1
   Compiling base64 v0.21.7
   Compiling fallible-streaming-iterator v0.1.9
   Compiling itertools v0.11.0
   Compiling tinyvec v1.13.3
   Compiling unsafe-libyaml v0.2.11
   Compiling base64 v0.22.1
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling getrandom v0.2.17
   Compiling mio v1.2.0
   Compiling clap_builder v4.6.7
   Compiling socket2 v0.5.10
   Compiling memmap2 v0.9.11
   Compiling term_size v0.3.2
   Compiling fastrand v2.4.1
   Compiling form_urlencoded v1.2.2
   Compiling fallible-iterator v0.3.0
   Compiling deranged v0.5.8
   Compiling fs2 v0.4.3
   Compiling tracing-log v0.2.0
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling sharded-slab v0.1.7
   Compiling thread_local v1.1.9
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling libsqlite3-sys v0.30.1
   Compiling time-macros v0.2.27
   Compiling http-body v0.4.6
   Compiling phf v0.11.3
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling serde_spanned v1.1.2
   Compiling serde_path_to_error v0.1.20
   Compiling regex-automata v0.4.14
   Compiling nu-ansi-term v0.50.3
   Compiling hex v0.4.3
   Compiling encoding_rs_io v0.1.8
   Compiling etcetera v0.8.0
   Compiling semver v1.0.28
   Compiling matchit v0.7.3
   Compiling unicode-width v0.2.2
   Compiling http-body v1.0.1
   Compiling ipnet v2.12.0
   Compiling unicode-casefold v0.2.0
   Compiling webpki-roots v0.25.4
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling rustls-pemfile v1.0.4
   Compiling pyo3 v0.22.6
   Compiling rand_core v0.6.4
   Compiling sync_wrapper v0.1.2
   Compiling indoc v2.0.7
   Compiling signal-hook-registry v1.4.8
   Compiling pem v3.0.6
   Compiling unindent v0.2.4
   Compiling unicode-normalization v0.1.25
   Compiling num-integer v0.1.46
   Compiling chrono v0.4.44
   Compiling crypto-common v0.1.7
   Compiling block-buffer v0.10.4
   Compiling parking_lot v0.12.5
   Compiling ppv-lite86 v0.2.21
   Compiling toml v0.9.12+spec-1.1.0
   Compiling time v0.3.47
   Compiling grep-searcher v0.1.17
   Compiling http-body-util v0.1.3
   Compiling digest v0.10.7
   Compiling num-bigint v0.4.6
   Compiling hashbrown v0.14.5
   Compiling pest v2.9.4
   Compiling tempfile v3.27.0
   Compiling rand_chacha v0.3.1
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling rayon v1.12.0
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling hashlink v0.9.1
   Compiling rand v0.8.6
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling pest_meta v2.9.4
   Compiling phf_generator v0.11.3
   Compiling phf_codegen v0.11.3
   Compiling globwalk v0.9.1
   Compiling chrono-tz-build v0.3.0
   Compiling chrono-tz v0.9.0
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling arbitrary v1.5.0
   Compiling synstructure v0.13.2
   Compiling pest_derive v2.9.4
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
   Compiling clap v4.6.7
   Compiling async-stream v0.3.6
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling tracing v0.1.44
   Compiling clap-cargo v0.18.3
   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
   Compiling zerofrom v0.1.7
   Compiling table_formatter v0.6.1
   Compiling simple_asn1 v0.6.4
   Compiling tower-http v0.5.2
   Compiling yoke v0.8.2
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling json5 v0.4.1
   Compiling serde_urlencoded v0.7.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling pyo3-macros v0.22.6
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling matchers v0.2.0
   Compiling icu_collections v2.2.0
   Compiling icu_locale_core v2.2.0
   Compiling tracing-subscriber v0.3.23
   Compiling axum-core v0.4.5
   Compiling tokei v15.0.0
   Compiling icu_provider v2.2.0
   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling idna_adapter v1.2.2
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling tokio-rustls v0.24.1
   Compiling hyper v1.9.0
   Compiling idna v1.1.0
   Compiling h2 v0.3.27
   Compiling url v2.5.8
   Compiling hyper-util v0.1.20
   Compiling axum v0.7.9
   Compiling hyper v0.14.32
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_gateway v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 14m 52s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-oozk4rsp/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/53948e5395355ba76ef6c69ac42dfb46e517ec6d86fad08aeaa1d296c742b5eb/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 2ms
Prepared 1 package in 150ms
Uninstalled 1 package in 1ms
Installed 1 package in 2ms
 - sase-core-rs==0.43.2
 + sase-core-rs==0.43.3 (from file:///home/bryan/.sase/cache/sase-core-artifacts/53948e5395355ba76ef6c69ac42dfb46e517ec6d86fad08aeaa1d296c742b5eb/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: no exact cached wheel
   Compiling libc v0.2.186
   Compiling proc-macro2 v1.0.106
   Compiling quote v1.0.45
   Compiling unicode-ident v1.0.24
   Compiling zerocopy v0.8.48
   Compiling memchr v2.8.0
   Compiling cfg-if v1.0.4
   Compiling serde_core v1.0.228
   Compiling crossbeam-utils v0.8.21
   Compiling find-msvc-tools v0.1.9
   Compiling shlex v1.3.0
   Compiling regex-syntax v0.8.10
   Compiling version_check v0.9.5
   Compiling siphasher v1.0.4
   Compiling autocfg v1.5.0
   Compiling serde v1.0.228
   Compiling crossbeam-epoch v0.9.21
   Compiling zmij v1.0.21
   Compiling once_cell v1.21.4
   Compiling serde_json v1.0.149
   Compiling crossbeam-deque v0.8.8
   Compiling log v0.4.29
   Compiling pin-project-lite v0.2.17
   Compiling iana-time-zone v0.1.65
   Compiling equivalent v1.0.2
   Compiling hashbrown v0.17.0
   Compiling ucd-trie v0.1.7
   Compiling smallvec v1.15.1
   Compiling bitflags v2.11.1
   Compiling itoa v1.0.18
   Compiling futures-core v0.3.32
   Compiling libm v0.2.16
   Compiling same-file v1.0.6
   Compiling futures-sink v0.3.32
   Compiling parking_lot_core v0.9.12
   Compiling typenum v1.20.0
   Compiling bytes v1.11.1
   Compiling scopeguard v1.2.0
   Compiling futures-io v0.3.32
   Compiling lazy_static v1.5.0
   Compiling slab v0.4.12
   Compiling futures-task v0.3.32
   Compiling deunicode v1.6.2
   Compiling pkg-config v0.3.33
   Compiling percent-encoding v2.3.2
   Compiling vcpkg v0.2.15
   Compiling thiserror v1.0.69
   Compiling heck v0.5.0
   Compiling unicode-segmentation v1.13.3
   Compiling anstyle v1.0.14
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling clap_lex v1.1.1
   Compiling num-traits v0.2.19
   Compiling getrandom v0.4.2
   Compiling tower-service v0.3.3
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling cc v1.2.61
   Compiling winnow v1.0.4
   Compiling aho-corasick v1.1.4
   Compiling phf_shared v0.11.3
   Compiling bstr v1.13.1
   Compiling encoding_rs v0.8.35
   Compiling rustix v1.1.4
   Compiling tracing-core v0.1.36
   Compiling sync_wrapper v1.0.2
   Compiling tower-layer v0.3.3
   Compiling itertools v0.11.0
   Compiling colored v2.2.0
   Compiling grep-matcher v0.1.9
   Compiling cpufeatures v0.2.17
   Compiling winnow v0.7.15
   Compiling bitflags v1.3.2
   Compiling httparse v1.10.1
   Compiling futures-channel v0.3.32
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling linux-raw-sys v0.12.1
   Compiling home v0.5.12
   Compiling unsafe-libyaml v0.2.11
   Compiling walkdir v2.5.0
   Compiling lock_api v0.4.14
   Compiling clap_builder v4.6.7
   Compiling fastrand v2.4.1
   Compiling tinyvec v1.13.3
   Compiling fallible-iterator v0.3.0
   Compiling slug v0.1.6
   Compiling ryu v1.0.23
   Compiling fallible-streaming-iterator v0.1.9
   Compiling sharded-slab v0.1.7
   Compiling thread_local v1.1.9
   Compiling nu-ansi-term v0.50.3
   Compiling unicode-width v0.2.2
   Compiling hex v0.4.3
   Compiling unicode-casefold v0.2.0
   Compiling semver v1.0.28
   Compiling crossbeam-channel v0.5.17
   Compiling indexmap v2.14.0
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling serde_spanned v1.1.2
   Compiling getrandom v0.2.17
   Compiling ppv-lite86 v0.2.21
   Compiling phf v0.11.3
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling errno v0.3.14
   Compiling mio v1.2.0
   Compiling socket2 v0.6.3
   Compiling regex-automata v0.4.14
   Compiling humansize v2.1.3
   Compiling memmap2 v0.9.11
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling libsqlite3-sys v0.30.1
   Compiling term_size v0.3.2
   Compiling encoding_rs_io v0.1.8
   Compiling fs2 v0.4.3
   Compiling tracing-log v0.2.0
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling etcetera v0.8.0
   Compiling fluent-uri v0.1.4
   Compiling unicode-normalization v0.1.25
   Compiling rand_core v0.6.4
   Compiling signal-hook-registry v1.4.8
   Compiling toml v0.9.12+spec-1.1.0
   Compiling parking_lot v0.12.5
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling hashbrown v0.14.5
   Compiling grep-searcher v0.1.17
   Compiling digest v0.10.7
   Compiling matchers v0.2.0
   Compiling chrono v0.4.44
   Compiling rand_chacha v0.3.1
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling tempfile v3.27.0
   Compiling hashlink v0.9.1
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling pest v2.9.4
   Compiling rayon v1.12.0
   Compiling rand v0.8.6
   Compiling globwalk v0.9.1
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling pest_meta v2.9.4
   Compiling phf_generator v0.11.3
   Compiling phf_codegen v0.11.3
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling serde_derive v1.0.228
   Compiling tracing-attributes v0.1.31
   Compiling futures-macro v0.3.32
   Compiling tokio-macros v2.7.0
   Compiling thiserror-impl v1.0.69
   Compiling serde_repr v0.1.20
   Compiling chrono-tz-build v0.3.0
   Compiling arbitrary v1.5.0
   Compiling pest_derive v2.9.4
   Compiling tokio v1.52.2
   Compiling chrono-tz v0.9.0
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling clap v4.6.7
   Compiling tracing-subscriber v0.3.23
   Compiling table_formatter v0.6.1
   Compiling clap-cargo v0.18.3
   Compiling futures v0.3.32
   Compiling tower v0.5.3
   Compiling tokio-util v0.7.18
   Compiling dashmap v6.1.0
   Compiling lsp-types v0.97.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling tokei v15.0.0
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_macro_lsp v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Finished `dev-update` profile [optimized] target(s) in 1m 08s
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/7707dceaea799c4a5a11b8f8f1ead5812a1d1f03d6bb318b0e86586b6d06cabc/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/sase-macro-lsp
uv pip install --python .venv/bin/python --no-sources $(just --set venv_dir ".venv" --set sase_core_dir "sase/repos/linked/sase-core" _core-overrides-arg) -e ".[dev]"
Resolved 98 packages in 243ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
Prepared 1 package in 490ms
Uninstalled 1 package in 3ms
Installed 1 package in 5ms
 ~ sase==0.18.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
........................................................................ [ 61%]
.............................................                            [100%]
============================= slowest 20 durations =============================
0.07s setup    tests/core/test_workspace_retention.py::test_schema_version_matches_binding
0.06s call     tests/turns/test_workspace_retention.py::test_late_retention_publishes_recovery_notification
0.06s call     tests/ace/tui/widgets/test_identity_header_compact.py::test_agent_rows_carry_name_model_and_state
0.05s call     tests/turns/test_workspace_retention.py::test_primary_clean_linked_dirty_retains
0.04s call     tests/turns/test_workspace_retention.py::test_repeated_hold_is_idempotent
0.04s call     tests/turns/test_workspace_retention.py::test_explicit_dismissal_releases_exact_retained_claim_and_settles_record
0.04s call     tests/turns/test_workspace_retention.py::test_session_owned_dirt_pins_and_persists_record
0.03s call     tests/turns/test_workspace_retention.py::test_staged_and_untracked_edits_retain
0.03s call     tests/ace/tui/widgets/test_identity_header_compact.py::test_clan_rows_carry_name_status_and_count_chip
0.03s call     tests/turns/test_workspace_retention.py::test_missing_baseline_with_custody_retains
0.03s call     tests/turns/test_workspace_retention.py::test_claim_transfer_racing_settlement_is_noop
0.03s call     tests/ace/tui/widgets/test_identity_header_compact.py::test_tribe_rows_carry_label_status_and_fold
0.03s call     tests/ace/tui/widgets/test_identity_header_compact.py::test_clan_rows_overflow_tribe_chips_after_three
0.03s call     tests/ace/tui/widgets/test_identity_header_compact.py::test_clan_compact_second_line_starts_with_project_label
0.03s call     tests/ace/tui/widgets/test_identity_header_compact.py::test_clan_headers_omit_project_fields_without_labels
0.03s call     tests/turns/test_workspace_retention.py::test_explicit_dismissal_preserves_reused_claim_and_unresolved_record
0.03s call     tests/turns/test_workspace_retention.py::test_historical_carried_to_does_not_count_as_successor
0.03s call     tests/turns/test_workspace_retention.py::test_different_workspace_successor_retains_original
0.03s call     tests/turns/test_workspace_retention.py::test_unchanged_foreign_dirt_releases
0.02s setup    tests/ace/tui/actions/test_workspace_retention_dismissal.py::test_dismiss_releases_live_gate_claim_only_for_its_retention_record
117 passed in 4.36s
succeeded  exit=0  duration=976379ms

