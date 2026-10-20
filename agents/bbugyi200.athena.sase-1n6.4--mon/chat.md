# Chat History - ace-run (sase-1n6.4--mon)

- **TIMESTAMP:** 2026-10-19 19:21:23 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1n6.4--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'finish check (joined run)'

## Response

sase tool run f09a9076a23e954eef98aee5225a9e47
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core to origin/master
[validate_sase_core_rs] installed sase-core-rs distribution version 0.41.0 is behind sase's sase-core-rs>=0.42.0,<0.43.0 floor in /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/pyproject.toml. Rebuild the extension: run `just install-venv`.
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
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/bin/python
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
   Compiling log v0.4.29
   Compiling serde v1.0.228
   Compiling siphasher v1.0.4
   Compiling version_check v0.9.5
   Compiling zmij v1.0.21
   Compiling futures-core v0.3.32
   Compiling smallvec v1.15.1
   Compiling crossbeam-epoch v0.9.21
   Compiling serde_json v1.0.149
   Compiling stable_deref_trait v1.2.1
   Compiling crossbeam-deque v0.8.8
   Compiling futures-sink v0.3.32
   Compiling target-lexicon v0.12.16
   Compiling hashbrown v0.17.0
   Compiling equivalent v1.0.2
   Compiling tower-service v0.3.3
   Compiling iana-time-zone v0.1.65
   Compiling slab v0.4.12
   Compiling futures-io v0.3.32
   Compiling ucd-trie v0.1.7
   Compiling futures-task v0.3.32
   Compiling bitflags v2.11.1
   Compiling heck v0.5.0
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling untrusted v0.9.0
   Compiling libm v0.2.16
   Compiling litemap v0.8.2
   Compiling same-file v1.0.6
   Compiling icu_normalizer_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling typenum v1.20.0
   Compiling lazy_static v1.5.0
   Compiling fnv v1.0.7
   Compiling tower-layer v0.3.3
   Compiling deunicode v1.6.2
   Compiling parking_lot_core v0.9.12
   Compiling httpdate v1.0.3
   Compiling cc v1.2.61
   Compiling unicode-segmentation v1.13.3
   Compiling vcpkg v0.2.15
   Compiling num-traits v0.2.19
   Compiling rayon-core v1.13.0
   Compiling aho-corasick v1.1.4
   Compiling generic-array v0.14.7
   Compiling tracing-core v0.1.36
   Compiling ahash v0.8.12
   Compiling bstr v1.13.1
   Compiling either v1.19.0
   Compiling rustls v0.21.12
   Compiling thiserror v1.0.69
   Compiling phf_shared v0.11.3
   Compiling http v1.4.0
   Compiling sync_wrapper v1.0.2
   Compiling anstyle v1.0.14
   Compiling encoding_rs v0.8.35
   Compiling percent-encoding v2.3.2
   Compiling scopeguard v1.2.0
   Compiling ryu v1.0.23
   Compiling pkg-config v0.3.33
   Compiling walkdir v2.5.0
   Compiling clap_lex v1.1.1
   Compiling winnow v1.0.4
   Compiling rustversion v1.0.22
   Compiling getrandom v0.4.2
   Compiling http v0.2.12
   Compiling slug v0.1.6
   Compiling num-conv v0.2.1
   Compiling try-lock v0.2.5
   Compiling rustix v1.1.4
   Compiling powerfmt v0.2.0
   Compiling time-core v0.1.8
   Compiling thiserror v2.0.18
   Compiling grep-matcher v0.1.9
   Compiling colored v2.2.0
   Compiling cpufeatures v0.2.17
   Compiling mime v0.3.17
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling indexmap v2.14.0
   Compiling futures-channel v0.3.32
   Compiling home v0.5.12
   Compiling atomic-waker v1.1.2
   Compiling serde_spanned v1.1.2
   Compiling ppv-lite86 v0.2.21
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling winnow v0.7.15
   Compiling want v0.3.1
   Compiling linux-raw-sys v0.12.1
   Compiling crossbeam-channel v0.5.17
   Compiling pyo3-build-config v0.22.6
   Compiling phf v0.11.3
   Compiling itertools v0.11.0
   Compiling memoffset v0.9.1
   Compiling tinyvec v1.13.3
   Compiling unsafe-libyaml v0.2.11
   Compiling base64 v0.22.1
   Compiling fastrand v2.4.1
   Compiling humansize v2.1.3
   Compiling fallible-streaming-iterator v0.1.9
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling regex-automata v0.4.14
   Compiling http-body v1.0.1
   Compiling lock_api v0.4.14
   Compiling libsqlite3-sys v0.30.1
   Compiling clap_builder v4.6.7
   Compiling errno v0.3.14
   Compiling mio v1.2.0
   Compiling getrandom v0.2.17
   Compiling socket2 v0.6.3
   Compiling form_urlencoded v1.2.2
   Compiling deranged v0.5.8
   Compiling http-body v0.4.6
   Compiling encoding_rs_io v0.1.8
   Compiling memmap2 v0.9.11
   Compiling socket2 v0.5.10
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling etcetera v0.8.0
   Compiling term_size v0.3.2
   Compiling time-macros v0.2.27
   Compiling base64 v0.21.7
   Compiling fallible-iterator v0.3.0
   Compiling fs2 v0.4.3
   Compiling tracing-log v0.2.0
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling serde_path_to_error v0.1.20
   Compiling thread_local v1.1.9
   Compiling sharded-slab v0.1.7
   Compiling unicode-width v0.2.2
   Compiling hex v0.4.3
   Compiling chrono v0.4.44
   Compiling num-integer v0.1.46
   Compiling unicode-casefold v0.2.0
   Compiling webpki-roots v0.25.4
   Compiling ipnet v2.12.0
   Compiling nu-ansi-term v0.50.3
   Compiling hashbrown v0.14.5
   Compiling unicode-normalization v0.1.25
   Compiling sync_wrapper v0.1.2
   Compiling matchit v0.7.3
   Compiling http-body-util v0.1.3
   Compiling indoc v2.0.7
   Compiling unindent v0.2.4
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling rand_core v0.6.4
   Compiling pyo3 v0.22.6
   Compiling pem v3.0.6
   Compiling parking_lot v0.12.5
   Compiling signal-hook-registry v1.4.8
   Compiling time v0.3.47
   Compiling grep-searcher v0.1.17
   Compiling toml v0.9.12+spec-1.1.0
   Compiling rustls-pemfile v1.0.4
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling matchers v0.2.0
   Compiling digest v0.10.7
   Compiling num-bigint v0.4.6
   Compiling hashlink v0.9.1
   Compiling tempfile v3.27.0
   Compiling rand_chacha v0.3.1
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling pest v2.9.4
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling rand v0.8.6
   Compiling rayon v1.12.0
   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling pest_meta v2.9.4
   Compiling globwalk v0.9.1
   Compiling phf_generator v0.11.3
   Compiling rusqlite v0.32.1
   Compiling phf_codegen v0.11.3
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling arbitrary v1.5.0
   Compiling chrono-tz-build v0.3.0
   Compiling clap v4.6.7
   Compiling pest_derive v2.9.4
   Compiling synstructure v0.13.2
   Compiling chrono-tz v0.9.0
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
   Compiling simple_asn1 v0.6.4
   Compiling table_formatter v0.6.1
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling zerofrom v0.1.7
   Compiling tracing-subscriber v0.3.23
   Compiling tower-http v0.5.2
   Compiling pyo3-macros v0.22.6
   Compiling json5 v0.4.1
   Compiling serde_urlencoded v0.7.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling yoke v0.8.2
   Compiling axum-core v0.4.5
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling hyper v1.9.0
   Compiling tokio-rustls v0.24.1
   Compiling tokei v15.0.0
   Compiling h2 v0.3.27
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling hyper-util v0.1.20
   Compiling icu_collections v2.2.0
   Compiling icu_locale_core v2.2.0
   Compiling axum v0.7.9
   Compiling icu_provider v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling icu_properties v2.2.0
   Compiling hyper v0.14.32
   Compiling sase_core v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_core)
   Compiling idna_adapter v1.2.2
   Compiling idna v1.1.0
   Compiling url v2.5.8
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling sase_gateway v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 14m 34s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-s2roo9wl/sase_core_rs-0.42.1-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/7f0ef1311bf0fa0a6f9188f9dc0d1e1177ba409a002b9cb4e04b6cd9ef9a1295/sase_core_rs-0.42.1-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 2ms
Prepared 1 package in 155ms
Uninstalled 1 package in 2ms
Installed 1 package in 2ms
 - sase-core-rs==0.41.0 (from file:///home/bryan/.sase/cache/sase-core-artifacts/261feb2ac4111ce1dc208ed757ac00a8ace8dfc61708f71e61569d2e086ed699/sase_core_rs-0.41.0-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.42.1 (from file:///home/bryan/.sase/cache/sase-core-artifacts/7f0ef1311bf0fa0a6f9188f9dc0d1e1177ba409a002b9cb4e04b6cd9ef9a1295/sase_core_rs-0.42.1-cp312-abi3-manylinux_2_39_x86_64.whl)
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
   Compiling serde_core v1.0.228
   Compiling crossbeam-utils v0.8.21
   Compiling find-msvc-tools v0.1.9
   Compiling shlex v1.3.0
   Compiling regex-syntax v0.8.10
   Compiling version_check v0.9.5
   Compiling siphasher v1.0.4
   Compiling serde v1.0.228
   Compiling autocfg v1.5.0
   Compiling zmij v1.0.21
   Compiling crossbeam-epoch v0.9.21
   Compiling once_cell v1.21.4
   Compiling serde_json v1.0.149
   Compiling crossbeam-deque v0.8.8
   Compiling log v0.4.29
   Compiling ucd-trie v0.1.7
   Compiling hashbrown v0.17.0
   Compiling pin-project-lite v0.2.17
   Compiling equivalent v1.0.2
   Compiling iana-time-zone v0.1.65
   Compiling smallvec v1.15.1
   Compiling bitflags v2.11.1
   Compiling itoa v1.0.18
   Compiling futures-sink v0.3.32
   Compiling same-file v1.0.6
   Compiling futures-core v0.3.32
   Compiling libm v0.2.16
   Compiling typenum v1.20.0
   Compiling parking_lot_core v0.9.12
   Compiling scopeguard v1.2.0
   Compiling futures-task v0.3.32
   Compiling deunicode v1.6.2
   Compiling slab v0.4.12
   Compiling bytes v1.11.1
   Compiling futures-io v0.3.32
   Compiling lazy_static v1.5.0
   Compiling thiserror v1.0.69
   Compiling heck v0.5.0
   Compiling pkg-config v0.3.33
   Compiling anstyle v1.0.14
   Compiling vcpkg v0.2.15
   Compiling percent-encoding v2.3.2
   Compiling unicode-segmentation v1.13.3
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling clap_lex v1.1.1
   Compiling sync_wrapper v1.0.2
   Compiling getrandom v0.4.2
   Compiling encoding_rs v0.8.35
   Compiling tower-layer v0.3.3
   Compiling aho-corasick v1.1.4
   Compiling phf_shared v0.11.3
   Compiling num-traits v0.2.19
   Compiling bstr v1.13.1
   Compiling cc v1.2.61
   Compiling rustix v1.1.4
   Compiling tower-service v0.3.3
   Compiling winnow v1.0.4
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling tracing-core v0.1.36
   Compiling slug v0.1.6
   Compiling grep-matcher v0.1.9
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling bitflags v1.3.2
   Compiling winnow v0.7.15
   Compiling httparse v1.10.1
   Compiling linux-raw-sys v0.12.1
   Compiling home v0.5.12
   Compiling cpufeatures v0.2.17
   Compiling fastrand v2.4.1
   Compiling fallible-streaming-iterator v0.1.9
   Compiling fallible-iterator v0.3.0
   Compiling colored v2.2.0
   Compiling tinyvec v1.13.3
   Compiling ryu v1.0.23
   Compiling unsafe-libyaml v0.2.11
   Compiling indexmap v2.14.0
   Compiling sharded-slab v0.1.7
   Compiling thread_local v1.1.9
   Compiling unicode-casefold v0.2.0
   Compiling lock_api v0.4.14
   Compiling nu-ansi-term v0.50.3
   Compiling clap_builder v4.6.7
   Compiling unicode-width v0.2.2
   Compiling hex v0.4.3
   Compiling itertools v0.11.0
   Compiling walkdir v2.5.0
   Compiling futures-channel v0.3.32
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling serde_spanned v1.1.2
   Compiling crossbeam-channel v0.5.17
   Compiling humansize v2.1.3
   Compiling encoding_rs_io v0.1.8
   Compiling phf v0.11.3
   Compiling regex-automata v0.4.14
   Compiling tracing-log v0.2.0
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling libsqlite3-sys v0.30.1
   Compiling fluent-uri v0.1.4
   Compiling etcetera v0.8.0
   Compiling ppv-lite86 v0.2.21
   Compiling getrandom v0.2.17
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling memmap2 v0.9.11
   Compiling term_size v0.3.2
   Compiling fs2 v0.4.3
   Compiling unicode-normalization v0.1.25
   Compiling chrono v0.4.44
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling hashbrown v0.14.5
   Compiling globset v0.4.19
   Compiling regex v1.12.3
   Compiling matchers v0.2.0
   Compiling rand_core v0.6.4
   Compiling grep-searcher v0.1.17
   Compiling signal-hook-registry v1.4.8
   Compiling toml v0.9.12+spec-1.1.0
   Compiling parking_lot v0.12.5
   Compiling digest v0.10.7
   Compiling tempfile v3.27.0
   Compiling ignore v0.4.32
   Compiling rand_chacha v0.3.1
   Compiling hashlink v0.9.1
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling pest v2.9.4
   Compiling parse-zoneinfo v0.3.1
   Compiling rand v0.8.6
   Compiling rayon v1.12.0
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling globwalk v0.9.1
   Compiling phf_generator v0.11.3
   Compiling pest_meta v2.9.4
   Compiling phf_codegen v0.11.3
   Compiling chrono-tz-build v0.3.0
   Compiling chrono-tz v0.9.0
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling arbitrary v1.5.0
   Compiling clap v4.6.7
   Compiling serde_derive v1.0.228
   Compiling tracing-attributes v0.1.31
   Compiling tokio-macros v2.7.0
   Compiling futures-macro v0.3.32
   Compiling thiserror-impl v1.0.69
   Compiling serde_repr v0.1.20
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling pest_derive v2.9.4
   Compiling clap-cargo v0.18.3
   Compiling table_formatter v0.6.1
   Compiling tracing-subscriber v0.3.23
   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling lsp-types v0.97.0
   Compiling futures v0.3.32
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling tokei v15.0.0
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_macro_lsp v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Finished `dev-update` profile [optimized] target(s) in 3m 28s
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/33ed9afaa872a4709134bdaf82e8637dbd608276fe9f9fbde2a221588d3c565e/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/bin/sase-macro-lsp
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
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
test selection escalated to the full suite (rules: selection-tooling); 5301 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: selection-tooling)
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 292s, heartbeat 2s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 131s, heartbeat 5s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 111s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 322s, heartbeat 2s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 161s, heartbeat 5s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 141s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 352s, heartbeat 2s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 192s, heartbeat 5s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 171s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 382s, heartbeat 2s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 222s, heartbeat 5s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 201s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 412s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 252s, heartbeat 5s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 231s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 442s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 282s, heartbeat 5s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 261s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 472s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 312s, heartbeat 5s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 291s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 502s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 342s, heartbeat 5s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 321s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 532s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 372s, heartbeat 4s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 351s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 562s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 402s, heartbeat 4s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 381s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 592s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 432s, heartbeat 4s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 411s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 623s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 462s, heartbeat 4s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 442s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 653s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 492s, heartbeat 4s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 472s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 683s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 522s, heartbeat 4s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 502s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 713s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 552s, heartbeat 4s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 532s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 743s, heartbeat 1s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 582s, heartbeat 3s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 562s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 773s, heartbeat 0s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 612s, heartbeat 3s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 592s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 803s, heartbeat 5s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 642s, heartbeat 3s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 622s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 833s, heartbeat 4s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 672s, heartbeat 3s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 652s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 3619695, grant 14, age 863s, heartbeat 7s, argv 'tools/run_pytest scoped'; 14 tokens: pid 3713020, grant 14, age 703s, heartbeat 3s, argv 'tools/run_pytest scoped'; 4 tokens: pid 3725225, grant 4, age 682s, heartbeat 5s, argv 'tools/run_pytest scoped'
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, hypothesis-6.167.1, platformdirs-4.13.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [56743 items]

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
....................s................................................... [  1%]
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
.......s................................................................ [ 13%]
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
.................................................s...................... [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
..........................................................s............. [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
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
......................................................s................. [ 56%]
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
.............s...........................................ss............. [ 60%]
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
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
............................................................s........... [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
......................................................................s. [ 65%]
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
......................................................................ss [ 67%]
ss...................................................................... [ 67%]
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
..................................................s..................... [ 72%]
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
..............................................................F......... [ 74%]
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
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
.......................................s................................ [ 79%]
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
...................................FF................................... [ 81%]
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
........................................................................ [ 99%]
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
________ test_contract_set_manifest_entry_budget_has_no_hidden_headroom ________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/bin/python

    def test_contract_set_manifest_entry_budget_has_no_hidden_headroom() -> None:
        files = _read_manifest()
    
>       assert len(files) == _MANIFEST_ENTRY_BUDGET, _budget_failure_message(files)
E       AssertionError: tests/contract_manifest.txt contains 80 entries, over the 79-entry contract-set budget.
E         The current set was measured at 130.81 serial seconds across 79 entries.
E         Re-curate by value per second, then update this cap and measured-cost comment per plans/202608/test_suite_tier1.md.
E         entries over budget: ['tests/test_validate_test_environment_tool.py']
E       assert 80 == 79
E        +  where 80 = len(['tests/ace/tui/test_visual_fixture_host_paths.py', 'tests/test_agent_session_terminology.py', 'tests/test_agent_stop_...ibe_terminology.py', 'tests/test_check_sase_core_rs_bindings_tool.py', 'tests/test_ci_bootstrap_sidecars_tool.py', ...])

tests/test_contract_manifest.py:385: AssertionError
___________________________ test_project_help_golden ___________________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/bin/python

capsys = <_pytest.capture.CaptureFixture object at 0x7f7d155611d0>
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f7d31d9e7b0>

    def test_project_help_golden(
        capsys: pytest.CaptureFixture[str], monkeypatch: pytest.MonkeyPatch
    ) -> None:
        monkeypatch.setenv("COLUMNS", "80")
        help_text = parse_and_capture_help(["stats", "project", "-h"], capsys)
        path = GOLDEN / "project_help.txt"
        if _UPDATE:
            path.parent.mkdir(parents=True, exist_ok=True)
            path.write_text(help_text, encoding="utf-8")
            return
>       assert help_text == path.read_text(encoding="utf-8")
E       assert "usage: sase ...ts, plans}'\n" == "usage: sase ...ts, plans}'\n"
E         
E         Skipping 869 identical leading characters in diff, use -v to show
E           refs)
E         -   -f {json,markdown,rich}, --format {json,markdown,rich}
E         ?     ------ ---------------
E         +   -f, --format {json,markdown,rich}
E                                   Output format (default: rich)...
E         
E         ...Full output truncated (44 lines hidden), use '-vv' to show

tests/main/test_parser_stats.py:110: AssertionError
_____________ test_project_help_includes_definitions_and_examples ______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/bin/python

capsys = <_pytest.capture.CaptureFixture object at 0x7f7d155631d0>
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f7d2e56d9b0>

    def test_project_help_includes_definitions_and_examples(
        capsys: pytest.CaptureFixture[str], monkeypatch: pytest.MonkeyPatch
    ) -> None:
        monkeypatch.setenv("COLUMNS", "80")
        help_text = parse_and_capture_help(["stats", "project", "-h"], capsys)
    
        assert "definitions:" in help_text
        for entry in PROJECT_REPORT_LEGENDS:
            assert entry.term in help_text
            assert entry.meaning in help_text
        assert "sase stats project -p sase -r all" in help_text
        assert "-D, --include-disabled" in help_text
        assert "-F, --fetch" in help_text
>       assert "-f {json,markdown,rich}, --format {json,markdown,rich}" in help_text
E       assert '-f {json,markdown,rich}, --format {json,markdown,rich}' in "usage: sase stats project [-h] [-D] [-F] [-f {json,markdown,rich}]\n                          [-g {model,patch,projec...sase-stats.md\n  sase stats project -p sase -j | jq '.data.projects[0].models[] | {provider, model, commits, plans}'\n"

tests/main/test_parser_stats.py:126: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=4167476) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/macro/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_readiness_through_real_loader_with_in_process_grammar
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:233: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    args = (deepcopy(arg, memo) for arg in args)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/argparse.py:620: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def _metavar_formatter(self, action, default_metavar):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=4167481) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=4167417) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/agents/_archive_controller_build.py:343: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    dict(row) for row in payload.get("rows", ()) if isinstance(row, Mapping)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  <string>:2: RuntimeWarning: coroutine '_run_archive_request' was never awaited
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_parking.py::test_collapsed_ungrouped_panel_restores_collapsed_focus
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:2308: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    def cast(typ, val):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
64.78s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
53.68s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
45.27s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
45.23s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
32.84s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
27.48s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
27.44s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
25.86s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
19.09s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
18.41s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
18.12s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
15.36s call     tests/test_sdd_commit.py::test_commit_sdd_files_removes_persistent_index_lock_after_retry_exhausted
15.33s call     tests/test_bare_git_init.py::TestInitBareGitProject::test_git_runner_removes_persistent_index_lock_after_retries
15.10s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
15.08s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
14.85s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
14.67s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
14.21s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
12.91s call     tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly
12.68s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
=========================== short test summary info ============================
FAILED tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom
FAILED tests/main/test_parser_stats.py::test_project_help_golden - assert "us...
FAILED tests/main/test_parser_stats.py::test_project_help_includes_definitions_and_examples
==== 3 failed, 56724 passed, 17 skipped, 114 warnings in 2512.94s (0:41:52) ====
error: recipe `test-scoped` failed on line 591 with exit code 1
scoped: escalated to the full suite (rules: selection-tooling); contexts baseline not consulted
✗ 1 stage(s) failed; continued past them (first exit 1)
error: recipe `check` failed on line 859 with exit code 1
failed/1  4625389ms
triage test (scoped): 3 KNOWN
KNOWN test (scoped): FAILED tests/main/test_parser_stats.py::test_project_help_includes_definitions_and_examples — witness 07b9835b8dfab6b46be4b7d7306f250f; no owner
KNOWN test (scoped): FAILED tests/main/test_parser_stats.py::test_project_help_golden - assert "us... — witness 07b9835b8dfab6b46be4b7d7306f250f; no owner
KNOWN test (scoped): FAILED tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom — witness 07b9835b8dfab6b46be4b7d7306f250f; no owner
sase tool show f09a9076a23e954eef98aee5225a9e47 -l
verdict: undetermined — 3 KNOWN; exit 1

