# Chat History - ace-run (sase-1tz.4.1.10--mon-0)

- **TIMESTAMP:** 2026-11-20 18:44:26 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.4.1.10--mon-0

## Prompt

sase monitor start --command 'just check' --reason 'Verify notify_quieting before host completion (full-suite escalation needs ~2h)'

## Response

sase tool run d2531174b13b310c3c0ca51577f1894c
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core to origin/master
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
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/bin/python
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
   Compiling regex-syntax v0.8.10
   Compiling bytes v1.11.1
   Compiling serde v1.0.228
   Compiling log v0.4.29
   Compiling siphasher v1.0.4
   Compiling futures-core v0.3.32
   Compiling zmij v1.0.21
   Compiling version_check v0.9.5
   Compiling crossbeam-epoch v0.9.21
   Compiling smallvec v1.15.1
   Compiling serde_json v1.0.149
   Compiling crossbeam-deque v0.8.8
   Compiling stable_deref_trait v1.2.1
   Compiling target-lexicon v0.12.16
   Compiling futures-sink v0.3.32
   Compiling equivalent v1.0.2
   Compiling hashbrown v0.17.0
   Compiling futures-task v0.3.32
   Compiling iana-time-zone v0.1.65
   Compiling futures-io v0.3.32
   Compiling slab v0.4.12
   Compiling ucd-trie v0.1.7
   Compiling tower-service v0.3.3
   Compiling bitflags v2.11.1
   Compiling libm v0.2.16
   Compiling heck v0.5.0
   Compiling litemap v0.8.2
   Compiling writeable v0.6.3
   Compiling httparse v1.10.1
   Compiling untrusted v0.9.0
   Compiling same-file v1.0.6
   Compiling icu_normalizer_data v2.2.0
   Compiling typenum v1.20.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling parking_lot_core v0.9.12
   Compiling deunicode v1.6.2
   Compiling fnv v1.0.7
   Compiling httpdate v1.0.3
   Compiling lazy_static v1.5.0
   Compiling tower-layer v0.3.3
   Compiling sync_wrapper v1.0.2
   Compiling percent-encoding v2.3.2
   Compiling rustls v0.21.12
   Compiling encoding_rs v0.8.35
   Compiling pkg-config v0.3.33
   Compiling clap_lex v1.1.1
   Compiling phf_shared v0.11.3
   Compiling rayon-core v1.13.0
   Compiling scopeguard v1.2.0
   Compiling thiserror v1.0.69
   Compiling ryu v1.0.23
   Compiling tracing-core v0.1.36
   Compiling unicode-segmentation v1.13.3
   Compiling vcpkg v0.2.15
   Compiling anstyle v1.0.14
   Compiling either v1.19.0
   Compiling cc v1.2.61
   Compiling powerfmt v0.2.0
   Compiling num-traits v0.2.19
   Compiling num-conv v0.2.1
   Compiling walkdir v2.5.0
   Compiling getrandom v0.4.2
   Compiling rustversion v1.0.22
   Compiling futures-channel v0.3.32
   Compiling time-core v0.1.8
   Compiling rustix v1.1.4
   Compiling winnow v1.0.4
   Compiling thiserror v2.0.18
   Compiling generic-array v0.14.7
   Compiling ahash v0.8.12
   Compiling try-lock v0.2.5
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling atomic-waker v1.1.2
   Compiling winnow v0.7.15
   Compiling linux-raw-sys v0.12.1
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling slug v0.1.6
   Compiling grep-matcher v0.1.9
   Compiling cpufeatures v0.2.17
   Compiling home v0.5.12
   Compiling colored v2.2.0
   Compiling pyo3-build-config v0.22.6
   Compiling mime v0.3.17
   Compiling indexmap v2.14.0
   Compiling phf v0.11.3
   Compiling http v1.4.0
   Compiling http v0.2.12
   Compiling memoffset v0.9.1
   Compiling humansize v2.1.3
   Compiling tinyvec v1.13.3
   Compiling crossbeam-channel v0.5.17
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling getrandom v0.2.17
   Compiling mio v1.2.0
   Compiling lock_api v0.4.14
   Compiling itertools v0.11.0
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling memmap2 v0.9.11
   Compiling socket2 v0.5.10
   Compiling term_size v0.3.2
   Compiling deranged v0.5.8
   Compiling fallible-iterator v0.3.0
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling base64 v0.21.7
   Compiling unsafe-libyaml v0.2.11
   Compiling form_urlencoded v1.2.2
   Compiling libsqlite3-sys v0.30.1
   Compiling fallible-streaming-iterator v0.1.9
   Compiling fastrand v2.4.1
   Compiling time-macros v0.2.27
   Compiling base64 v0.22.1
   Compiling serde_spanned v1.1.2
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling serde_path_to_error v0.1.20
   Compiling etcetera v0.8.0
   Compiling fs2 v0.4.3
   Compiling sharded-slab v0.1.7
   Compiling thread_local v1.1.9
   Compiling want v0.3.1
   Compiling hex v0.4.3
   Compiling sync_wrapper v0.1.2
   Compiling nu-ansi-term v0.50.3
   Compiling rand_core v0.6.4
   Compiling tracing-log v0.2.0
   Compiling encoding_rs_io v0.1.8
   Compiling unicode-width v0.2.2
   Compiling chrono v0.4.44
   Compiling webpki-roots v0.25.4
   Compiling matchit v0.7.3
   Compiling clap_builder v4.6.7
   Compiling crypto-common v0.1.7
   Compiling block-buffer v0.10.4
   Compiling ipnet v2.12.0
   Compiling pyo3-ffi v0.22.6
   Compiling num-integer v0.1.46
   Compiling pyo3-macros-backend v0.22.6
   Compiling parking_lot v0.12.5
   Compiling regex-automata v0.4.14
   Compiling pyo3 v0.22.6
   Compiling unicode-casefold v0.2.0
   Compiling signal-hook-registry v1.4.8
   Compiling semver v1.0.28
   Compiling unicode-normalization v0.1.25
   Compiling unindent v0.2.4
   Compiling indoc v2.0.7
   Compiling http-body v0.4.6
   Compiling http-body v1.0.1
   Compiling ppv-lite86 v0.2.21
   Compiling pem v3.0.6
   Compiling rustls-pemfile v1.0.4
   Compiling toml v0.9.12+spec-1.1.0
   Compiling grep-searcher v0.1.17
   Compiling time v0.3.47
   Compiling digest v0.10.7
   Compiling num-bigint v0.4.6
   Compiling tempfile v3.27.0
   Compiling http-body-util v0.1.3
   Compiling hashbrown v0.14.5
   Compiling pest v2.9.4
   Compiling rand_chacha v0.3.1
   Compiling sha2 v0.10.9
   Compiling sha1 v0.10.7
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling rand v0.8.6
   Compiling hashlink v0.9.1
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling rayon v1.12.0
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling pest_meta v2.9.4
   Compiling phf_generator v0.11.3
   Compiling phf_codegen v0.11.3
   Compiling chrono-tz-build v0.3.0
   Compiling globwalk v0.9.1
   Compiling chrono-tz v0.9.0
   Compiling rustls-webpki v0.101.7
   Compiling sct v0.7.1
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling arbitrary v1.5.0
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
   Compiling pest_derive v2.9.4
   Compiling async-stream v0.3.6
   Compiling tokio v1.52.2
   Compiling clap v4.6.7
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling clap-cargo v0.18.3
   Compiling zerofrom v0.1.7
   Compiling simple_asn1 v0.6.4
   Compiling table_formatter v0.6.1
   Compiling yoke v0.8.2
   Compiling tower-http v0.5.2
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling matchers v0.2.0
   Compiling tracing-subscriber v0.3.23
   Compiling tera v1.20.1
   Compiling json5 v0.4.1
   Compiling serde_urlencoded v0.7.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
   Compiling pyo3-macros v0.22.6
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling axum-core v0.4.5
   Compiling icu_locale_core v2.2.0
   Compiling icu_collections v2.2.0
   Compiling tokei v15.0.0
   Compiling icu_provider v2.2.0
   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling idna_adapter v1.2.2
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling hyper v1.9.0
   Compiling tokio-rustls v0.24.1
   Compiling idna v1.1.0
   Compiling h2 v0.3.27
   Compiling url v2.5.8
   Compiling hyper-util v0.1.20
   Compiling axum v0.7.9
   Compiling hyper v0.14.32
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_gateway v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 15m 13s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-eijlvwio/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/0a9e72208521346e993b11b6cd2f790817988cedcc701aaff5f8ee0a13842547/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 167ms
Uninstalled 1 package in 2ms
Installed 1 package in 2ms
 - sase-core-rs==0.44.2 (from file:///home/bryan/.sase/cache/sase-core-artifacts/a042bae53e5ac07a5e5b13bcc28fc8f840fe21d149eed38d8a3311bc495b30e7/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.44.2 (from file:///home/bryan/.sase/cache/sase-core-artifacts/0a9e72208521346e993b11b6cd2f790817988cedcc701aaff5f8ee0a13842547/sase_core_rs-0.44.2-cp312-abi3-manylinux_2_39_x86_64.whl)
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
   Compiling shlex v1.3.0
   Compiling find-msvc-tools v0.1.9
   Compiling regex-syntax v0.8.10
   Compiling siphasher v1.0.4
   Compiling version_check v0.9.5
   Compiling autocfg v1.5.0
   Compiling serde v1.0.228
   Compiling zmij v1.0.21
   Compiling crossbeam-epoch v0.9.21
   Compiling once_cell v1.21.4
   Compiling serde_json v1.0.149
   Compiling crossbeam-deque v0.8.8
   Compiling log v0.4.29
   Compiling ucd-trie v0.1.7
   Compiling iana-time-zone v0.1.65
   Compiling equivalent v1.0.2
   Compiling hashbrown v0.17.0
   Compiling pin-project-lite v0.2.17
   Compiling itoa v1.0.18
   Compiling bitflags v2.11.1
   Compiling smallvec v1.15.1
   Compiling same-file v1.0.6
   Compiling futures-core v0.3.32
   Compiling libm v0.2.16
   Compiling futures-sink v0.3.32
   Compiling typenum v1.20.0
   Compiling parking_lot_core v0.9.12
   Compiling futures-task v0.3.32
   Compiling lazy_static v1.5.0
   Compiling slab v0.4.12
   Compiling futures-io v0.3.32
   Compiling bytes v1.11.1
   Compiling deunicode v1.6.2
   Compiling scopeguard v1.2.0
   Compiling heck v0.5.0
   Compiling thiserror v1.0.69
   Compiling either v1.19.0
   Compiling vcpkg v0.2.15
   Compiling rayon-core v1.13.0
   Compiling percent-encoding v2.3.2
   Compiling unicode-segmentation v1.13.3
   Compiling anstyle v1.0.14
   Compiling clap_lex v1.1.1
   Compiling pkg-config v0.3.33
   Compiling rustix v1.1.4
   Compiling tower-layer v0.3.3
   Compiling tower-service v0.3.3
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling tracing-core v0.1.36
   Compiling phf_shared v0.11.3
   Compiling num-traits v0.2.19
   Compiling cc v1.2.61
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling encoding_rs v0.8.35
   Compiling sync_wrapper v1.0.2
   Compiling winnow v1.0.4
   Compiling getrandom v0.4.2
   Compiling itertools v0.11.0
   Compiling httparse v1.10.1
   Compiling home v0.5.12
   Compiling linux-raw-sys v0.12.1
   Compiling cpufeatures v0.2.17
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling winnow v0.7.15
   Compiling indexmap v2.14.0
   Compiling walkdir v2.5.0
   Compiling bitflags v1.3.2
   Compiling grep-matcher v0.1.9
   Compiling colored v2.2.0
   Compiling fallible-streaming-iterator v0.1.9
   Compiling unsafe-libyaml v0.2.11
   Compiling tinyvec v1.13.3
   Compiling futures-channel v0.3.32
   Compiling clap_builder v4.6.7
   Compiling ryu v1.0.23
   Compiling fastrand v2.4.1
   Compiling fallible-iterator v0.3.0
   Compiling sharded-slab v0.1.7
   Compiling lock_api v0.4.14
   Compiling thread_local v1.1.9
   Compiling nu-ansi-term v0.50.3
   Compiling unicode-width v0.2.2
   Compiling slug v0.1.6
   Compiling semver v1.0.28
   Compiling hex v0.4.3
   Compiling unicode-casefold v0.2.0
   Compiling ppv-lite86 v0.2.21
   Compiling serde_spanned v1.1.2
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling crossbeam-channel v0.5.17
   Compiling getrandom v0.2.17
   Compiling phf v0.11.3
   Compiling errno v0.3.14
   Compiling mio v1.2.0
   Compiling socket2 v0.6.3
   Compiling memmap2 v0.9.11
   Compiling humansize v2.1.3
   Compiling term_size v0.3.2
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling libsqlite3-sys v0.30.1
   Compiling tracing-log v0.2.0
   Compiling regex-automata v0.4.14
   Compiling encoding_rs_io v0.1.8
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling etcetera v0.8.0
   Compiling fs2 v0.4.3
   Compiling fluent-uri v0.1.4
   Compiling unicode-normalization v0.1.25
   Compiling crypto-common v0.1.7
   Compiling block-buffer v0.10.4
   Compiling hashbrown v0.14.5
   Compiling rand_core v0.6.4
   Compiling signal-hook-registry v1.4.8
   Compiling parking_lot v0.12.5
   Compiling grep-searcher v0.1.17
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling toml v0.9.12+spec-1.1.0
   Compiling matchers v0.2.0
   Compiling digest v0.10.7
   Compiling hashlink v0.9.1
   Compiling rand_chacha v0.3.1
   Compiling tempfile v3.27.0
   Compiling chrono v0.4.44
   Compiling ignore v0.4.32
   Compiling parse-zoneinfo v0.3.1
   Compiling pest v2.9.4
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling rand v0.8.6
   Compiling rayon v1.12.0
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling globwalk v0.9.1
   Compiling pest_meta v2.9.4
   Compiling phf_generator v0.11.3
   Compiling phf_codegen v0.11.3
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling serde_derive v1.0.228
   Compiling tokio-macros v2.7.0
   Compiling tracing-attributes v0.1.31
   Compiling futures-macro v0.3.32
   Compiling thiserror-impl v1.0.69
   Compiling serde_repr v0.1.20
   Compiling chrono-tz-build v0.3.0
   Compiling arbitrary v1.5.0
   Compiling tokio v1.52.2
   Compiling pest_derive v2.9.4
   Compiling futures-util v0.3.32
   Compiling chrono-tz v0.9.0
   Compiling tracing v0.1.44
   Compiling clap v4.6.7
   Compiling table_formatter v0.6.1
   Compiling tracing-subscriber v0.3.23
   Compiling clap-cargo v0.18.3
   Compiling futures v0.3.32
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling lsp-types v0.97.0
   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling tokei v15.0.0
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_macro_lsp v0.44.2 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Finished `dev-update` profile [optimized] target(s) in 3m 28s
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/217df327e38293e3a85405f199c8b4e9727cd423b4df5c80bd6b77b7c8ea735b/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/.venv/bin/sase-macro-lsp
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.44.2 is missing 47 capability(s), and at least one has no containing sase-core release tag yet.
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
[core-floor-probe] axe_error_wire_schema_version: first appears in sase-core 3a32a23 (feat(axe-error): add volatile-token normalizer and signature grouping); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_touch_member_query_wire_schema_version: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] bead_triage_owner_candidates: first appears in sase-core cb76eb2 (feat(bead): project triage owner candidates from the read model); no release tag contains it yet.
[core-floor-probe] bead_view_member_query: first appears in sase-core 9f9341e (feat(bead): add member-targeted touch index query with streaming views fold); no release tag contains it yet.
[core-floor-probe] chop_batch_generation_matches: first appears in sase-core b1a0363 (feat(axe-chop): add clan-scoped generation match and cancelled settlement); no release tag contains it yet.
[core-floor-probe] decide_local_command_trust: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] decide_publication_standing: first appears in sase-core 3c3263f (feat(publication): add standing-alert decider with capped backoff); no release tag contains it yet.
[core-floor-probe] digest_local_commands: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
[core-floor-probe] filter_trusted_local_layer: first appears in sase-core e7647bf (feat(config): add digest-pinned local-command trust contract and bindings); no release tag contains it yet.
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
[core-floor-probe] scan_agent_artifact_dirs_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] scan_agent_artifacts_list: first appears in sase-core 8cedd45 (feat: add compact agent-list wire contracts and PyO3 bindings); no release tag contains it yet.
[core-floor-probe] select_agent_artifact_group: first appears in sase-core b9f33b0 (feat(agent-scan): select indexed session and clan generations); no release tag contains it yet.
[core-floor-probe] select_named_agent: first appears in sase-core d201086 (feat(agent-scan): add bounded named lookup selection); no release tag contains it yet.
[core-floor-probe] select_unscanned_coverage: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); no release tag contains it yet.
[core-floor-probe] suggest_unscanned_repair: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); no release tag contains it yet.
[core-floor-probe] summarize_chop_batch: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
[core-floor-probe] unscanned_wire_schema_version: first appears in sase-core 7ac2081 (feat(finalizer): add shared unscanned-writes coverage and repair policy); no release tag contains it yet.
[core-floor-probe] validate_chop_batch_manifest: first appears in sase-core 6cd9a0c (feat(axe-chop): versioned crash-safe chop batch contract); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "8cedd45", "name": "agent_artifact_list_wire_schema_version", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "9940715", "name": "agent_hijack_decide", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "9940715", "name": "agent_hijack_eligibility_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_observe", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "agent_hijack_latch_wire_schema_version", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "9940715", "name": "agent_hijack_select_occupant", "release": null, "subject": "feat(agent-hijack): add eligibility v2 wire, occupant selection, stop_blocked ledger"}, {"commit": "6cd9a0c", "name": "apply_chop_batch_transition", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "19b89ac", "name": "artifact_file_association_query", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "19b89ac", "name": "artifact_file_association_query_wire_schema_version", "release": null, "subject": "feat(artifact-file): add targeted association query over JSONL index"}, {"commit": "3992fce", "name": "artifact_read_audit_query", "release": null, "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "3992fce", "name": "artifact_read_audit_query_wire_schema_version", "release": null, "subject": "feat(audit-query): query artifact-read audit logs"}, {"commit": "3a32a23", "name": "axe_error_wire_schema_version", "release": null, "subject": "feat(axe-error): add volatile-token normalizer and signature grouping"}, {"commit": "9f9341e", "name": "bead_touch_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "9f9341e", "name": "bead_touch_member_query_wire_schema_version", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "cb76eb2", "name": "bead_triage_owner_candidates", "release": null, "subject": "feat(bead): project triage owner candidates from the read model"}, {"commit": "9f9341e", "name": "bead_view_member_query", "release": null, "subject": "feat(bead): add member-targeted touch index query with streaming views fold"}, {"commit": "b1a0363", "name": "chop_batch_generation_matches", "release": null, "subject": "feat(axe-chop): add clan-scoped generation match and cancelled settlement"}, {"commit": "e7647bf", "name": "decide_local_command_trust", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "3c3263f", "name": "decide_publication_standing", "release": null, "subject": "feat(publication): add standing-alert decider with capped backoff"}, {"commit": "e7647bf", "name": "digest_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "e7647bf", "name": "filter_trusted_local_layer", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "3a32a23", "name": "group_axe_errors", "release": null, "subject": "feat(axe-error): add volatile-token normalizer and signature grouping"}, {"commit": "e9b1cf0", "name": "hijack_latch_force_eligibility", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "e9b1cf0", "name": "hijack_latch_reconcile", "release": null, "subject": "feat(agent-hijack): add latch ledger policy and bindings"}, {"commit": "233cb41", "name": "local_command_trust_store_allow", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_get", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "233cb41", "name": "local_command_trust_store_revoke", "release": null, "subject": "feat(config): persist digest-pinned local command trust"}, {"commit": "e7647bf", "name": "local_command_trust_wire_schema_version", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "a4b1c84", "name": "lookup_agent_artifacts", "release": null, "subject": "feat(agent-scan): add read-only indexed artifact identity lookups"}, {"commit": "d201086", "name": "lookup_named_dismissed_bundle", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "c5e60d7", "name": "memory_audit_query", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "c5e60d7", "name": "memory_audit_query_wire_schema_version", "release": null, "subject": "feat(audit-query): add targeted memory audit query over JSONL"}, {"commit": "3a32a23", "name": "normalize_error_signature", "release": null, "subject": "feat(axe-error): add volatile-token normalizer and signature grouping"}, {"commit": "1191f9a", "name": "plan_prompt_command_substitution", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "e7647bf", "name": "project_local_commands", "release": null, "subject": "feat(config): add digest-pinned local-command trust contract and bindings"}, {"commit": "1191f9a", "name": "prompt_command_substitution_wire_schema_version", "release": null, "subject": "feat: add prompt command-substitution source policy"}, {"commit": "8cedd45", "name": "query_agent_artifact_index_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "6cd9a0c", "name": "reconcile_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "8cedd45", "name": "scan_agent_artifact_dirs_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "8cedd45", "name": "scan_agent_artifacts_list", "release": null, "subject": "feat: add compact agent-list wire contracts and PyO3 bindings"}, {"commit": "b9f33b0", "name": "select_agent_artifact_group", "release": null, "subject": "feat(agent-scan): select indexed session and clan generations"}, {"commit": "d201086", "name": "select_named_agent", "release": null, "subject": "feat(agent-scan): add bounded named lookup selection"}, {"commit": "7ac2081", "name": "select_unscanned_coverage", "release": null, "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "7ac2081", "name": "suggest_unscanned_repair", "release": null, "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "6cd9a0c", "name": "summarize_chop_batch", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}, {"commit": "7ac2081", "name": "unscanned_wire_schema_version", "release": null, "subject": "feat(finalizer): add shared unscanned-writes coverage and repair policy"}, {"commit": "6cd9a0c", "name": "validate_chop_batch_manifest", "release": null, "subject": "feat(axe-chop): versioned crash-safe chop batch contract"}], "declared_floor": "0.44.2", "exit_code": 4, "message": "sase-core-rs==0.44.2 is missing 47 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✓ docs (build + links)
✓ test (scoped)
scoped: escalated to the full suite (rules: core-identity-changed, src-data-asset); contexts baseline not consulted
succeeded  exit=0  duration=3725869ms
unattrib  19m 18s

