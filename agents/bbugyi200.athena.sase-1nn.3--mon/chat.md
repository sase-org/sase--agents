# Chat History - ace-run (sase-1nn.3--mon)

- **TIMESTAMP:** 2026-10-23 12:17:15 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1nn.3--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'finish check (joined run)'

## Response

sase tool run 399cf5928cebd2fc5752cf5069e2aef7
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.42.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[core-source] linked sase-core source changed since the extension was built; flagging an extension rebuild.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
[setup] Rebuilding sase_core_rs: linked sase-core source changed since the extension was built.
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.42.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[rust-install] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev builds from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core ignore it. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/bin/python
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
   Compiling target-lexicon v0.12.16
   Compiling stable_deref_trait v1.2.1
   Compiling crossbeam-deque v0.8.8
   Compiling futures-sink v0.3.32
   Compiling equivalent v1.0.2
   Compiling hashbrown v0.17.0
   Compiling tower-service v0.3.3
   Compiling iana-time-zone v0.1.65
   Compiling slab v0.4.12
   Compiling futures-io v0.3.32
   Compiling ucd-trie v0.1.7
   Compiling futures-task v0.3.32
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
   Compiling lazy_static v1.5.0
   Compiling fnv v1.0.7
   Compiling tower-layer v0.3.3
   Compiling deunicode v1.6.2
   Compiling parking_lot_core v0.9.12
   Compiling httpdate v1.0.3
   Compiling clap_lex v1.1.1
   Compiling encoding_rs v0.8.35
   Compiling unicode-segmentation v1.13.3
   Compiling vcpkg v0.2.15
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling rustls v0.21.12
   Compiling cc v1.2.61
   Compiling generic-array v0.14.7
   Compiling ahash v0.8.12
   Compiling thiserror v1.0.69
   Compiling sync_wrapper v1.0.2
   Compiling tracing-core v0.1.36
   Compiling anstyle v1.0.14
   Compiling percent-encoding v2.3.2
   Compiling scopeguard v1.2.0
   Compiling num-traits v0.2.19
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling ryu v1.0.23
   Compiling pkg-config v0.3.33
   Compiling slug v0.1.6
   Compiling time-core v0.1.8
   Compiling thiserror v2.0.18
   Compiling winnow v1.0.4
   Compiling rustversion v1.0.22
   Compiling getrandom v0.4.2
   Compiling walkdir v2.5.0
   Compiling num-conv v0.2.1
   Compiling try-lock v0.2.5
   Compiling rustix v1.1.4
   Compiling powerfmt v0.2.0
   Compiling colored v2.2.0
   Compiling pyo3-build-config v0.22.6
   Compiling grep-matcher v0.1.9
   Compiling futures-channel v0.3.32
   Compiling http v1.4.0
   Compiling http v0.2.12
   Compiling cpufeatures v0.2.17
   Compiling mime v0.3.17
   Compiling phf_shared v0.11.3
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling home v0.5.12
   Compiling indexmap v2.14.0
   Compiling humansize v2.1.3
   Compiling atomic-waker v1.1.2
   Compiling winnow v0.7.15
   Compiling getrandom v0.2.17
   Compiling errno v0.3.14
   Compiling mio v1.2.0
   Compiling socket2 v0.6.3
   Compiling lock_api v0.4.14
   Compiling memmap2 v0.9.11
   Compiling clap_builder v4.6.7
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling itertools v0.11.0
   Compiling socket2 v0.5.10
   Compiling linux-raw-sys v0.12.1
   Compiling crossbeam-channel v0.5.17
   Compiling libsqlite3-sys v0.30.1
   Compiling form_urlencoded v1.2.2
   Compiling term_size v0.3.2
   Compiling memoffset v0.9.1
   Compiling tinyvec v1.13.3
   Compiling unsafe-libyaml v0.2.11
   Compiling serde_spanned v1.1.2
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling time-macros v0.2.27
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling want v0.3.1
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling deranged v0.5.8
   Compiling base64 v0.22.1
   Compiling fastrand v2.4.1
   Compiling fallible-streaming-iterator v0.1.9
   Compiling encoding_rs_io v0.1.8
   Compiling base64 v0.21.7
   Compiling etcetera v0.8.0
   Compiling ppv-lite86 v0.2.21
   Compiling fallible-iterator v0.3.0
   Compiling regex-automata v0.4.14
   Compiling rand_core v0.6.4
   Compiling serde_path_to_error v0.1.20
   Compiling tracing-log v0.2.0
   Compiling http-body v0.4.6
   Compiling fs2 v0.4.3
   Compiling sharded-slab v0.1.7
   Compiling http-body v1.0.1
   Compiling thread_local v1.1.9
   Compiling matchit v0.7.3
   Compiling signal-hook-registry v1.4.8
   Compiling unicode-width v0.2.2
   Compiling hex v0.4.3
   Compiling ipnet v2.12.0
   Compiling unicode-casefold v0.2.0
   Compiling phf v0.11.3
   Compiling webpki-roots v0.25.4
   Compiling sync_wrapper v0.1.2
   Compiling parking_lot v0.12.5
   Compiling nu-ansi-term v0.50.3
   Compiling indoc v2.0.7
   Compiling unindent v0.2.4
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
   Compiling chrono v0.4.44
   Compiling num-integer v0.1.46
   Compiling unicode-normalization v0.1.25
   Compiling digest v0.10.7
   Compiling hashbrown v0.14.5
   Compiling rustls-pemfile v1.0.4
   Compiling grep-searcher v0.1.17
   Compiling rand_chacha v0.3.1
   Compiling toml v0.9.12+spec-1.1.0
   Compiling http-body-util v0.1.3
   Compiling num-bigint v0.4.6
   Compiling pem v3.0.6
   Compiling time v0.3.47
   Compiling pest v2.9.4
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling rand v0.8.6
   Compiling hashlink v0.9.1
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling rayon v1.12.0
   Compiling tempfile v3.27.0
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling phf_generator v0.11.3
   Compiling ignore v0.4.32
   Compiling parse-zoneinfo v0.3.1
   Compiling pest_meta v2.9.4
   Compiling phf_codegen v0.11.3
   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
   Compiling chrono-tz-build v0.3.0
   Compiling globwalk v0.9.1
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
   Compiling async-stream v0.3.6
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling clap-cargo v0.18.3
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling tracing v0.1.44
   Compiling table_formatter v0.6.1
   Compiling zerofrom v0.1.7
   Compiling simple_asn1 v0.6.4
   Compiling tower-http v0.5.2
   Compiling yoke v0.8.2
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling matchers v0.2.0
   Compiling tracing-subscriber v0.3.23
   Compiling serde_urlencoded v0.7.1
   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling pyo3-macros v0.22.6
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling icu_collections v2.2.0
   Compiling icu_locale_core v2.2.0
   Compiling axum-core v0.4.5
   Compiling tokei v15.0.0
   Compiling icu_provider v2.2.0
   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling tokio-rustls v0.24.1
   Compiling hyper v1.9.0
   Compiling idna_adapter v1.2.2
   Compiling idna v1.1.0
   Compiling h2 v0.3.27
   Compiling hyper-util v0.1.20
   Compiling url v2.5.8
   Compiling axum v0.7.9
   Compiling hyper v0.14.32
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/crates/sase_core)
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
   Compiling sase_gateway v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 16m 26s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-a1vggkk7/sase_core_rs-0.42.1-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/d3f30a779a938d3a3a0ccdb30a49cb25b617b5ece2898fd16c925ea4b007f59f/sase_core_rs-0.42.1-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 3ms
Prepared 1 package in 155ms
Uninstalled 1 package in 62ms
Installed 1 package in 2ms
 - sase-core-rs==0.42.1 (from file:///home/bryan/.sase/cache/sase-core-artifacts/7791b3cce356307101162e21721f79ac97befcddbf8f4fd6c1ede38a45fc4f34/sase_core_rs-0.42.1-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.42.1 (from file:///home/bryan/.sase/cache/sase-core-artifacts/d3f30a779a938d3a3a0ccdb30a49cb25b617b5ece2898fd16c925ea4b007f59f/sase_core_rs-0.42.1-cp312-abi3-manylinux_2_39_x86_64.whl)
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
   Compiling serde_json v1.0.149
   Compiling crossbeam-deque v0.8.8
   Compiling log v0.4.29
   Compiling pin-project-lite v0.2.17
   Compiling equivalent v1.0.2
   Compiling iana-time-zone v0.1.65
   Compiling ucd-trie v0.1.7
   Compiling hashbrown v0.17.0
   Compiling bitflags v2.11.1
   Compiling itoa v1.0.18
   Compiling smallvec v1.15.1
   Compiling libm v0.2.16
   Compiling futures-sink v0.3.32
   Compiling same-file v1.0.6
   Compiling futures-core v0.3.32
   Compiling typenum v1.20.0
   Compiling parking_lot_core v0.9.12
   Compiling futures-io v0.3.32
   Compiling lazy_static v1.5.0
   Compiling scopeguard v1.2.0
   Compiling futures-task v0.3.32
   Compiling deunicode v1.6.2
   Compiling slab v0.4.12
   Compiling bytes v1.11.1
   Compiling unicode-segmentation v1.13.3
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling clap_lex v1.1.1
   Compiling thiserror v1.0.69
   Compiling heck v0.5.0
   Compiling pkg-config v0.3.33
   Compiling anstyle v1.0.14
   Compiling percent-encoding v2.3.2
   Compiling vcpkg v0.2.15
   Compiling rustix v1.1.4
   Compiling tower-service v0.3.3
   Compiling winnow v1.0.4
   Compiling slug v0.1.6
   Compiling sync_wrapper v1.0.2
   Compiling getrandom v0.4.2
   Compiling tower-layer v0.3.3
   Compiling walkdir v2.5.0
   Compiling ahash v0.8.12
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling generic-array v0.14.7
   Compiling encoding_rs v0.8.35
   Compiling tracing-core v0.1.36
   Compiling phf_shared v0.11.3
   Compiling colored v2.2.0
   Compiling num-traits v0.2.19
   Compiling winnow v0.7.15
   Compiling bitflags v1.3.2
   Compiling httparse v1.10.1
   Compiling linux-raw-sys v0.12.1
   Compiling cc v1.2.61
   Compiling home v0.5.12
   Compiling cpufeatures v0.2.17
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling fallible-iterator v0.3.0
   Compiling tinyvec v1.13.3
   Compiling errno v0.3.14
   Compiling mio v1.2.0
   Compiling socket2 v0.6.3
   Compiling humansize v2.1.3
   Compiling lock_api v0.4.14
   Compiling getrandom v0.2.17
   Compiling itertools v0.11.0
   Compiling memmap2 v0.9.11
   Compiling crossbeam-channel v0.5.17
   Compiling term_size v0.3.2
   Compiling ryu v1.0.23
   Compiling unsafe-libyaml v0.2.11
   Compiling fastrand v2.4.1
   Compiling futures-channel v0.3.32
   Compiling fallible-streaming-iterator v0.1.9
   Compiling fs2 v0.4.3
   Compiling sharded-slab v0.1.7
   Compiling thread_local v1.1.9
   Compiling indexmap v2.14.0
   Compiling nu-ansi-term v0.50.3
   Compiling unicode-width v0.2.2
   Compiling hex v0.4.3
   Compiling serde_spanned v1.1.2
   Compiling clap_builder v4.6.7
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling grep-matcher v0.1.9
   Compiling unicode-casefold v0.2.0
   Compiling regex-automata v0.4.14
   Compiling ppv-lite86 v0.2.21
   Compiling phf v0.11.3
   Compiling encoding_rs_io v0.1.8
   Compiling unicode-normalization v0.1.25
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling libsqlite3-sys v0.30.1
   Compiling etcetera v0.8.0
   Compiling rand_core v0.6.4
   Compiling tracing-log v0.2.0
   Compiling chrono v0.4.44
   Compiling fluent-uri v0.1.4
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling signal-hook-registry v1.4.8
   Compiling grep-searcher v0.1.17
   Compiling hashbrown v0.14.5
   Compiling toml v0.9.12+spec-1.1.0
   Compiling parking_lot v0.12.5
   Compiling rand_chacha v0.3.1
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling tempfile v3.27.0
   Compiling digest v0.10.7
   Compiling hashlink v0.9.1
   Compiling rand v0.8.6
   Compiling pest v2.9.4
   Compiling parse-zoneinfo v0.3.1
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling ignore v0.4.32
   Compiling rayon v1.12.0
   Compiling matchers v0.2.0
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
   Compiling futures-macro v0.3.32
   Compiling tracing-attributes v0.1.31
   Compiling tokio-macros v2.7.0
   Compiling thiserror-impl v1.0.69
   Compiling serde_repr v0.1.20
   Compiling chrono-tz-build v0.3.0
   Compiling pest_derive v2.9.4
   Compiling chrono-tz v0.9.0
   Compiling arbitrary v1.5.0
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling tracing-subscriber v0.3.23
   Compiling table_formatter v0.6.1
   Compiling clap v4.6.7
   Compiling clap-cargo v0.18.3
   Compiling futures v0.3.32
   Compiling tower v0.5.3
   Compiling tokio-util v0.7.18
   Compiling dashmap v6.1.0
   Compiling lsp-types v0.97.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling tokei v15.0.0
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_macro_lsp v0.42.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Finished `dev-update` profile [optimized] target(s) in 3m 31s
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/2bfc8458e25c5cf008986a04f41339923f07cb3d4e6d91ed69424bccf21f43ae/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/bin/sase-macro-lsp
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.42.0 is missing 9 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] classify_publication_error: first appears in sase-core f9aa563 (feat(publication-recovery): add failure accounting and bounded drain selection); no release tag contains it yet.
[core-floor-probe] classify_replay_paths: first appears in sase-core 461e7a1 (feat(vcs): add stale-replay conflict and preservation policy); no release tag contains it yet.
[core-floor-probe] decide_publication_failure_accounting: first appears in sase-core f9aa563 (feat(publication-recovery): add failure accounting and bounded drain selection); no release tag contains it yet.
[core-floor-probe] decide_replay_apply: first appears in sase-core 461e7a1 (feat(vcs): add stale-replay conflict and preservation policy); no release tag contains it yet.
[core-floor-probe] decide_replay_byte_divergence: first appears in sase-core 461e7a1 (feat(vcs): add stale-replay conflict and preservation policy); no release tag contains it yet.
[core-floor-probe] decide_replay_hood_merge: first appears in sase-core 461e7a1 (feat(vcs): add stale-replay conflict and preservation policy); no release tag contains it yet.
[core-floor-probe] repair_session_manifest_entry: first appears in sase-core cfae073 (feat(vcs): expose verified manifest repair policy); no release tag contains it yet.
[core-floor-probe] select_publication_drain: first appears in sase-core f9aa563 (feat(publication-recovery): add failure accounting and bounded drain selection); no release tag contains it yet.
[core-floor-probe] sudo_fit_ledger: first appears in sase-core 246e287 (feat(sudo): fit oversized ledgers to the settlement JSON budget); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "f9aa563", "name": "classify_publication_error", "release": null, "subject": "feat(publication-recovery): add failure accounting and bounded drain selection"}, {"commit": "461e7a1", "name": "classify_replay_paths", "release": null, "subject": "feat(vcs): add stale-replay conflict and preservation policy"}, {"commit": "f9aa563", "name": "decide_publication_failure_accounting", "release": null, "subject": "feat(publication-recovery): add failure accounting and bounded drain selection"}, {"commit": "461e7a1", "name": "decide_replay_apply", "release": null, "subject": "feat(vcs): add stale-replay conflict and preservation policy"}, {"commit": "461e7a1", "name": "decide_replay_byte_divergence", "release": null, "subject": "feat(vcs): add stale-replay conflict and preservation policy"}, {"commit": "461e7a1", "name": "decide_replay_hood_merge", "release": null, "subject": "feat(vcs): add stale-replay conflict and preservation policy"}, {"commit": "cfae073", "name": "repair_session_manifest_entry", "release": null, "subject": "feat(vcs): expose verified manifest repair policy"}, {"commit": "f9aa563", "name": "select_publication_drain", "release": null, "subject": "feat(publication-recovery): add failure accounting and bounded drain selection"}, {"commit": "246e287", "name": "sudo_fit_ledger", "release": null, "subject": "feat(sudo): fit oversized ledgers to the settlement JSON budget"}], "declared_floor": "0.42.0", "exit_code": 4, "message": "sase-core-rs==0.42.0 is missing 9 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.42.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 5332 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [57217 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
..............s......................................................... [  0%]
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
...........................s............................................ [  1%]
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
..............................s......................................... [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
...........s............................................................ [  8%]
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
.................................................s...................... [ 13%]
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
......................s................................................. [ 14%]
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
............................s........................................... [ 40%]
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
...................................................s.................... [ 46%]
............................ss.......................................... [ 47%]
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
......................................................................s. [ 49%]
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
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
.................................................................ssss... [ 62%]
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
......................F................................................. [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
..........s............................................................. [ 68%]
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
........................................................................ [ 79%]
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
......F................................................................. [ 88%]
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
........................................................................ [ 92%]
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
....................................................................F... [ 94%]
.......................................................F................ [ 94%]
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
.................................................                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______________ test_populated_perf_renderable_covers_every_panel _______________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/bin/python

    def test_populated_perf_renderable_covers_every_panel() -> None:
        result = _perf_result()
        pane = StatisticsPane(auto_load=False)
        pane._view = "perf"
        rendered = _render_plain(pane._perf_renderable(result))
        tiles = _render_plain(Group(*pane._perf_hero_tiles(result, width=24)))
    
        assert "Startup breakdown" in rendered
        assert "process→mount" in rendered
        assert "visible ready" in rendered
        assert "1.5s" in tiles
        assert "3 sessions" in rendered
        assert "slowest agents" in rendered
        assert format_local(1_900.0, "%b %d %H:%M") in rendered
    
        assert "Stalls & hitches" in rendered
        stalls = _render_plain(pane._perf_stalls_panel(result.perf, width=80))
        assert "tui_stall" in stalls
        assert "tui_hitch" in stalls
        assert "tui_pump_stall" in stalls
        assert "tui_hitch +5 suppressed" in stalls
        assert "Freeze records by context" in rendered
        assert "agents" in rendered
        assert "1 recovery" in rendered
        assert "3.2s" in rendered
    
        assert "Latency & reliability · By Subsystem" in rendered
        assert "Agent runs" in rendered
        assert "LLM calls" in rendered
        assert "Hooks" in rendered
        assert "Workflows" in rendered
        assert "Axe cycles" in rendered
        latency = _render_plain(pane._perf_latency_panel(result.perf, width=180))
        assert "Share" not in latency
        assert pane._perf_count(None) == "—"
        workflows = next(row for row in result.perf.latency.rows if row.key == "workflows")
        axe = next(row for row in result.perf.latency.rows if row.key == "axe")
        assert pane._perf_count(workflows.count) == "—"
        assert pane._perf_count(axe.count) == "—"
        assert workflows.count is None
        assert axe.count is None
    
        assert "Data & instrumentation" in rendered
        assert "Telemetry" in rendered
        assert "enabled" in rendered
        assert "raw" in rendered
        assert "12 raw / 4 5m / 2 1h" in rendered
        assert "git_ops" in rendered
        assert "absent" in rendered
        assert "launch_timing" in rendered
        assert "truncated" in rendered
        assert "1 unreadable" in rendered
        assert "1 unreadable records skipped" in rendered
        assert "Bounded log read truncated older records for: launch_timing" in rendered
>       assert "SASE_TUI_PERF off" in rendered
E       AssertionError: assert 'SASE_TUI_PERF off' in '╭────────────────── Startup breakdown ───────────────────╮   ╭─────────────────── Stalls & hitches ──────────────────...───────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯\n'

tests/ace/tui/test_statistics_perf.py:174: AssertionError
________________ test_tui_app_import_stays_under_startup_budget ________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/bin/python

    def test_tui_app_import_stays_under_startup_budget() -> None:
        """Importing the app should not pull known heavy deferred profile edges."""
    
        last_elapsed = 0.0
        last_count = 0
        for _ in range(2):
>           payload = _measure_tui_app_import()
                      ^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_app_import_budget.py:111: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    def _measure_tui_app_import() -> dict[str, Any]:
        result = subprocess.run(
            [
                sys.executable,
                "-c",
                textwrap.dedent(
                    """
                    import importlib
                    import json
                    import sys
                    import time
    
                    started = time.process_time()
                    importlib.import_module("sase.ace.tui.app")
                    elapsed = time.process_time() - started
    
                    print(json.dumps({
                        "elapsed_seconds": elapsed,
                        "module_count": len(sys.modules),
                        "deferred_modules": [
                            name for name in (
                                "sase.agent.multi_prompt",
                                "sase.agent.multi_prompt_launcher",
                                "sase.agent.scope_sweep",
                                "sase.artifact_cli.create",
                                "sase.artifact_links.projection._agent_created_epic",
                                "sase.core.wait_dependency_resolution",
                                "sase.core.wait_epic_follow_view",
                                "sase.finalizers.commit_memory_guard",
                                "sase.service.status",
                                "sase.service.control",
                                "sase.dev_update",
                                "sase.dev_update.execute",
                                "sase.update_progress",
                            )
                            if name in sys.modules
                        ],
                    }))
                    """
                ),
            ],
            check=False,
            text=True,
            capture_output=True,
        )
        assert result.returncode == 0, result.stderr + result.stdout
        payload = json.loads(result.stdout)
        assert payload["deferred_modules"] == [], (
            f"TUI startup eagerly imports deferred modules: {payload['deferred_modules']!r}"
        )
>       assert payload["module_count"] < _MAX_MODULE_COUNT, (
            f"TUI app import loads {payload['module_count']} modules "
            f"against the {_MAX_MODULE_COUNT} cap; attribute the growth with "
            f"`tools/tui_import_closure --diff "
            f"$(git merge-base HEAD origin/master)` and defer the new edges"
        )
E       AssertionError: TUI app import loads 3529 modules against the 3527 cap; attribute the growth with `tools/tui_import_closure --diff $(git merge-base HEAD origin/master)` and defer the new edges
E       assert 3529 < 3527

tests/ace/tui/test_app_import_budget.py:96: AssertionError
___________________________ test_freeze_happens_once ___________________________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/bin/python

clock = <tests.ace.tui.util.test_gc_policy._Clock object at 0x7f717f1e42f0>
collector = <tests.ace.tui.util.test_gc_policy._Collector object at 0x7f717f1e5fd0>
recorder = <tests.ace.tui.util.test_gc_policy._Recorder object at 0x7f717f1e70e0>
tags = ['startup_freeze', 'idle']

    def test_freeze_happens_once(
        clock: _Clock,
        collector: _Collector,
        recorder: _Recorder,
        tags: list[str],
    ) -> None:
        cold = GCPolicy(
            monotonic=clock,
            last_input_mono=lambda: clock.now - 10.0,
            loads_done=lambda: False,
            collector=collector,
            recorder=recorder,
            trim_runner=lambda: None,
        )
        assert cold.tick(clock.now) is None
        assert collector.collections == 0
    
        policy = _idle_policy(clock, collector, recorder)
        assert policy.tick(clock.now) == "startup_freeze"
        assert collector.collections == 1
        assert collector.freezes == 1
        assert tags == ["startup_freeze"]
    
        # A later idle tick collects again but never re-freezes.
        recorder.gen1 = 150
        clock.advance(61.0)
        assert policy.tick(clock.now) == "idle"
>       assert collector.collections == 2
E       assert 3 == 2
E        +  where 3 = <tests.ace.tui.util.test_gc_policy._Collector object at 0x7f717f1e5fd0>.collections

tests/ace/tui/util/test_gc_policy.py:175: AssertionError
__________________________ test_census_off_by_default __________________________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/bin/python

clock = <tests.ace.tui.util.test_gc_policy._Clock object at 0x7f71568b6a80>
collector = <tests.ace.tui.util.test_gc_policy._Collector object at 0x7f7155f21c80>
recorder = <tests.ace.tui.util.test_gc_policy._Recorder object at 0x7f71568b75c0>

    def test_census_off_by_default(
        clock: _Clock, collector: _Collector, recorder: _Recorder
    ) -> None:
        emitted: list[dict[str, Any]] = []
        policy = _idle_policy(clock, collector, recorder)
        policy._census_emit = emitted.append
        assert policy.tick(clock.now) == "startup_freeze"
        recorder.gen1 = 150
        clock.advance(61.0)
        assert policy.tick(clock.now) == "idle"
>       assert emitted == []
E       AssertionError: assert [{'event': 't...unt': 0, ...}] == []
E         
E         Left contains one more item: {'event': 'tui_gc_census', 'garbage_top': [], 'survivor_top': [], 'garbage_count': 0, ...}
E         Use -v to get more diff

tests/ace/tui/util/test_gc_policy.py:475: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/macro/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/ace/tui/test_agent_archive_controller_lookup.py::test_coalesced_idle_does_not_publish_false_missing_for_queued_open
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/nodes.py:336: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return (x[1] for x in self.iter_markers_with_node(name=name))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  <string>:2: RuntimeWarning: coroutine '_run_archive_request' was never awaited
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=2143239) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=2143284) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:146: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    rv = reductor(4)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_submit_happy_path_settles_on_exit_completion
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/argparse.py:620: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def _metavar_formatter(self, action, default_metavar):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agents/_archive_controller_build.py:343: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    dict(row) for row in payload.get("rows", ()) if isinstance(row, Mapping)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=2143279) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
70.32s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
68.96s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
65.04s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
58.89s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
49.93s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
43.34s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
40.82s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
36.26s call     tests/pager/test_rendered_link_navigation.py::test_mixed_origin_inputs_keep_diff_sha_and_file_path_rules
31.70s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
30.16s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
27.16s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
26.07s call     tests/pager/test_app_history.py::test_bounded_trail_numbering_is_retained_history_only
21.53s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
18.78s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
18.58s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
15.61s call     tests/test_sdd_commit.py::test_commit_sdd_files_removes_persistent_index_lock_after_retry_exhausted
15.51s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
15.39s call     tests/test_bare_git_init.py::TestInitBareGitProject::test_git_runner_removes_persistent_index_lock_after_retries
14.33s call     tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly
14.04s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
=========================== short test summary info ============================
FAILED tests/ace/tui/test_statistics_perf.py::test_populated_perf_renderable_covers_every_panel
FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget
FAILED tests/ace/tui/util/test_gc_policy.py::test_freeze_happens_once - asser...
FAILED tests/ace/tui/util/test_gc_policy.py::test_census_off_by_default - Ass...
==== 4 failed, 57197 passed, 17 skipped, 154 warnings in 880.23s (0:14:40) =====
error: recipe `test-scoped` failed on line 595 with exit code 1
error: recipe `check` failed on line 861 with exit code 1
failed/1  2457290ms
triage test (scoped): 1 KNOWN 3 NEW
NEW test (scoped): FAILED tests/ace/tui/util/test_gc_policy.py::test_census_off_by_default - Ass... — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/test_statistics_perf.py::test_populated_perf_renderable_covers_every_panel — recorded evidence; no owner
KNOWN test (scoped): FAILED tests/ace/tui/util/test_gc_policy.py::test_freeze_happens_once - asser... — witness 0565caed0d1ee997557a16ec01dc1ecb; no owner
sase tool show 399cf5928cebd2fc5752cf5069e2aef7 -l
verdict: new_failures — 3 NEW, 1 KNOWN; exit 1

