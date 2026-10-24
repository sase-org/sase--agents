# Chat History - ace-run (13k--mon)

- **TIMESTAMP:** 2026-10-24 07:39:34 EDT
- **MODEL:** codex/gpt-6-luna
- **AGENT:** 13k--mon

## Prompt

sase monitor start --command 'just fix-tui-screenshots' --reason 'Refresh and inspect Artifacts pane visual snapshots'

## Response

sase tool run 775ee35b429d22fb2693e4646f62a1ca
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core to origin/master
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
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python
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
   Compiling zmij v1.0.21
   Compiling futures-core v0.3.32
   Compiling version_check v0.9.5
   Compiling smallvec v1.15.1
   Compiling crossbeam-epoch v0.9.21
   Compiling serde_json v1.0.149
   Compiling futures-sink v0.3.32
   Compiling target-lexicon v0.12.16
   Compiling stable_deref_trait v1.2.1
   Compiling crossbeam-deque v0.8.8
   Compiling equivalent v1.0.2
   Compiling hashbrown v0.17.0
   Compiling futures-task v0.3.32
   Compiling tower-service v0.3.3
   Compiling iana-time-zone v0.1.65
   Compiling slab v0.4.12
   Compiling futures-io v0.3.32
   Compiling ucd-trie v0.1.7
   Compiling bitflags v2.11.1
   Compiling untrusted v0.9.0
   Compiling libm v0.2.16
   Compiling litemap v0.8.2
   Compiling same-file v1.0.6
   Compiling heck v0.5.0
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling icu_normalizer_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling typenum v1.20.0
   Compiling httpdate v1.0.3
   Compiling lazy_static v1.5.0
   Compiling fnv v1.0.7
   Compiling tower-layer v0.3.3
   Compiling deunicode v1.6.2
   Compiling parking_lot_core v0.9.12
   Compiling encoding_rs v0.8.35
   Compiling percent-encoding v2.3.2
   Compiling ryu v1.0.23
   Compiling pkg-config v0.3.33
   Compiling cc v1.2.61
   Compiling tracing-core v0.1.36
   Compiling clap_lex v1.1.1
   Compiling unicode-segmentation v1.13.3
   Compiling vcpkg v0.2.15
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling rustls v0.21.12
   Compiling thiserror v1.0.69
   Compiling sync_wrapper v1.0.2
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling anstyle v1.0.14
   Compiling phf_shared v0.11.3
   Compiling num-traits v0.2.19
   Compiling slug v0.1.6
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling scopeguard v1.2.0
   Compiling http v1.4.0
   Compiling http v0.2.12
   Compiling powerfmt v0.2.0
   Compiling time-core v0.1.8
   Compiling thiserror v2.0.18
   Compiling winnow v1.0.4
   Compiling rustversion v1.0.22
   Compiling getrandom v0.4.2
   Compiling num-conv v0.2.1
   Compiling try-lock v0.2.5
   Compiling rustix v1.1.4
   Compiling indexmap v2.14.0
   Compiling walkdir v2.5.0
   Compiling futures-channel v0.3.32
   Compiling colored v2.2.0
   Compiling grep-matcher v0.1.9
   Compiling winnow v0.7.15
   Compiling linux-raw-sys v0.12.1
   Compiling cpufeatures v0.2.17
   Compiling mime v0.3.17
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling home v0.5.12
   Compiling atomic-waker v1.1.2
   Compiling pyo3-build-config v0.22.6
   Compiling errno v0.3.14
   Compiling mio v1.2.0
   Compiling psm v0.1.24
   Compiling getrandom v0.2.17
   Compiling socket2 v0.6.3
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling form_urlencoded v1.2.2
   Compiling clap_builder v4.6.7
   Compiling socket2 v0.5.10
   Compiling libsqlite3-sys v0.30.1
   Compiling lock_api v0.4.14
   Compiling memmap2 v0.9.11
   Compiling term_size v0.3.2
   Compiling crossbeam-channel v0.5.17
   Compiling memoffset v0.9.1
   Compiling itertools v0.11.0
   Compiling base64 v0.21.7
   Compiling phf v0.11.3
   Compiling humansize v2.1.3
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling regex-automata v0.4.14
   Compiling serde_spanned v1.1.2
   Compiling fallible-iterator v0.3.0
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling encoding_rs_io v0.1.8
   Compiling deranged v0.5.8
   Compiling tinyvec v1.13.3
   Compiling unsafe-libyaml v0.2.11
   Compiling http-body v1.0.1
   Compiling want v0.3.1
   Compiling base64 v0.22.1
   Compiling fastrand v2.4.1
   Compiling fallible-streaming-iterator v0.1.9
   Compiling serde_path_to_error v0.1.20
   Compiling http-body v0.4.6
   Compiling block-buffer v0.10.4
   Compiling ppv-lite86 v0.2.21
   Compiling crypto-common v0.1.7
   Compiling time-macros v0.2.27
   Compiling tracing-log v0.2.0
   Compiling fs2 v0.4.3
   Compiling sharded-slab v0.1.7
   Compiling etcetera v0.8.0
   Compiling signal-hook-registry v1.4.8
   Compiling thread_local v1.1.9
   Compiling rand_core v0.6.4
   Compiling nu-ansi-term v0.50.3
   Compiling matchit v0.7.3
   Compiling ipnet v2.12.0
   Compiling chrono v0.4.44
   Compiling unicode-width v0.2.2
   Compiling hex v0.4.3
   Compiling parking_lot v0.12.5
   Compiling sync_wrapper v0.1.2
   Compiling unicode-casefold v0.2.0
   Compiling webpki-roots v0.25.4
   Compiling unindent v0.2.4
   Compiling indoc v2.0.7
   Compiling num-integer v0.1.46
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
   Compiling rustls-pemfile v1.0.4
   Compiling grep-searcher v0.1.17
   Compiling toml v0.9.12+spec-1.1.0
   Compiling digest v0.10.7
   Compiling unicode-normalization v0.1.25
   Compiling hashbrown v0.14.5
   Compiling http-body-util v0.1.3
   Compiling rand_chacha v0.3.1
   Compiling pem v3.0.6
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling time v0.3.47
   Compiling tempfile v3.27.0
   Compiling pest v2.9.4
   Compiling num-bigint v0.4.6
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling rand v0.8.6
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling hashlink v0.9.1
   Compiling rayon v1.12.0
   Compiling pest_meta v2.9.4
   Compiling rustls-webpki v0.101.7
   Compiling sct v0.7.1
   Compiling phf_generator v0.11.3
   Compiling globwalk v0.9.1
   Compiling phf_codegen v0.11.3
   Compiling chrono-tz-build v0.3.0
   Compiling chrono-tz v0.9.0
   Compiling matchers v0.2.0
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
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
   Compiling arbitrary v1.5.0
   Compiling async-stream v0.3.6
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling clap v4.6.7
   Compiling pest_derive v2.9.4
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling simple_asn1 v0.6.4
   Compiling table_formatter v0.6.1
   Compiling clap-cargo v0.18.3
   Compiling tracing-subscriber v0.3.23
   Compiling tower-http v0.5.2
   Compiling zerofrom v0.1.7
   Compiling yoke v0.8.2
   Compiling pyo3-macros v0.22.6
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling serde_urlencoded v0.7.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_workspace_hack)
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
   Compiling idna v1.1.0
   Compiling hyper-util v0.1.20
   Compiling axum v0.7.9
   Compiling url v2.5.8
   Compiling hyper v0.14.32
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_gateway v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 14m 51s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-iiug5mys/sase_core_rs-0.42.3-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/edc6c80af1770e214ffd387069ca385454c6daa92de6b6da7c8a391097697bee/sase_core_rs-0.42.3-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 4ms
Prepared 1 package in 159ms
Uninstalled 1 package in 10ms
Installed 1 package in 9ms
 - sase-core-rs==0.42.3 (from file:///home/bryan/.sase/cache/sase-core-artifacts/6041a9ba51260aac62687980de4f9e140fdb94c40e5386ae0a9e8559779fdf13/sase_core_rs-0.42.3-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.42.3 (from file:///home/bryan/.sase/cache/sase-core-artifacts/edc6c80af1770e214ffd387069ca385454c6daa92de6b6da7c8a391097697bee/sase_core_rs-0.42.3-cp312-abi3-manylinux_2_39_x86_64.whl)
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
   Compiling crossbeam-epoch v0.9.21
   Compiling zmij v1.0.21
   Compiling once_cell v1.21.4
   Compiling crossbeam-deque v0.8.8
   Compiling serde_json v1.0.149
   Compiling log v0.4.29
   Compiling pin-project-lite v0.2.17
   Compiling iana-time-zone v0.1.65
   Compiling equivalent v1.0.2
   Compiling ucd-trie v0.1.7
   Compiling hashbrown v0.17.0
   Compiling bitflags v2.11.1
   Compiling smallvec v1.15.1
   Compiling itoa v1.0.18
   Compiling libm v0.2.16
   Compiling futures-sink v0.3.32
   Compiling same-file v1.0.6
   Compiling futures-core v0.3.32
   Compiling typenum v1.20.0
   Compiling parking_lot_core v0.9.12
   Compiling deunicode v1.6.2
   Compiling bytes v1.11.1
   Compiling futures-io v0.3.32
   Compiling lazy_static v1.5.0
   Compiling slab v0.4.12
   Compiling scopeguard v1.2.0
   Compiling futures-task v0.3.32
   Compiling pkg-config v0.3.33
   Compiling anstyle v1.0.14
   Compiling percent-encoding v2.3.2
   Compiling vcpkg v0.2.15
   Compiling unicode-segmentation v1.13.3
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling clap_lex v1.1.1
   Compiling thiserror v1.0.69
   Compiling heck v0.5.0
   Compiling getrandom v0.4.2
   Compiling tower-layer v0.3.3
   Compiling rustix v1.1.4
   Compiling tower-service v0.3.3
   Compiling winnow v1.0.4
   Compiling encoding_rs v0.8.35
   Compiling phf_shared v0.11.3
   Compiling sync_wrapper v1.0.2
   Compiling winnow v0.7.15
   Compiling aho-corasick v1.1.4
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling bstr v1.13.1
   Compiling tracing-core v0.1.36
   Compiling num-traits v0.2.19
   Compiling grep-matcher v0.1.9
   Compiling httparse v1.10.1
   Compiling linux-raw-sys v0.12.1
   Compiling home v0.5.12
   Compiling slug v0.1.6
   Compiling cpufeatures v0.2.17
   Compiling bitflags v1.3.2
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling fallible-iterator v0.3.0
   Compiling tinyvec v1.13.3
   Compiling ryu v1.0.23
   Compiling unsafe-libyaml v0.2.11
   Compiling fastrand v2.4.1
   Compiling fallible-streaming-iterator v0.1.9
   Compiling itertools v0.11.0
   Compiling indexmap v2.14.0
   Compiling futures-channel v0.3.32
   Compiling thread_local v1.1.9
   Compiling nu-ansi-term v0.50.3
   Compiling unicode-width v0.2.2
   Compiling cc v1.2.61
   Compiling hex v0.4.3
   Compiling walkdir v2.5.0
   Compiling unicode-casefold v0.2.0
   Compiling colored v2.2.0
   Compiling sharded-slab v0.1.7
   Compiling lock_api v0.4.14
   Compiling clap_builder v4.6.7
   Compiling crossbeam-channel v0.5.17
   Compiling humansize v2.1.3
   Compiling getrandom v0.2.17
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling serde_spanned v1.1.2
   Compiling phf v0.11.3
   Compiling encoding_rs_io v0.1.8
   Compiling regex-automata v0.4.14
   Compiling ppv-lite86 v0.2.21
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling tracing-log v0.2.0
   Compiling fluent-uri v0.1.4
   Compiling etcetera v0.8.0
   Compiling chrono v0.4.44
   Compiling unicode-normalization v0.1.25
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling memmap2 v0.9.11
   Compiling term_size v0.3.2
   Compiling fs2 v0.4.3
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling libsqlite3-sys v0.30.1
   Compiling rand_core v0.6.4
   Compiling toml v0.9.12+spec-1.1.0
   Compiling hashbrown v0.14.5
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling parking_lot v0.12.5
   Compiling signal-hook-registry v1.4.8
   Compiling grep-searcher v0.1.17
   Compiling rand_chacha v0.3.1
   Compiling tempfile v3.27.0
   Compiling hashlink v0.9.1
   Compiling digest v0.10.7
   Compiling rand v0.8.6
   Compiling pest v2.9.4
   Compiling rayon v1.12.0
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling globset v0.4.19
   Compiling regex v1.12.3
   Compiling matchers v0.2.0
   Compiling phf_generator v0.11.3
   Compiling ignore v0.4.32
   Compiling parse-zoneinfo v0.3.1
   Compiling phf_codegen v0.11.3
   Compiling pest_meta v2.9.4
   Compiling globwalk v0.9.1
   Compiling chrono-tz-build v0.3.0
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling chrono-tz v0.9.0
   Compiling arbitrary v1.5.0
   Compiling serde_derive v1.0.228
   Compiling tokio-macros v2.7.0
   Compiling futures-macro v0.3.32
   Compiling tracing-attributes v0.1.31
   Compiling thiserror-impl v1.0.69
   Compiling serde_repr v0.1.20
   Compiling clap v4.6.7
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling pest_derive v2.9.4
   Compiling clap-cargo v0.18.3
   Compiling table_formatter v0.6.1
   Compiling tracing-subscriber v0.3.23
   Compiling json5 v0.4.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling lsp-types v0.97.0
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling futures v0.3.32
   Compiling tower v0.5.3
   Compiling tokio-util v0.7.18
   Compiling tokei v15.0.0
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_macro_lsp v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Finished `dev-update` profile [optimized] target(s) in 3m 59s
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/5eed894f9311d0030b6c2b624a3affb77a34be3caa97338c3441ea9009acb78f/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/sase-macro-lsp
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, platformdirs-4.12.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [1388 items]

........................................................................ [  5%]
........................................................................ [ 10%]
........................................................................ [ 15%]
........................................................................ [ 20%]
........................................................................ [ 25%]
........................................................................ [ 31%]
........................................................................ [ 36%]
........................................................................ [ 41%]
........................................................................ [ 46%]
........................................................................ [ 51%]
........................................................................ [ 57%]
........................................................................ [ 62%]
........................................................................ [ 67%]
........................................................................ [ 72%]
........................................................................ [ 77%]
........................................................................ [ 82%]
........................................................................ [ 88%]
........................................................................ [ 93%]
........................................................................ [ 98%]
....................                                                     [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
32.43s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
23.15s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_header.py::test_tool_runs_header_chips_png_snapshots
21.90s call     tests/ace/tui/visual/test_ace_png_snapshots_tool_runs_cards.py::test_tool_runs_card_png_snapshots
17.66s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_macro.py::test_mini_macro_pane_dirty_png_snapshot
16.41s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
15.93s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_readonly_png_snapshot
15.88s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_jinja_invalid_png_snapshot
15.83s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
15.78s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_layered_wave_dividers_png_snapshot[80]
15.69s call     tests/ace/tui/visual/test_ace_png_snapshots_jinja_completion.py::test_jinja_filter_completion_png_snapshot
15.35s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
15.28s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_clan_waves_ladder_png_snapshots
14.97s call     tests/ace/tui/visual/test_ace_png_snapshots_vcs_ref_completion.py::test_vcs_ref_completion_panel_png_snapshot
14.88s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_macro.py::test_mini_macro_pane_stale_png_snapshot
14.86s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_vim_cursor_insert_png_snapshot
14.67s call     tests/ace/tui/visual/test_ace_png_snapshots_vcs_repo_completion.py::test_vcs_repo_loading_panel_png_snapshot
14.57s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
14.51s call     tests/ace/tui/visual/test_ace_png_snapshots_macro_arg_completion.py::test_macro_arg_model_value_completion_png_snapshot[light]
14.26s call     tests/ace/tui/visual/test_ace_png_snapshots_next_word.py::test_next_word_menu_narrow_png_snapshot
14.26s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_empty_png_snapshot
=========== 1388 passed, 1 skipped, 56 warnings in 449.58s (0:07:29) ===========
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16
configfile: pyproject.toml
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, platformdirs-4.12.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [387 items]

........................................................................ [ 18%]
........................................................................ [ 37%]
........................................................................ [ 55%]
........................................................................ [ 74%]
........................................................................ [ 93%]
...........................                                              [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
16.27s call     tests/ace/tui/visual/test_ace_png_snapshots_macro_arg_completion.py::test_macro_arg_enum_value_completion_png_snapshot[light]
15.40s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_macro.py::test_mini_macro_pane_dirty_png_snapshot
14.86s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_macro.py::test_mini_macro_scoped_frontmatter_png_snapshot
14.08s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting_refs.py::test_prompt_macro_highlight_solo_light_png_snapshot
14.03s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_macro.py::test_mini_macro_pane_stale_png_snapshot
13.58s call     tests/ace/tui/visual/test_ace_png_snapshots_model_alias_completion.py::test_model_alias_completion_filtered_preview_png_snapshot
13.55s call     tests/ace/tui/visual/test_ace_png_snapshots_macro_arg_completion.py::test_typed_form_enum_choice_picker_png_snapshot[light]
13.28s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_completion_panel_png_snapshot
13.21s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting_search.py::test_prompt_search_count_pill_png_snapshot[flexoki-prompt_search_count_pill_flexoki_120x40-ACE prompt input - committed search count pill, flexoki theme]
13.09s call     tests/ace/tui/visual/test_ace_png_snapshots_finalizer_completion.py::test_finalizer_completion_mixed_menu_narrow_png_snapshot
12.92s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
12.81s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_cursor_readout.py::test_prompt_cursor_readout_stack_png_snapshot
12.59s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_macro.py::test_mini_macro_pane_new_and_clean_png_snapshots[True-mini_macro_pane_clean_light_120x40-ACE mini-macro pane - clean light]
12.50s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting_search.py::test_prompt_search_count_pill_png_snapshot[textual-dark-prompt_search_count_pill_dark_120x40-ACE prompt input - committed search count pill, dark theme]
12.46s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting_markdown.py::test_prompt_bullet_highlight_solo_png_snapshot[textual-dark-prompt_bullet_highlight_solo_dark_120x40-ACE prompt input \u2014 bullet-dash highlighting, dark theme]
12.46s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting_refs.py::test_prompt_project_tag_highlight_png_snapshot[textual-light-prompt_project_tag_highlight_light_120x40-ACE prompt input \u2014 project tag highlighting, light theme]
12.44s call     tests/ace/tui/visual/test_ace_png_snapshots_vcs_repo_completion.py::test_vcs_repo_error_panel_png_snapshot
12.39s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_vim_cursor_insert_png_snapshot
12.38s call     tests/ace/tui/visual/test_ace_png_snapshots_vcs_project_completion.py::test_vcs_project_completion_panel_png_snapshot
12.25s call     tests/ace/tui/visual/test_ace_png_snapshots_macro_arg_completion.py::test_macro_arg_enum_value_completion_png_snapshot[dark]
======================= 387 passed in 167.38s (0:02:47) ========================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16
configfile: pyproject.toml
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, platformdirs-4.12.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
4.77s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.29s call     tests/pager/visual/test_history_png_snapshots.py::test_history_png_snapshot[tombstone-True-size1]
0.17s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_sessions.py::test_renamed_generic_agent_session_root_png_snapshot
0.01s setup    tests/pager/visual/test_history_png_snapshots.py::test_history_png_snapshot[tombstone-True-size1]

(2 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 10.50s ==============================
fix-tui-screenshots: update applied
scope: full
counts: created=0 updated=386 unchanged=738 stale=0
manifest: .pytest_cache/sase-visual/runs/32fc3e03bf064afc938d0124db815bcb/manifest.json
run-dir: .pytest_cache/sase-visual/runs/32fc3e03bf064afc938d0124db815bcb
report: .pytest_cache/sase-visual/runs/32fc3e03bf064afc938d0124db815bcb/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/32fc3e03bf064afc938d0124db815bcb/report/summary.md
succeeded  exit=0  duration=1996587ms

