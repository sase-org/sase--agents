# Chat History - ace-run (sase-1sl.3--mon)

- **TIMESTAMP:** 2026-11-12 18:03:32 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1sl.3--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'finish check (joined run)'

## Response

Local commands in /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/sase.yml were skipped (no-acknowledgment); run `sase config trust allow /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/sase.yml` after review.
sase tool run 1b260240f986521dbf1d2d9caf7fe43c
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core to origin/master
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
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling proc-macro2 v1.0.106
   Compiling unicode-ident v1.0.24
   Compiling quote v1.0.45
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
   Compiling regex-syntax v0.8.10
   Compiling bytes v1.11.1
   Compiling serde v1.0.228
   Compiling log v0.4.29
   Compiling siphasher v1.0.4
   Compiling version_check v0.9.5
   Compiling zmij v1.0.21
   Compiling futures-core v0.3.32
   Compiling crossbeam-epoch v0.9.21
   Compiling smallvec v1.15.1
   Compiling serde_json v1.0.149
   Compiling futures-sink v0.3.32
   Compiling crossbeam-deque v0.8.8
   Compiling target-lexicon v0.12.16
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
   Compiling same-file v1.0.6
   Compiling heck v0.5.0
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling untrusted v0.9.0
   Compiling libm v0.2.16
   Compiling litemap v0.8.2
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
   Compiling encoding_rs v0.8.35
   Compiling clap_lex v1.1.1
   Compiling unicode-segmentation v1.13.3
   Compiling rayon-core v1.13.0
   Compiling cc v1.2.61
   Compiling num-traits v0.2.19
   Compiling phf_shared v0.11.3
   Compiling aho-corasick v1.1.4
   Compiling tracing-core v0.1.36
   Compiling bstr v1.13.1
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling either v1.19.0
   Compiling rustls v0.21.12
   Compiling thiserror v1.0.69
   Compiling pkg-config v0.3.33
   Compiling anstyle v1.0.14
   Compiling vcpkg v0.2.15
   Compiling percent-encoding v2.3.2
   Compiling scopeguard v1.2.0
   Compiling sync_wrapper v1.0.2
   Compiling ryu v1.0.23
   Compiling winnow v1.0.4
   Compiling rustversion v1.0.22
   Compiling getrandom v0.4.2
   Compiling http v1.4.0
   Compiling walkdir v2.5.0
   Compiling num-conv v0.2.1
   Compiling slug v0.1.6
   Compiling try-lock v0.2.5
   Compiling futures-channel v0.3.32
   Compiling indexmap v2.14.0
   Compiling http v0.2.12
   Compiling rustix v1.1.4
   Compiling powerfmt v0.2.0
   Compiling time-core v0.1.8
   Compiling thiserror v2.0.18
   Compiling grep-matcher v0.1.9
   Compiling cpufeatures v0.2.17
   Compiling mime v0.3.17
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling colored v2.2.0
   Compiling home v0.5.12
   Compiling atomic-waker v1.1.2
   Compiling winnow v0.7.15
   Compiling pyo3-build-config v0.22.6
   Compiling linux-raw-sys v0.12.1
   Compiling itertools v0.11.0
   Compiling crossbeam-channel v0.5.17
   Compiling regex-automata v0.4.14
   Compiling phf v0.11.3
   Compiling clap_builder v4.6.7
   Compiling form_urlencoded v1.2.2
   Compiling memoffset v0.9.1
   Compiling tinyvec v1.13.3
   Compiling unsafe-libyaml v0.2.11
   Compiling base64 v0.22.1
   Compiling fastrand v2.4.1
   Compiling fallible-iterator v0.3.0
   Compiling fallible-streaming-iterator v0.1.9
   Compiling base64 v0.21.7
   Compiling tracing-log v0.2.0
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling getrandom v0.2.17
   Compiling humansize v2.1.3
   Compiling lock_api v0.4.14
   Compiling num-integer v0.1.46
   Compiling chrono v0.4.44
   Compiling memmap2 v0.9.11
   Compiling socket2 v0.5.10
   Compiling serde_spanned v1.1.2
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling encoding_rs_io v0.1.8
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling term_size v0.3.2
   Compiling serde_path_to_error v0.1.20
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling libsqlite3-sys v0.30.1
   Compiling want v0.3.1
   Compiling etcetera v0.8.0
   Compiling fs2 v0.4.3
   Compiling http-body v1.0.1
   Compiling time-macros v0.2.27
   Compiling sharded-slab v0.1.7
   Compiling thread_local v1.1.9
   Compiling deranged v0.5.8
   Compiling unicode-width v0.2.2
   Compiling unicode-casefold v0.2.0
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling ipnet v2.12.0
   Compiling webpki-roots v0.25.4
   Compiling hex v0.4.3
   Compiling http-body v0.4.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling ppv-lite86 v0.2.21
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
   Compiling sync_wrapper v0.1.2
   Compiling nu-ansi-term v0.50.3
   Compiling unicode-normalization v0.1.25
   Compiling semver v1.0.28
   Compiling matchit v0.7.3
   Compiling unindent v0.2.4
   Compiling rustls-pemfile v1.0.4
   Compiling indoc v2.0.7
   Compiling pem v3.0.6
   Compiling rand_core v0.6.4
   Compiling signal-hook-registry v1.4.8
   Compiling num-bigint v0.4.6
   Compiling parking_lot v0.12.5
   Compiling grep-searcher v0.1.17
   Compiling digest v0.10.7
   Compiling toml v0.9.12+spec-1.1.0
   Compiling time v0.3.47
   Compiling http-body-util v0.1.3
   Compiling pest v2.9.4
   Compiling rand_chacha v0.3.1
   Compiling tempfile v3.27.0
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling hashbrown v0.14.5
   Compiling rayon v1.12.0
   Compiling rand v0.8.6
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling phf_generator v0.11.3
   Compiling pest_meta v2.9.4
   Compiling phf_codegen v0.11.3
   Compiling hashlink v0.9.1
   Compiling globwalk v0.9.1
   Compiling chrono-tz-build v0.3.0
   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
   Compiling chrono-tz v0.9.0
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling arbitrary v1.5.0
   Compiling pest_derive v2.9.4
   Compiling clap v4.6.7
   Compiling synstructure v0.13.2
   Compiling serde_derive v1.0.228
   Compiling tokio-macros v2.7.0
   Compiling tracing-attributes v0.1.31
   Compiling zerovec-derive v0.11.3
   Compiling displaydoc v0.2.5
   Compiling futures-macro v0.3.32
   Compiling thiserror-impl v1.0.69
   Compiling thiserror-impl v2.0.18
   Compiling async-trait v0.1.89
   Compiling async-stream-impl v0.3.6
   Compiling clap-cargo v0.18.3
   Compiling async-stream v0.3.6
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling table_formatter v0.6.1
   Compiling simple_asn1 v0.6.4
   Compiling zerofrom v0.1.7
   Compiling tower-http v0.5.2
   Compiling matchers v0.2.0
   Compiling yoke v0.8.2
   Compiling tracing-subscriber v0.3.23
   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling serde_urlencoded v0.7.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
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
   Compiling idna_adapter v1.2.2
   Compiling h2 v0.3.27
   Compiling idna v1.1.0
   Compiling hyper-util v0.1.20
   Compiling axum v0.7.9
   Compiling url v2.5.8
   Compiling hyper v0.14.32
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_gateway v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 16m 20s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-9mvy69gr/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/e4876acfba7a09db90d21b66a70553aa50939be750747d68fc7e9edd10da3b0f/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 3ms
Prepared 1 package in 158ms
Uninstalled 1 package in 2ms
Installed 1 package in 1ms
 - sase-core-rs==0.44.2 (from file:///home/bryan/.sase/cache/sase-core-artifacts/1472aa180482a2e1695f108434e00e787e3c579ed33c69253fbd128c60334212/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.44.2 (from file:///home/bryan/.sase/cache/sase-core-artifacts/e4876acfba7a09db90d21b66a70553aa50939be750747d68fc7e9edd10da3b0f/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: no exact cached wheel
   Compiling libc v0.2.186
   Compiling proc-macro2 v1.0.106
   Compiling unicode-ident v1.0.24
   Compiling quote v1.0.45
   Compiling zerocopy v0.8.48
   Compiling memchr v2.8.0
   Compiling cfg-if v1.0.4
   Compiling crossbeam-utils v0.8.21
   Compiling serde_core v1.0.228
   Compiling shlex v1.3.0
   Compiling find-msvc-tools v0.1.9
   Compiling regex-syntax v0.8.10
   Compiling siphasher v1.0.4
   Compiling version_check v0.9.5
   Compiling serde v1.0.228
   Compiling autocfg v1.5.0
   Compiling crossbeam-epoch v0.9.21
   Compiling zmij v1.0.21
   Compiling once_cell v1.21.4
   Compiling crossbeam-deque v0.8.8
   Compiling serde_json v1.0.149
   Compiling log v0.4.29
   Compiling hashbrown v0.17.0
   Compiling ucd-trie v0.1.7
   Compiling pin-project-lite v0.2.17
   Compiling iana-time-zone v0.1.65
   Compiling equivalent v1.0.2
   Compiling smallvec v1.15.1
   Compiling bitflags v2.11.1
   Compiling itoa v1.0.18
   Compiling same-file v1.0.6
   Compiling futures-sink v0.3.32
   Compiling futures-core v0.3.32
   Compiling libm v0.2.16
   Compiling typenum v1.20.0
   Compiling parking_lot_core v0.9.12
   Compiling lazy_static v1.5.0
   Compiling slab v0.4.12
   Compiling futures-task v0.3.32
   Compiling deunicode v1.6.2
   Compiling bytes v1.11.1
   Compiling scopeguard v1.2.0
   Compiling futures-io v0.3.32
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling clap_lex v1.1.1
   Compiling pkg-config v0.3.33
   Compiling percent-encoding v2.3.2
   Compiling vcpkg v0.2.15
   Compiling thiserror v1.0.69
   Compiling heck v0.5.0
   Compiling unicode-segmentation v1.13.3
   Compiling anstyle v1.0.14
   Compiling winnow v1.0.4
   Compiling rustix v1.1.4
   Compiling sync_wrapper v1.0.2
   Compiling tower-layer v0.3.3
   Compiling encoding_rs v0.8.35
   Compiling getrandom v0.4.2
   Compiling tower-service v0.3.3
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling linux-raw-sys v0.12.1
   Compiling home v0.5.12
   Compiling bitflags v1.3.2
   Compiling cpufeatures v0.2.17
   Compiling phf_shared v0.11.3
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling num-traits v0.2.19
   Compiling winnow v0.7.15
   Compiling httparse v1.10.1
   Compiling ryu v1.0.23
   Compiling fallible-streaming-iterator v0.1.9
   Compiling unsafe-libyaml v0.2.11
   Compiling fastrand v2.4.1
   Compiling tinyvec v1.13.3
   Compiling tracing-core v0.1.36
   Compiling fallible-iterator v0.3.0
   Compiling thread_local v1.1.9
   Compiling lock_api v0.4.14
   Compiling walkdir v2.5.0
   Compiling indexmap v2.14.0
   Compiling clap_builder v4.6.7
   Compiling colored v2.2.0
   Compiling itertools v0.11.0
   Compiling grep-matcher v0.1.9
   Compiling sharded-slab v0.1.7
   Compiling hex v0.4.3
   Compiling semver v1.0.28
   Compiling unicode-casefold v0.2.0
   Compiling slug v0.1.6
   Compiling crossbeam-channel v0.5.17
   Compiling nu-ansi-term v0.50.3
   Compiling cc v1.2.61
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling unicode-width v0.2.2
   Compiling futures-channel v0.3.32
   Compiling humansize v2.1.3
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling getrandom v0.2.17
   Compiling memmap2 v0.9.11
   Compiling term_size v0.3.2
   Compiling fs2 v0.4.3
   Compiling ppv-lite86 v0.2.21
   Compiling encoding_rs_io v0.1.8
   Compiling phf v0.11.3
   Compiling fluent-uri v0.1.4
   Compiling etcetera v0.8.0
   Compiling tracing-log v0.2.0
   Compiling unicode-normalization v0.1.25
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling serde_spanned v1.1.2
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling libsqlite3-sys v0.30.1
   Compiling regex-automata v0.4.14
   Compiling signal-hook-registry v1.4.8
   Compiling rand_core v0.6.4
   Compiling parking_lot v0.12.5
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling hashbrown v0.14.5
   Compiling grep-searcher v0.1.17
   Compiling chrono v0.4.44
   Compiling toml v0.9.12+spec-1.1.0
   Compiling tempfile v3.27.0
   Compiling digest v0.10.7
   Compiling rand_chacha v0.3.1
   Compiling hashlink v0.9.1
   Compiling pest v2.9.4
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling rand v0.8.6
   Compiling rayon v1.12.0
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling phf_generator v0.11.3
   Compiling pest_meta v2.9.4
   Compiling matchers v0.2.0
   Compiling ignore v0.4.32
   Compiling parse-zoneinfo v0.3.1
   Compiling phf_codegen v0.11.3
   Compiling chrono-tz-build v0.3.0
   Compiling globwalk v0.9.1
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling arbitrary v1.5.0
   Compiling chrono-tz v0.9.0
   Compiling serde_derive v1.0.228
   Compiling tracing-attributes v0.1.31
   Compiling futures-macro v0.3.32
   Compiling tokio-macros v2.7.0
   Compiling thiserror-impl v1.0.69
   Compiling serde_repr v0.1.20
   Compiling clap v4.6.7
   Compiling pest_derive v2.9.4
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling clap-cargo v0.18.3
   Compiling table_formatter v0.6.1
   Compiling tracing-subscriber v0.3.23
   Compiling json5 v0.4.1
   Compiling dashmap v6.1.0
   Compiling lsp-types v0.97.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling futures v0.3.32
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling tokei v15.0.0
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_macro_lsp v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Finished `dev-update` profile [optimized] target(s) in 3m 44s
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/8f8aacc5ec515a7efc481b146adfd22faac03a14443cd938965fddd6dee3ed33/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.venv/bin/sase-macro-lsp
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
Local commands in /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/sase.yml were skipped (no-acknowledgment); run `sase config trust allow /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/sase.yml` after review.
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.44.2 is missing 8 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] decide_local_command_trust: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] digest_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] filter_trusted_local_layer: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] local_command_trust_store_allow: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); no release tag contains it yet.
[core-floor-probe] local_command_trust_store_get: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); no release tag contains it yet.
[core-floor-probe] local_command_trust_store_revoke: first appears in sase-core 233cb41 (feat(config): persist digest-pinned local command trust); no release tag contains it yet.
[core-floor-probe] local_command_trust_wire_schema_version: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] project_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "e7647bf", "name": "decide_local_command_trust", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "digest_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "filter_trusted_local_layer", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "233cb41", "name": "local_command_trust_store_allow", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_get", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_revoke", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "e7647bf", "name": "local_command_trust_wire_schema_version", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "project_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}], "declared_floor": "0.44.2", "exit_code": 4, "message": "sase-core-rs==0.44.2 is missing 8 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✓ test (scoped)
scoped: escalated to the full suite (rules: contract-set-only, core-identity-changed); contexts baseline not consulted
succeeded  2664886ms
sase tool show 1b260240f986521dbf1d2d9caf7fe43c -l

